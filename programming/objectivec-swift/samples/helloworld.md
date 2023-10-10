---
layout: default-layout
title: HelloWorld Sample - Dynamsoft Barcode Reader for iOS
description: This is the HelloWorld Sample page of Dynamsoft Barcode Reader for iOS SDK.
keywords: iOS, samples, HelloWorld
needAutoGenerateSidebar: true
breadcrumbText: HelloWorld
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/samples/helloworld.html
---

# Decode from Video Sample - Use DynamsoftCameraEnhancer as Image Source

This sample illustrates how to recognize barcode from the video streaming. In this sample, you can read how to use DynamsoftCameraEnhancer to capture the video streaming.

View the samples

* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/HelloWorldObjC/" target="_blank">Objective-C HelloWorld</a>
* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Swift/HelloWorldSwift/" target="_blank">Swift HelloWorld</a>

There are some basic concepts that are helpful on understanding the SDK.

## CaptureVisionRouter

`CaptureVisionRouter` is a router that responsible for retrieving images from the source, coordinating the image processing tasks and dispatching the processing results. To implement a barcode decoding task, what you have to do are:

* Set a standard input for your `CaptureVisionRouter` instance.
* Set a result receiver via your `CaptureVisionRouter` instance.
* Tell your `CaptureVisionRouter` instance to start working and specify a barcode decoding template with its name.
* (Additional) Configure the image processing Parameters to optimize the barcode decoding performance.

## Standard Input

Use the `setInput` method of the `CaptureVisionRouter` to bind an `ImageSourceAdapter` instance is the simplest way to access to the standard input. `CameraEnhancer` is one of the official implementation of the `ImageSourceAdapter` for you to quickly set up the mobile camera as the image source.

## Output

To get the output result, you have to implement the `CapturedResultReceiver` and bind it with your `CaptureVisionRouter` instance. You will receive the barcode decoding results in the `onDecodedBarcodesReceived` method each time when a image (video frame) is processed.

## Control the Start & Stop of the Capturing

If only one barcode decoding result is required in one scan, you can stop the barcode decoding thread via `stopCapturing` method. You can call the `startCapturing` at any time when you want to restart the barcode decoding.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)onDecodedBarcodesReceived:(DSDecodedBarcodesResult *)result {
   if (result.items.count > 0) {
      // Stop capturing if barcode result is no empty.
      dispatch_async(dispatch_get_main_queue(), ^{
         [self.cvr stopCapturing];
      });
      for (DSBarcodeResultItem *item in result.items) {
         // Deal with the result you get.
      }
   }
}
```
2. 
```swift
func onDecodedBarcodesReceived(_ result: DecodedBarcodesResult) {
   if let items = result.items, items.count > 0 {
      DispatchQueue.main.async {
         self.cvr.stopCapturing()
      }
      for item in items {
         // Deal with the result you get.
      }
   }
}
```

For more details about how to get started with Dynamsoft Barcode Reader, please view the [user guide]({{ site.oc }}user-guide.html).
