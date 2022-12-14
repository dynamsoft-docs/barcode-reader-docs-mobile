---
layout: default-layout
title: Video Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows Video methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: video barcode decoding, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/primary-video-v9.0.2.html
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
| [`enableResultVerification`](#enableresultverification) | Enable **Result Verification** feature to improve the accuracy of barcode results for video streaming barcode decoding. |
| [`enableDuplicateFilter`](#enableduplicatefilter) | Enable **Duplicate Filter** feature to filter out the duplicate results in the period of 3000ms for video barcode decoding. |

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

## enableResultVerification

Enable **Result Verification** on the barcode results of video streaming barcode decoding. This feature is not enabled by default.

There are 2 way for you to get barcode results:

- From the return value of [`decode`](primary-decode.md) methods when processing a single image.
- From the [`textResultCallback`](interface-textresultcallback.md) when processing the video streaming.

**Result verification** feature only effects on the **OneD barcode** results you get from `textResultCallback`.

```objc
@property (nonatomic, assign) BOOL enableResultVerification;
```

**Parameters**

`boolean` value which stands for the target status of result verification mode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader enableResultVerification:true];
// To check the status of this mode
[barcodeReader getEnableResultVerification]
```
2. 
```swift
barcodeReader.enableResultVerification = true
// To check the status of this mode
let x = barcodeReader.enableResultVerification
```

## enableDuplicateFilter

Filter out the duplicate results in the period of 3000ms for video barcode decoding. Barcode results with the same text and format will be returned only once during the period.

There are 2 way for you to get barcode results:

- From the return value of [`decode`](primary-decode.md) methods when processing a single image.
- From the [`textResultCallback`](interface-textresultcallback.md) when processing the video streaming.

**Duplicate filter** only effects on the duplicate results that output by `textResultCallback`.

```objc
@property (nonatomic, assign) BOOL enableDuplicateFilter;
```

**Parameters**

`boolean` value which stands for the target status of result duplicate filter mode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader enableDuplicateFilter:true];
// To check the status of this mode
[barcodeReader getEnableDuplicateFilter]
```
2. 
```swift
barcodeReader.enableDuplicateFilter = true
// To check the status of this mode
let x = barcodeReader.enableDuplicateFilter
```
