---
layout: default-layout
title: Decode Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows Decode methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: decodeFileWithName, decodeImage, decodeBuffer, decodeBase64, decode methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: false
permalink: /programming/objectivec-swift/api-reference/primary-decode.html
---


# Decode Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeBuffer(ImageData)`](#decodebufferimagedata) | Decode barcodes from a pixel buffer with width, height, stride and pixel format info. |
  | [`decodeBuffer`](#decodebuffer) | Decode barcodes from a pixel buffer with width, height, stride and pixel format info. |
  | [`decodeFileWithName`](#decodefilewithname) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](#decodefileinmemory) | Decode barcodes from a file that is read in the memory. |
  | [`decodeBase64`](#decodebase64) | Decode barcodes from a base64 encoded string. |
  | [`decodeImage`](#decodeimage) | Decode barcodes from a `UIImage`. |
  
---

## decodeBuffer(ImageData)

Decode barcodes from a pixel buffer with width, height, stride and pixel format info. Generally, this method is used to process the video streaming. You can get a coordinate transformation matrix if you include the orientation information of the image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSArray<iTextResult*>* _Nullable)decodeBuffer:(iImageData* _Nonnull)imageData
                                           error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func decodeBuffer(_ imageData: iImageData) throws -> [iTextResult]
```

**Parameters**

`[in] imageData`: An `iImageData` object that includes the pixel buffer, width, height, stride and pixel format of the image. You can get it from [`AVCaptureVideoDataOutput`](#get-imagedata-from-captureoutput) or [`DynamsoftCameraEnhancer`](#get-imagedata-from-dceframe).  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to read the image.
- The image data type is not supported.

**Return Value**

The [`iTextResult`](auxiliary-iTextResult.md) of each successfully decoded barcode.

**Code Snippet**

### Get ImageData from DCEFrame

If you have imported **DynamsoftCameraEnhancer.framework**, you can get video frames from the `frameOutputCallback`. DCEFrame object contains all required parameters of `decodeBuffer` method.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce addListener:self];
//Get frames in callback methods.
- (void)frameOutPutCallback:(DCEFrame *)frame timeStamp:(NSTimeInterval)timeStamp{
   NSArray<iTextResult*>* barcodeResults = [barcodeReader decodeBuffer:frame.imageData withWidth:frame.width height:frame.height stride:frame.stride format:frame.pixelFormat error:nil];
}
```
2. 
```swift
func frameOutPutCallback(_ frame: DCEFrame, timeStamp: TimeInterval){
   do{
          let barcodeResults = try barcodeReader.decodeBuffer(frame.imageData, withWidth: frame.width, height: frame.height, stride: frame.stride, format: EnumImagePixelFormat(rawValue: frame.pixelFormat) ?? EnumImagePixelFormat.ARGB_8888)
   }catch{
          // Add your code to deal with exceptions
   }
}
```

### Get ImageData from CaptureOutput

If you are acquiring video frames from `captureOutput` callback, you can use the following code to extract the required parameters from `sampleBuffer`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, strong) iImageData *imageData;
...
- (void)captureOutput:(AVCaptureOutput *)captureOutput didOutputSampleBuffer:(CMSampleBufferRef)sampleBuffer fromConnection:(AVCaptureConnection *)connection;
{
   // Extract image data from sampleBuffer.
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
   // Assign value for the imageData
   self.imageData.bytes = buffer;
   self.imageData.width = width;
   self.imageData.height = height;
   self.imageData.stride = bytesPerRow;
   self.imageData.format = EnumImagePixelFormatARGB_8888;
   // Orientation is an optional property.
   // The library will output a transformation matrix to help you transform the coordinate of the barcode result points when you include the image orientation information.
   self.imageData.orientation = 0;
}
```
2. 
```swift
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
   // Orientation is an optional property.
   // The library will output a transformation matrix to help you transform the coordinate of the barcode result points when you include the image orientation information.
   imageData.orientation = 0
}
```

> View sample <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Swift/DecodeWithAVCaptureSession" target="_blank">`DecodeWithAVCaptureSession`</a> to see how to process the video streaming.

## decodeBuffer

Decode barcodes from image data that including pixel buffer, width, height, stride and pixel format.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSArray<iTextResult*>* _Nullable)decodeBuffer:(NSData* _Nonnull)buffer
                                       withWidth:(NSInteger)width
                                          height:(NSInteger)height
                                          stride:(NSInteger)stride
                                          format:(EnumImagePixelFormat)format
                                           error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func decodeBuffer(_ buffer: Data, width: Int, height: Int, stride: Int, format: EnumImagePixelFormat) throws -> [iTextResult]
```

**Parameters**

`[in] buffer`: The array of bytes that stores the pixel buffer of the image.  
`[in] width`: The width of the image in pixels.  
`[in] height`: The height of the image in pixels.  
`[in] stride`: The stride is measured by the `byte` length of each line in the `buffer`.  
`[in] format`: The image pixel format used in the image byte array.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to read the image.
- The image data type is not supported.

**Return Value**

The [`iTextResult`](auxiliary-iTextResult.md) of each successfully decoded barcode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce addListener:self];
//Get frames in callback methods.
- (void)frameOutPutCallback:(DCEFrame *)frame timeStamp:(NSTimeInterval)timeStamp{
   NSArray<iTextResult*>* barcodeResults = [barcodeReader decodeBuffer:frame.imageData withWidth:frame.width height:frame.height stride:frame.stride format:frame.pixelFormat error:nil];
}
```
2. 
```swift
func frameOutPutCallback(_ frame: DCEFrame, timeStamp: TimeInterval){
   do{
          let barcodeResults = try barcodeReader.decodeBuffer(frame.imageData, withWidth: frame.width, height: frame.height, stride: frame.stride, format: EnumImagePixelFormat(rawValue: frame.pixelFormat) ?? EnumImagePixelFormat.ARGB_8888)
   }catch{
          // Add your code to deal with exceptions
   }
}
```

## decodeFileWithName

Decode barcodes from a specified image file.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSArray<iTextResult*>* _Nullable)decodeFileWithName:(NSString* _Nonnull)path
                                                 error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func decodeFileWithName(_ path: String) throws -> [iTextResult]
```

**Parameters**

`[in] name`: The local path of the file. It supports BMP, TIFF, JPG, PNG and PDF files.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The file is not found.
- The library failed to read the image.
- The image data type is not supported.

**Return Value**

The [`iTextResult`](auxiliary-iTextResult.md) of each successfully decoded barcode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSArray<iTextResult*>* barcodeResults = [barcodeReader decodeFileWithName:@"your file path" error:&error];
```
2. 
```swift
do{
   let barcodeResults = try barcodeReader.decodeFileWithName("your file path")
}catch{
   // Add your code to deal with exceptions
}
```

## decodeFileInMemory

Decode barcodes from a file that is read in the memory.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSArray<iTextResult *> *_Nullable)decodeFileInMemory:(NSData *_Nonnull)buffer error:(NSError *_Nullable *_Nullable)error;
```
2. 
```swift
func decodeFile(inMemory buffer: Data) throws -> [iTextResult]
```

**Parameter**

`[in] buffer`: The image file that is read in memory.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to read the image.
- The image data type is not supported.

**Return Value**

The [`iTextResult`](auxiliary-iTextResult.md) of each successfully decoded barcode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError __autoreleasing * _Nullable error;
NSData * imageBuffer = [[NSData alloc] initWithContentOfFile:@"The file path"];
NSArray<iTextResult*>* barcodeResults = [barcodeReader decodeFileInMemory:imageBuffer error:&error];
```
2. 
```swift
do{
   let imageBuffer = try NSData.init(contentsOfFile:"The file path")
   let barcodeResults = try barcodeReader.decodeFileInMemory(imageBuffer)
}catch{
   // Add your code to deal with exceptions
}
```

## decodeBase64

Decode barcodes from an image file encoded as a base64 string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSArray<iTextResult*>* _Nullable)decodeBase64:(NSString* _Nonnull)base64
                                           error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func decodeBase64(_ base64: String) throws -> [iTextResult]
```

**Parameters**

`[in] base64`: A base64 encoded string that represents an image.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to read the image.
- The image data type is not supported.

**Return Value**

The [`iTextResult`](auxiliary-iTextResult.md) of each successfully decoded barcode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError __autoreleasing * _Nullable error;
NSArray<iTextResult*>* barcodeResults = [barcodeReader decodeBase64:@"file in base64 string" error:&error];
```
2. 
```swift
do{
   let barcodeResults = try barcodeReader.decodeBase64("file in base64 string")
}catch{
   // Add your code to deal with exceptions
}
```

## decodeImage

Decode barcodes from a UIImage.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSArray<iTextResult*>* _Nullable)decodeImage:(UIImage* _Nonnull)image
                                          error:(NSError* _Nullable * _Nullable)error
                                          NS_SWIFT_NAME(decodeImage(_:));
```
2. 
```swift
func decodeImage(_ image: UIImage) throws -> [iTextResult]
```

**Parameters**

`[in] image`: A UIImage object.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to read the image.
- The image data type is not supported.

**Return Value**

The [`iTextResult`](auxiliary-iTextResult.md) of each successfully decoded barcode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
UIImage *image = [[UIImage alloc] init];
NSError __autoreleasing * _Nullable error;
NSArray<iTextResult*>* barcodeResults = [_barcodeReader decodeImage:image error:&error];
```
2. 
```swift
let frameImage = dce.getFrameFromBuffer(true).toUIImage()
do{
   let barcodeResults = try barcodeReader.decodeImage(frameImage)
}catch{
   // Add your code to deal with exceptions
}
```
