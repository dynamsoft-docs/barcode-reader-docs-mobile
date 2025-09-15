---
layout: default-layout
title: Protocol ImageSource - Dynamsoft Barcode Reader iOS API Reference
description: This page shows ImageSource protocol of Dynamsoft Barcode Reader for iOS SDK.
keywords: ImageSource, Protocol, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
ignore: true
permalink: /programming/objectivec-swift/api-reference/protocol-imagesource.html
---

# ImageSource

Protocol for producers of images. It can be implemented by developers to support other image sources, such as external cameras or image filesets.

How to Use:

1. Use [`BarcodeReader.setImageSource`](primary-video.html#setimagesource) to set `ImageSource` as the source of image.
2. Add code in method `getImage`. When DBR finishes the current process and trying to start decoding from another image, it will call the `getImage`.
3. Trigger [`BarcodeReader.startScanning`](primary-video.html#startscanning) to start the barcode decoding thread when all above are configured.
4. When barcode decoding thread is started, users can stop the thread by calling [`BarcodeReader.stopScanning`](primary-video.html#stopscanning)

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@protocol ImageSource <NSObject>
```
2. 
```swift
protocol ImageSource : NSObjectProtocol
```

| Method | Description |
| ------ | ----------- |
| `getImage` | The method for users for complete. Get image/video from external sources and out put the data as [`iImageData`](auxiliary-iImageData.html). |

## getImage

The method for users for complete which returns [`iImageData`](auxiliary-iImageData.html). When using external sources, users can generate the external image source into [`iImageData`](auxiliary-iImageData.html) and output them in method `getImage` so that the image can be recognized by the Barcode Reader.

The barcode reader will continuously use `getImage` to acquire [`iImageData`](auxiliary-iImageData.html) for barcode decoding when:

- Method [`BarcodeReader.setImageSource`](primary-video.html#setimagesource) has been configured in user's project.
- [`BarcodeReader.startScanning`](primary-video.html#startscanning) is triggered.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (iImageData *_Nullable)getImage;
```
2. 
```swift
func getImage() -> iImageData?
```

**Return Value**

An object of [`iImageData`](auxiliary-iImageData.html).

**Code Snippet**

Here we use AVFoundation as the example of the image source. The following code displays how to use AVFoundation to capture video frames and tranfer the video frames into [`iImageData`](auxiliary-iImageData.html).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Add property imageData in your project to receive the image data.
@property (nonatomic, strong) iImageData *imageData;
//Start barcode decoding when the view appears.
- (void)viewWillAppear:(BOOL)animated {
   [super viewWillAppear:animated];
   [self.barcodeReader startScanning];
}
//Stop barcode decoding when the view disappears.
- (void)viewWillDisappear:(BOOL)animated {
   [super viewWillDisappear:animated];
   [self.barcodeReader stopScanning];
}
- (void)configurationDBR {
   self.barcodeReader = [[DynamsoftBarcodeReader alloc] init];
   // Set image source
   [self.barcodeReader setImageSource:self];
   [self.barcodeReader setDBRTextResultListener:self];
}
...
// Get the buffer image from AVCaptureOutput and generate the image into iImageData.
- (void)captureOutput:(AVCaptureOutput *)output didOutputSampleBuffer:(CMSampleBufferRef)sampleBuffer fromConnection:(AVCaptureConnection *)connection {
   CVImageBufferRef imageBuffer = CMSampleBufferGetImageBuffer(sampleBuffer);
   if (imageBuffer == nil) {
          return;
   }
   CVPixelBufferLockBaseAddress(imageBuffer, 0);
   void *baseAddress = CVPixelBufferGetBaseAddress(imageBuffer);
   size_t bufferSize = CVPixelBufferGetDataSize(imageBuffer);
   size_t width = CVPixelBufferGetWidth(imageBuffer);
   size_t height = CVPixelBufferGetHeight(imageBuffer);
   size_t bytesPerRow = CVPixelBufferGetBytesPerRow(imageBuffer);
   CVPixelBufferUnlockBaseAddress(imageBuffer,0);
   NSData *buffer = [NSData dataWithBytes:baseAddress length:bufferSize];
   // Initialize the image data and allocate the value.
   if (self.imageData == nil) {
          self.imageData = [[iImageData alloc] init];
   }
   self.imageData.bytes = buffer;
   self.imageData.width = width;
   self.imageData.height = height;
   self.imageData.stride = bytesPerRow;
   self.imageData.format = EnumImagePixelFormatARGB_8888;
}
// Configure the getImage method.
- (iImageData *)getImage {
   return self.imageData;
}
- (void)textResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iTextResult *> *)results {
   // Add your code to execute when iTextResult is received.
}
```
2. 
```swift
class CamerViewController: UIViewController, AVCaptureVideoDataOutputSampleBufferDelegate, ImageSource, DBRTextResultListener{
   // Add property imageData in your project to receive the image data.
   var imageData:iImageData! = nil
   //Start barcode decoding when the view appears.
   override func viewWillAppear(_ animated: Bool) {
          barcodeReader.startScanning()
   }
   //Stop barcode decoding when the view disappears.
   override func viewWillDisappear(_ animated: Bool) {
          barcodeReader.stopScanning()
   }
   func setDBR() {
          barcodeReader = DynamsoftBarcodeReader.init()
          // Set image source
          barcodeReader.setImageSource(self)
          barcodeReader.setDBRTextResultListener(self)
   }
   // Get the buffer image from AVCaptureOutput and generate the image into iImageData.
   func captureOutput(_ output: AVCaptureOutput, didOutput sampleBuffer: CMSampleBuffer, from connection: AVCaptureConnection)
   {
          let imageBuffer:CVImageBuffer = CMSampleBufferGetImageBuffer(sampleBuffer)!
          CVPixelBufferLockBaseAddress(imageBuffer, .readOnly)
          let baseAddress = CVPixelBufferGetBaseAddress(imageBuffer)
          let bufferSize = CVPixelBufferGetDataSize(imageBuffer)
          let width = CVPixelBufferGetWidth(imageBuffer)
          let height = CVPixelBufferGetHeight(imageBuffer)
          let bpr = CVPixelBufferGetBytesPerRow(imageBuffer)
          CVPixelBufferUnlockBaseAddress(imageBuffer, .readOnly)
          let buffer = Data(bytes: baseAddress!, count: bufferSize)
          // Initialize the image data and allocate the value
          if (imageData == nil) {
             imageData = iImageData.init()
          }
          imageData.bytes = buffer
          imageData.width = width
          imageData.height = height
          imageData.stride = bpr
          imageData.format = .ARGB_8888
   }
   // Configure the getImage method.
   func getImage() -> iImageData? {
          return imageData
   }
   func textResultCallback(_ frameId: Int, imageData: iImageData, results: [iTextResult]?){
          // Add your code to execute when iTextResult is received.
   }
}
```
