---
layout: default-layout
title: Dynamsoft Barcode Reader Objective-C & Swift API Reference - Video Methods
description: This page shows Video methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: startFrameDecoding, startFrameDecodingEx, appendFrame, stopFrameDecoding, getFrameDecodingParameters, setDBRErrorDelegate, setDBRTextResultDelegate, setDBRIntermediateResultDelegate, getLengthOfFrameQueue, video methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/primary-video.html
---

# Video Decoding Methods

> Note:
>  
> - You have to include `DynamsoftCameraEnhancer` when using **Video Decoding Methods**.  
> - `DynamsoftCameraEnhancer` provide APIs that help you quickly deploy a camera module and capture video streaming for barcode decoding.  
> - Through **Video Decoding Methods** you can control whether to start video streaming barcode decoding and get the barcode results.  
> - Be sure that your `DynamsoftBarcodeReader` version is **8.9.0+** and `DynamsoftCameraEnhancer` is **2.1.0+** when using the methods on this page.

| Method               | Description |
|----------------------|-------------|
| [`setCameraEnhancer`](#setcameraenhancer) | Bind a Camera Enhancer instance to the Barcode Reader.  |
| [`startScanning`](#startscanning) | Start the barcode reading thread. |
| [`stopScanning`](#stopscanning) | Stop the barcode reading thread. |
| [`setDBRTextResultListener`](#setdbrtextresultlistener) | Set callback function to process text results generated during frame decoding. |
| [`setDBRIntermediateResultListener`](#setdbrintermediateresultlistener) | Set callback function to process intermediate results generated during frame decoding. |
| [`minImageReadingInterval`](#minimagereadinginterval) | The property indicates the minimum interval between two barcode decoding. |
| [`setImageSource`](#setimagesource) | Set the ImageSource as the source of video streaming. |

---

## setCameraEnhancer

Bind a `DynamsoftCameraEnhancer` instance to the Barcode Reader.

```objc
- (void)setCameraEnhancer:(DynamsoftCameraEnhancer* _Nonnull)cameraInstance;
```

**Parameters**

`cameraInstance`: An instance of `Dynamsoft Camera Enhancer`.

**Code Snippet**

This code snippet displays a complete code on how to add DynamsoftCameraEnhancer to your project and start to use Video Decoding Methods to decode and get barcode results from the video streaming.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
/* Be sure that you have import the following headers when using video decoding methods */
#import <DynamsoftBarcodeReader/DynamsoftBarcodeReader.h>
#import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
/* You have to add DBRTextResultListener to your interface. */
@interface ViewController ()<DBRTextResultListener>
@property(nonatomic, strong) DynamsoftBarcodeReader *barcodeReader;
@property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
@property(nonatomic, strong) DCECameraView *dceView;
@end
@implementation ViewController
- (void)viewDidLoad{
   [super viewDidLoad];
   [self configurationDBR];
}
- (void)configurationDBR{
   _barcodeReader =  [[DynamsoftBarcodeReader alloc] init];
   _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
   [self.view addSubview:_dceView];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   [_dce open];
   [_barcodeReader setCameraEnhancer:_dce];
   [_barcodeReader startScanning];
   [_barcodeReader setDBRTextResultListener:self];
}
- (void)textResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iTextResult *> *)results{
   // Add your code to do when barcode result is returned.
}
```
2. 
```swift
// Be sure that you have import the following headers when using video decoding methods
import DynamsoftBarcodeReader
import DynamsoftCameraEnhancer
// You have to add setDBRTextResultListener to your class.
class ViewController: UIViewController, DBRTextResultListener{
   var SafeAreaBottomHeight:CGFloat = UIApplication.shared.statusBarFrame.size.height > 20 ? 34 : 0
   var mainHeight = UIScreen.main.bounds.height
   var mainWidth = UIScreen.main.bounds.width
   var dce:DynamsoftCameraEnhancer! = nil
   var dceView:DCECameraView! = nil
   var barcodeReader:DynamsoftBarcodeReader! = nil
   override func viewDidLoad(){
          super.viewDidLoad()
          configurationDBR()
   }
   override func viewWillAppear(_ animated: Bool) {
        barcodeReader.startScanning()
   }
   override func viewWillDisappear(_ animated: Bool) {
        barcodeReader.stopScanning()
   }
   func configurationDBR(){
          barcodeReader = DynamsoftBarcodeReader.init()
          var barHeight = self.navigationController?.navigationBar.frame.height
          if UIApplication.shared.statusBarFrame.size.height <= 20 {
             barHeight = 20
          }
          dceView = DCECameraView.init(frame: CGRect(x: 0, y: barHeight!, width: mainWidth, height: mainHeight - SafeAreaBottomHeight - barHeight!))
          self.view.addSubview(dceView)
          dce = DynamsoftCameraEnhancer.init(view: dceView)
          dce.open()
          barcodeReader.setCameraEnhancer(dce)
          barcodeReader.setDBRTextResultListener(self)
   }
   func textResultCallback(_ frameId: Int, imageData: iImageData, results: [iTextResult]?){
          // Add your code
   }
}
```

## startScanning

Start the video streaming barcode decoding thread. Please be sure that you have bound a `DynamsoftCameraEnhacner` or [`ImageSource`](protocol-imagesource.md) to the barcode reader before you trigger `startScanning`.

```objc
-(void)startScanning;
```

**Code Snippet**

You can view detailed code snippet in [`setCameraEnhancer`](#setcameraenhancer)

## stopScanning

Stop the video streaming barcode decoding thread.

```objc
-(void)stopScanning;
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_barcodeReader stopScanning];
```
2. 
```swift
barcodeReader.stopScanning()
```

## setDBRTextResultListener

Set callback function to process text results generated during frame decoding.

```objc
-(void)setDBRTextResultListener:(id _Nullable)textResultListener;
```

**Parameters**

`[in] textResultListener`: Callback function.

**Code Snippet**

You can view detailed code snippet in [`setCameraEnhancer`](#setcameraenhancer)

## setDBRIntermediateResultListener

Set callback function to process intermediate results generated during frame decoding.

```objc
-(void)setDBRIntermediateResultListener:(id _Nullable)intermediateResultListener;
```

**Parameters**

`[in] intermediateResultListener`: Callback function.

**Code Snippet**

The usage of `intermediateResultListener` is similar to the `textResultListener`. You can view detailed code snippet in [`setCameraEnhancer`](#setcameraenhancer) and replace the `textResultListener` code with the `intermediateResultListener` code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// You have to add DBRIntermediateResultListener to your interface.
@interface ViewController ()<DBRIntermediateResultListener>
- (void)configurationDBR{
   _barcodeReader =  [[DynamsoftBarcodeReader alloc] init];
   [_barcodeReader setDBRIntermediateResultListener:self];
}
- (void)intermediateResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iTextResult *> *)results{
   // Add your code to execute when intermediate result is returned.
}
```
2. 
```swift
// You have to add DBRIntermediateResultListener to your class.
class ViewController: UIViewController, DBRIntermediateResultListener{
   func configurationDBR(){
          barcodeReader = DynamsoftBarcodeReader.init()
          barcodeReader.setDBRIntermediateResultListener(self)
   }
   func intermediateResultCallback(_ frameId: Int, imageData: iImageData, results: [iTextResult]?){
          // Add your code to execute when intermediate result is returned.
   }
}
```

## minImageReadingInterval

The property indicates the minimum interval between two barcode decoding. The unit of measure for this property is milliseconds. If the previous barcode decoding is finished in `n` milliseconds (`n` < `minImageReadingInterval`), the barcode decoding thread will be paused by `minImageReadingInterval` - `n` milliseconds.

```objc
@property NSInteger minImageReadingInterval;
```

## setImageSource

Set the ImageSource as the source of video streaming.

```objc
- (void)setImageSource:(nonnull id<ImageSource>)source;
```

**Parameters**

`[in] source` The protocol of ImageSource.

**Code Snippet**

Here we use AVFoundation as the example of the image source. The following code displays how to use AVFoundation to capture video frames and tranfer the video frames into [`iImageData`](auxiliary-iImageData.md).

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
