---
layout: default-layout
title: How to use the Barcode Reader without the Camera Enhancer - Dynamsoft Barcode Reader for iOS
description: This guide demonstrates how to use the Dynamsoft Barcode Reader SDK with the AV Capture API rather than the Camera Enhancer.
keywords: iOS, sample, Android, camera
needAutoGenerateSidebar: true
breadcrumbText: No Camera Enhancer
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/samples/no-camera-enhancer.html
ignore: true
---

# Decode from Video Sample - Use AVCaptureSession as Image Source

`DecodeWithAVCaptureSession` is another sample of recognizing barcodes from the video streaming. In this sample, instead of [`DynamsoftCameraEnhancer`]({{ site.dce_ios }}), `AVCaptureSession` is used to implement the [`ImageSourceAdapter`]({{ site.dcvb_ios_api }}core/basic-structures/image-source-adapter.html) (ISA) so that the `CaptureVisionRouter` is able to fetch the video frames.

**View the sample code**

* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.2002/ios/HelloWorld/DecodeWithAVCaptureSession/" target="_blank">Swift DecodeWithAVCaptureSession Sample</a>
* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.2002/ios/HelloWorld/DecodeWithAVCaptureSessionObjc/" target="_blank">Objective-C DecodeWithAVCaptureSession Sample</a>

## Generate ImageData from AVCaptureVideoDataOutput

[`ImageData`]({{ site.dcvb_ios_api }}core/basic-structures/image-data.html) is the standard image data type that can be recognized by Dynamsoft SDKs. [`ISA`]({{ site.dcvb_ios_api }}core/basic-structures/image-source-adapter.html) is the interface that maintains a video buffer of the `ImageData` and deliver the `ImageData` objects to Dynamsoft image processing SDKs.

* Create a Class for implementing the video streaming functions with `AVCaptureSession`.
* Let your class extend `ImageSourceAdapter` so that you can use ISA APIs.
* Receive video frames from AVCaptureVideoDataOutput and generate the image data to ImageData object.
* Send the `ImageData` to the ISA with its `addImageToBuffer` method. After that the ImageData will be maintained in the video buffer of the ISA.

The following code snippet shows how to generate ImageData from the `AVCaptureVideoDataOutput`

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@implementation DSCaptureEnhancer
- (void)captureOutput:(AVCaptureOutput *)output didOutputSampleBuffer:(CMSampleBufferRef)sampleBuffer fromConnection:(AVCaptureConnection *)connection {
   CVImageBufferRef imageBuffer = CMSampleBufferGetImageBuffer(sampleBuffer);
   CVPixelBufferLockBaseAddress(imageBuffer, kCVPixelBufferLock_ReadOnly);
   void *baseAddress = CVPixelBufferGetBaseAddress(imageBuffer);
   size_t bufferSize = CVPixelBufferGetDataSize(imageBuffer);
   size_t width = CVPixelBufferGetWidth(imageBuffer);
   size_t height = CVPixelBufferGetHeight(imageBuffer);
   size_t bytesPerRow = CVPixelBufferGetBytesPerRow(imageBuffer);
   CVPixelBufferUnlockBaseAddress(imageBuffer, kCVPixelBufferLock_ReadOnly);
   NSData *buffer = [NSData dataWithBytes:baseAddress length:bufferSize];
   // Create an ImageDate object with the data you extract from the CVImageBuffer
   DSImageData *imageData = [[DSImageData alloc] initWithBytes:buffer width:width height:heightstride:bytesPerRow format:DSImagePixelFormatARGB8888 orientation:0 tag:nil];
   // addImageToBuffer method can add your ImageData to the buffer of ISA.
   [self addImageToBuffer:imageData];
}
@end
```
2. 
```swift
// Let your class extend ImageSourceAdapter so that you can use ImageSourceAdapter APIs.
class CaptureEnhancer: ImageSourceAdapter, AVCaptureVideoDataOutputSampleBufferDelegate {
   ...
   func captureOutput(_ output: AVCaptureOutput, didOutput sampleBuffer: CMSampleBuffer, from connection: AVCaptureConnection)
   {
      let imageBuffer:CVImageBuffer = CMSampleBufferGetImageBuffer(sampleBuffer)!
      CVPixelBufferLockBaseAddress(imageBuffer, .readOnly)
      let baseAddress = CVPixelBufferGetBaseAddress(imageBuffer)
      let bufferSize = CVPixelBufferGetDataSize(imageBuffer)
      let width = CVPixelBufferGetWidth(imageBuffer)
      let height = CVPixelBufferGetHeight(imageBuffer)
      let bytesPerRow = CVPixelBufferGetBytesPerRow(imageBuffer)
      CVPixelBufferUnlockBaseAddress(imageBuffer, .readOnly)
      let buffer = Data(bytes: baseAddress!, count: bufferSize)
      // Create an ImageDate object with the data you extract from the CVImageBuffer
      let imageData = ImageData(bytes: buffer, width: UInt(width), height: UInt(height), stride: UInt(bytesPerRow), format: .ARGB8888, orientation: 0, tag: nil)
      // addImageToBuffer method can add your ImageData to the buffer of ISA.
      addImageToBuffer(imageData)
   }
}
```

## Setup CaptureVisionRouter with the ISA You Implemented Above

The following code snippet show how to bind the `ISA` you implemented above to the `CaptureVisionRouter` and start barcode decoding.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Let your view controller implement CapturedResultReceiver.
@interface ViewController () <DSCapturedResultReceiver>
...
- (void)setUpDCV {
   // Initialize the class you created above.
   self.capture = [[DSCaptureEnhancer alloc] init];
   self.cvr = [[DSCaptureVisionRouter alloc] init];
   NSError *error;
   // Bind the `capture` as an ISA instance to your CaptureVisionRouter.
   [self.cvr setInput:self.capture error:&error];
   // Add CapturedResultReceiver to receive barcode decoding results.
   [self.cvr addResultReceiver:self];
}
- (void)onDecodedBarcodesReceived:(DSDecodedBarcodesResult *)result {
   // Add code to do when barcode decoding results are received.
}
- (void)viewWillAppear:(BOOL)animated {
   // Start capturing.
   [self.cvr startCapturing:DSPresetTemplateReadBarcodes completionHandler:^(BOOL isSuccess, NSError * _Nullable error) {
       NSAssert((error == nil), error.description);
   }];
}
```
2. 
```swift
// Let your view controller implement CapturedResultReceiver.
class ViewController: UIViewController, CapturedResultReceiver {
   var capture:CaptureEnhancer!
   let cvr = CaptureVisionRouter()
   ...
   func setUpDCV() {
      // Initialize the class you created above.
      capture = .init()
      // Bind the `capture` as an ISA instance to your CaptureVisionRouter.
      try! cvr.setInput(capture)
      // Add CapturedResultReceiver to receive barcode decoding results.
      cvr.addResultReceiver(self)
   }
   override func viewWillAppear(_ animated: Bool) {
      // Start capturing.
      cvr.startCapturing(PresetTemplate.readBarcodes.rawValue) { isSuccess, error in
         if (!isSuccess) {
            if let error = error {
               print(error)
            }
         }
      }
   }
   func onDecodedBarcodesReceived(_ result: DecodedBarcodesResult) {
      // Add code to do when barcode decoding results are received.
   }
}
```
