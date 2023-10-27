---
layout: default-layout
title: How to use the Barcode Reader without the Camera Enhancer - Dynamsoft Barcode Reader for iOS
description: This guide demonstrates how to use the Dynamsoft Barcode Reader SDK with the AV Capture API rather than the Camera Enhancer.
keywords: iOS, sample, Android, camera
needAutoGenerateSidebar: true
breadcrumbText: No Camera Enhancer
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/samples/no-camera-enhancer-v9.6.30.html
---

# DecodeWithAVCaptureSession Sample

**DecodeWithAVCaptureSession** is a sample that demonstrates how to decode barcodes from video streaming when you are using AVFoundation as the source of video streaming. When using AVFoundation as the video source, the key points are:

- Set up `AVCaptureSession` for capturing and displaying the video streaming.
- Receive the `CMSampleBuffer` from `AVCaptureVideoDataOutput` and transfer the `CMSampleBuffer` to `iImageData` so that it can be recognized by `DynamsoftBarcodeReader`.
- Add configurations to interface `ImageSource`. Let the method `getImage` return the iImageData you generated from `AVCaptureVideoDataOutput`. The barcode reader can continuously obtain the `iImageData` via method `getImage`.

**View the Sample(s)**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.20/ios/Objective-C/DecodeWithAVCaptureSession/" target="_blank">Objective-C DecodeWithAVCaptureSession Sample</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.20/ios/Swift/DecodeWithAVCaptureSession/" target="_blank">Swift DecodeWithAVCaptureSession Sample</a>

## Generate ImageData from AVCaptureVideoDataOutput

`iImageData` is the data type that can be recognized by `DynamsoftBarcodeReader` as an image source for barcode decoding. The following code snippet shows you how to transfer `CMSampleBuffer`, which is produced by `AVCaptureSession`, to an `iImageData` object.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Create an iImageData property. The property will receive the image data from AVCaptureVideoDataOutput
@property (nonatomic, strong) iImageData *imageData;
...
// Receive data from captureOutput and transfer CMSampleBuffer to iImageData
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
   if (self.imageData == nil) {
          self.imageData = [[iImageData alloc] init];
   }
   self.imageData.bytes = buffer;
   self.imageData.width = width;
   self.imageData.height = height;
   self.imageData.stride = bytesPerRow;
   self.imageData.format = EnumImagePixelFormatARGB_8888;
}
```
2. 
```swift
class CamerViewController: UIViewController, AVCaptureVideoDataOutputSampleBufferDelegate, ImageSource, DBRTextResultListener{
   // Create an iImageData property. The property will receive the image data from AVCaptureVideoDataOutput
   var imageData:iImageData! = nil
}
// Receive data from captureOutput and transfer CMSampleBuffer to iImageData
func captureOutput(_ output: AVCaptureOutput, didOutput sampleBuffer: CMSampleBuffer, from connection: AVCaptureConnection){
   let imageBuffer:CVImageBuffer = CMSampleBufferGetImageBuffer(sampleBuffer)!
   CVPixelBufferLockBaseAddress(imageBuffer, .readOnly)
   let baseAddress = CVPixelBufferGetBaseAddress(imageBuffer)
   let bufferSize = CVPixelBufferGetDataSize(imageBuffer)
   let width = CVPixelBufferGetWidth(imageBuffer)
   let height = CVPixelBufferGetHeight(imageBuffer)
   let bpr = CVPixelBufferGetBytesPerRow(imageBuffer)
   CVPixelBufferUnlockBaseAddress(imageBuffer, .readOnly)
   let buffer = Data(bytes: baseAddress!, count: bufferSize)
   if (imageData == nil) {
          imageData = iImageData.init()
   }
   imageData.bytes = buffer
   imageData.width = width
   imageData.height = height
   imageData.stride = bpr
   imageData.format = .ARGB_8888
}
```

## Setup Image Source

There are three key points when decoding barcodes from the video streaming:

- Set up the source of image. The source and be either `ImageSource` or `DynamsoftCameraEnhancer`.
- Set up the `DBRTextResultListener` for receiving the barcode result from the callback.
- Trigger the method `startScanning` when you want to start video streaming barcode decoding.

The following code snippet shows how to use `ImageSource` as the source of video barcode decoding.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Add Delegate ImageSource and DBRTextResultListener to your ViewController
@interface CameraViewController ()<AVCaptureVideoDataOutputSampleBufferDelegate, ImageSource, DBRTextResultListener>
- (void)viewWillAppear:(BOOL)animated {
   [super viewWillAppear:animated];
   // Methods startScanning and stopScanning are the switch of barcode decoding thread.
   // Once you have configured the source of image and trigger startScanning, you will be able to receive barcode result from textResultCallback.
   [self.barcodeReader startScanning];
}
- (void)viewWillDisappear:(BOOL)animated {
   [super viewWillDisappear:animated];
   [self.barcodeReader stopScanning];
}
- (void)configurationDBR {
   self.barcodeReader = [[DynamsoftBarcodeReader alloc] init];
   // Set the ImageSource so that DBR will read barcode from ImageSource.
   [self.barcodeReader setImageSource:self];
   // Set text result listener so that you can receive barcode result from textResultCallback.
   [self.barcodeReader setDBRTextResultListener:self];
}
// Configure the method getImage. The method will be triggered each time when the library finished processing the previous image.
- (iImageData *)getImage {
   // The imageData here is the iImageData we transfered from CMSampleBuffer in the previous step.
   return self.imageData;
}
// Receive the text results each time when barcode processing is finished
- (void)textResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iTextResult *> *)results {
   // Add code to execute when barcode results are received.
}
```
2. 
```swift
// Add Delegate ImageSource and DBRTextResultListener to your ViewController
class CamerViewController: UIViewController, AVCaptureVideoDataOutputSampleBufferDelegate, ImageSource, DBRTextResultListener{
   override func viewWillAppear(_ animated: Bool) {
          // Methods startScanning and stopScanning are the switch of barcode decoding thread.
          // Once you have configured the source of image and trigger startScanning, you will be able to receive barcode result from textResultCallback.
          barcodeReader.startScanning()
   }
   override func viewWillDisappear(_ animated: Bool) {
          barcodeReader.stopScanning()
   }
   func configurationDBR() {
          barcodeReader = DynamsoftBarcodeReader.init()
          // Set the ImageSource so that DBR will read barcode from ImageSource.
          barcodeReader.setImageSource(self)
          // Set text result listener so that you can receive barcode result from textResultCallback.
          barcodeReader.setDBRTextResultListener(self)
   }
   // Configure the method getImage. The method will be triggered each time when the library finished processing the previous image.
   func getImage() -> iImageData? {
          return imageData
   }
   // Receive the text results each time when barcode processing is finished
   func textResultCallback(_ frameId: Int, imageData: iImageData, results: [iTextResult]?) {
          // Add code to execute when barcode results are received.
   }
}
```

If you still have questions about the usage of `AVCaptureSession` when implementing video barcode decoding, you can view the sample for more details.
