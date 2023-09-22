---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader for iOS
description: This is the user guide of Dynamsoft Barcode Reader for iOS SDK.
keywords: user guide, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/user-guide.html
---


# Getting Started with iOS

## Requirements

- Supported OS: **iOS 9** or higher (**iOS 11** and higher recommended).
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 7.1 and above (Xcode 13.0+ recommended).

## Add the SDK

There are three ways to add the SDK into your project - **Manually**, via **CocoaPods**, or via **Swift Package Manager**.

### Add the Frameworks Manually

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">Dynamsoft Website</a>. After unzipping, you can find the following **xcframeworks** under the **DynamsoftBarcodeReader\Frameworks** directory:

| File | Description |
| :--- | :---------- |
| DynamsoftBarcodeReader.xcframework | The Dynamsoft Barcode Reader SDK, including barcode decoding algorithm and related APIs. |
| DynamsoftCore.xcframework | The core library of Dynamsoft’s capture vision SDKs, including basic structures and intermediate result related APIs. |
| DynamsoftCaptureVisionRouter.xcframework | The CaptureVisionRouter is what a user uses to interact with image-processing and semantic-processing products in their applications. It accepts an image source and returns processing results which may contain Final results or Intermediate Results. |
| DynamsoftImageProcessing.xcframework | The image processing library of Dynamsoft’s capture vision SDKs, including image processing algorithms and APIs. |
| DynamsoftLicense.xcframework | The module includes the licensing APIs.
| DynamsoftCameraEnhancer.xcframework | The Dynamsoft Camera Enhancer SDK, including camera control and frame preprocessing APIs. |
| DynamsoftUtility.xcframework (Optional) | The module includes functional APIs that support you to integrate the input, filtering the results, generating result images, etc. |

2. Drag and drop the **xcframeworks** into your Xcode project. Make sure to check `Copy items if needed` and `Create groups` to copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for all above **xcframeworks**.

### Add the Frameworks via CocoaPods

1. Add the frameworks in your **Podfile**, replace `TargetName` with your real target name.

   ```sh
   target 'HelloWorld' do
      use_frameworks!

   pod 'DynamsoftCaptureVisionRouter','2.0.20'
   pod 'DynamsoftBarcodeReader','10.0.20'
   pod 'DynamsoftCameraEnhancer','4.0.1'
   pod 'DynamsoftUtility','1.0.10'

   end
   ```

2. Execute the pod command to install the frameworks and generate workspace(**[TargetName].xcworkspace**):

   ```sh
   pod install
   ```

### Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> AddPackages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/barcode-reader-spm"

3. Select `barcode-reader-spm` then click **Add Package**

4. Check all the **xcframeworks** and add.

## Build Your First Application

In this section, let's create a **HelloWorld** app for reading barcodes from camera video input.

> Note:  
>  
>- XCode 13.0 is used here in this guide.
>- You can download the complete Objective-C source code from [Objective-C HelloWorld Sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/HelloWorldObjC)
>- You can download the complete Swift source code from [Swift HelloWorld Sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Swift/HelloWorldSwift)
>- DCE is used for camera capture in this guide below. If you use the iOS AVFoundation framework for camera capture, check <a href="https://www.dynamsoft.com/barcode-reader/programming/objectivec-swift/samples/no-camera-enhancer.html" target="_blank">DecodeWithAVCaptureSession</a> on how to add barcode scanning to your app.

### Create a New Project

1. Open Xcode and select create a new project.

2. Select **iOS > App** for your application.

3. Input your product name (DBRHelloworld), interface (StoryBoard) and select the language (Objective-C/Swift).

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

6. If you have a `SceneDelegate` file in your new project, remove it and modify the `AppDelegate` file as follows:

    <div class="sample-code-prefix"></div>
    >- Objective-C
    >- Swift
    >
    >1. 
    ```objc
    #import "AppDelegate.h"
    @interface AppDelegate ()
    @end
    @implementation AppDelegate
    - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
      /**Override point for customization after application launch.*/
      return YES;
    }
    /**If you have methods 'application:configurationForConnectingSceneSession:options:' and 'application:didDiscardSceneSessions:', remove them.*/
    @end
    ```
    2. 
    ```swift
    import UIKit
    @main
    class AppDelegate: UIResponder, UIApplicationDelegate {
           /**Add the following line.*/
           var window: UIWindow?
           func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
              /**Override point for customization after application launch.*/
              return true
           }
           /**If you have methods 'application:configurationForConnectingSceneSession:options:' and 'application:didDiscardSceneSessions:', remove them.*/
    }
    ```

### Include the Frameworks

Add the SDK to your new project. Please go through [Add the SDK](#add-the-sdk) for more details.

### Initialize the License

Dynamsoft barcode reader needs a valid license to work. It is recommended to put the license activation code under the **AppDelegate** file. Before going into the coding part of it all, you must first obtain a trial license if you don't have one. In order to request a trial license, please request one via the [customer portal](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&package=mobile).

1. Implement the protocol `DBRLicenseVerificationListener` through class **AppDelegate**:

    <div class="sample-code-prefix"></div>
    >- Objective-C
    >- Swift
    >
    >1. 
    ```objc
    @interface AppDelegate ()<DBRLicenseVerificationListener>
    ```
    2. 
    ```swift
    class AppDelegate: DBRLicenseVerificationListener
    ```

2. Add the following code to initialize the license in method `application:didFinishLaunchingWithOptions:` and receive the callback message :

    <div class="sample-code-prefix"></div>
    >- Objective-C
    >- Swift
    >
    >1. 
    ```objc
    @implementation AppDelegate
    - (void)onLicenseVerified:(BOOL)isSuccess error:(nullable NSError *)error {
       if (!isSuccess && error != nil) {
          NSLog(@"%@", error);
       }
    }
    - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *) launchOptions {
       /**Override point for customization after application launch.*/
       [DSLicenseManager initLicense:@"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" verificationDelegate:self];
       return YES;
    }
    ```
    2. 
    ```swift
    class AppDelegate: UIResponder, UIApplicationDelegate, LicenseVerificationListener {
       func onLicenseVerified(_ isSuccess: Bool, error: Error?) {
              if !isSuccess {
                 if let error = error {
                        print("\(error.localizedDescription)")
                 }
              }
       }
       func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
              /**Override point for customization after application launch.*/
              LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", verificationDelegate: self)
              return true
       }
    }
    ```

   >Note:  
   >  
   >- Network connection is required for the license to work.
   >- The license string here will grant you a time-limited trial license.
   >- If the license has expired, you can go to the <a href="https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=ios" target="_blank">Customer Portal</a> to request for an extension.
   >- If you download the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?product=dbr&utm_source=guide&package=ios" target="_blank">Installation Package</a>, it comes with a 30-day trial license.

### Configure the Camera to Get Video Streaming

1. Import the headers in the `ViewController` file.

    <div class="sample-code-prefix"></div>
    >- Objective-C
    >- Swift
    >
    >1. 
    ```objc
    #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
    #import <DynamsoftCore/DynamsoftCore.h>
    #import <DynamsoftBarcodeReader/DynamsoftBarcodeReader.h>
    #import <DynamsoftCaptureVisionRouter/DynamsoftCaptureVisionRouter.h>
    ```
    2. 
    ```swift
    import DynamsoftCameraEnhancer
    import DynamsoftCaptureVisionRouter
    import DynamsoftBarcodeReader
    import DynamsoftCore
    ```

2. Declare `DynamsoftCameraEnhancer` and `DCECameraView`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   /*Initialize DynamsoftCameraEnhancer and DCECameraView*/
   @property (nonatomic, strong) DSCameraView *cameraView;
   @property (nonatomic, strong) DSCameraEnhancer *dce;
   ```
   2. 
   ```swift
   /*Initialize DynamsoftCameraEnhancer and DCECameraView*/
   var cameraView:CameraView!
   let dce = CameraEnhancer()
   ```

3. Initialize `DynamsoftCameraEnhancer` and `DCECameraView` and add configurations for DynamsoftCameraEnhancer.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)viewDidLoad {
      [super viewDidLoad];
      /** Add configurationDCE in viewDidLoad. */
      [self setUpCamera];
   }
   /**Create method configurationDCE to configure the Camera Enhancer.*/
   - (void)setUpCamera {
      self.cameraView = [[DSCameraView alloc] initWithFrame:self.view.bounds];
      self.cameraView.autoresizingMask = UIViewAutoresizingFlexibleWidth | UIViewAutoresizingFlexibleHeight;
      [self.view insertSubview:self.cameraView atIndex:0];
      self.dce = [[DSCameraEnhancer alloc] init];
      self.dce.cameraView = self.cameraView;
   }
   ```
   2. 
   ```swift
   override func viewDidLoad() {
      super.viewDidLoad()
      /**Add configurationDCE in viewDidLoad.*/
      setUpCamera()
   }
   /**Create method configurationDCE to configure the Camera Enhancer.*/
   func setUpCamera() {
      cameraView = .init(frame: view.bounds)
      cameraView.autoresizingMask = [.flexibleWidth, .flexibleHeight]
      view.insertSubview(cameraView, at: 0)
      dce.cameraView = cameraView
   }
   ```

### Configure the Barcode Decoding and Receive the Results

1. Initialize the `CaptureVisionRouter` and bind with the `CameraEnhancer` instance.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @property (nonatomic, strong) DSCaptureVisionRouter *cvr;
   - (void)setUpDCV {
      self.cvr = [[DSCaptureVisionRouter alloc] init];
      NSError *error;
      [self.cvr setInput:self.dce error:&error];
      [self.cvr addResultReceiver:self];
   }
   ```
   2. 
   ```swift
   let cvr = CaptureVisionRouter()
   func setUpDCV() {
      try! cvr.setInput(dce)
      cvr.addResultReceiver(self)
   }
   ```

2. Add result receiver and implement `onDecodedBarcodesReceived` to receive the barcode decoding results.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @interface ViewController () <DSCapturedResultReceiver>
   ...
   - (void)setUpDCV {
      ...
      [self.cvr addResultReceiver:self];
   }
   - (void)onDecodedBarcodesReceived:(DSDecodedBarcodesResult *)result {
      if (result.items.count > 0) {
             dispatch_async(dispatch_get_main_queue(), ^{
                [self.cvr stopCapturing];
             });
             NSString *message;
             for (DSBarcodeResultItem *item in result.items) {
                message = [NSString stringWithFormat:@"\nFormat: %@\nText: %@\n", item.formatString, item.text];
             }
             [self showResult:@"Results" message:message completion:^{
                [self.cvr startCapturing:DSPresetTemplateReadBarcodes completionHandler:nil];
             }];
      }
   }
   - (void)showResult:(NSString *)title message:(NSString *)message completion:(void (^)(void))completion {
      dispatch_async(dispatch_get_main_queue(), ^{
             UIAlertController *alert = [UIAlertController alertControllerWithTitle:title message:message preferredStyle:UIAlertControllerStyleAlert];
             [alert addAction:[UIAlertAction actionWithTitle:@"OK" style:UIAlertActionStyleDefault handler:^(UIAlertAction * _Nonnull action) {
                completion();
             }]];
             [self presentViewController:alert animated:YES completion:nil];
      });
   }
   ```
   2. 
   ```swift
   class ViewController: UIViewController, CapturedResultReceiver {
      ...
      func setUpDCV() {
         ...
         cvr.addResultReceiver(self)
      }
      func onDecodedBarcodesReceived(_ result: DecodedBarcodesResult) {
             if let items = result.items, items.count > 0 {
                DispatchQueue.main.async {
                       self.cvr.stopCapturing()
                }
                var message = ""
                for item in items {
                       message = String(format:"\nFormat: %@\nText: %@\n", item.formatString, item.text)
                }
                showResult("Results", message) {
                       self.cvr.startCapturing(PresetTemplate.readBarcodes.rawValue)
                }
             }
      }
      private func showResult(_ title: String, _ message: String, completion: @escaping () -> Void) {
             DispatchQueue.main.async {
                let alert = UIAlertController(title: title, message: message, preferredStyle: .alert)
                alert.addAction(UIAlertAction(title: "OK", style: .default, handler: { _ in completion() }))
                self.present(alert, animated: true, completion: nil)
             }
      }
   }
   ```

### Configure the viewDidLoad, viewWillAppear, viewWillDisappear

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)viewDidLoad {
      [super viewDidLoad];
      /**Do any additional setup after loading the view.*/
      [self setUpCamera];
      [self setUpDCV];
   }
   - (void)viewWillAppear:(BOOL)animated {
      [self.dce open];
      [self.cvr startCapturing:DSPresetTemplateReadBarcodes completionHandler:^(BOOL isSuccess, NSError * _Nullable error) {
             NSAssert((error == nil), error.description);
      }];
      [super viewWillAppear:animated];
   }
   - (void)viewWillDisappear:(BOOL)animated {
      [self.dce close];
      [self.cvr stopCapturing];
      [super viewWillDisappear:animated];
   }
   ```
   2. 
   ```swift
   override func viewDidLoad() {
      super.viewDidLoad()
      /**Do any additional setup after loading the view.*/
      setUpCamera()
      setUpDCV()
   }
   override func viewWillAppear(_ animated: Bool) {
      dce.open()
      cvr.startCapturing(PresetTemplate.readBarcodes.rawValue) { isSuccess, error in
             if (!isSuccess) {
                if let error = error {
                       print("\(error)")
                }
             }
      }
      super.viewWillAppear(animated)
   }
   override func viewWillDisappear(_ animated: Bool) {
      dce.close()
      cvr.stopCapturing()
      super.viewWillDisappear(animated)
   }
   ```

### Configure Camera Permissions

Add the following lines to the file `info.plist` to request camera permission:

```xml
<dict>
  ...
  <key>NSCameraUsageDescription</key>
  <string>HelloWorld Sample needs to access your camera.</string>
  ...
</dict>
```

### Run the Project

1. Select the device that you want to run your app on.
2. Run the project, then your app will be installed on your device.

You can download the complete source code here:

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/HelloWorldObjC" target="_blank">Objective-C source code</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Swift/HelloWorldSwift" target="_blank">Swift source code</a>

## Next Steps

From this page, you have learned how to create a simple video barcode decoding app. In the next steps, the following pages will help you on adding configurations to enhance your barcode reader.

### Explore Features

If you want to explore the many features of the SDK and learn how to use them to best process the images you read in your application, read the articles in [Explore Features](user-guide/explore-features/index.md).

### Check Use Cases

If you want to check how the SDK works in popular use cases, read the articles in [Use Cases](user-guide/use-cases/index.md).

### Optimize Performance

If you have successfully integrated the SDK in your application but would like to get the best performance possible, read how to do this in [Optimize Performance](quick-performance-settings.md).

### Using AVFoundation with DBR

If you use the iOS AVFoundation framework, <a href="https://www.dynamsoft.com/barcode-reader/programming/objectivec-swift/samples/no-camera-enhancer.html" target="_blank">DecodeWithAVCaptureSession</a> will guide you on how to add barcode scanning to your app.

### Other platforms

- <a target="_blank" href="https://www.dynamsoft.com/barcode-reader/docs/mobile/programming/android/?ver=latest">Getting Started with Android</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/mobile/programming/react-native/?ver=latest&&product=dbr">Getting Started with React Native</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/mobile/programming/flutter/?ver=latest&&product=dbr">Getting Started with Flutter</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/mobile/programming/xamarin/?ver=latest&&product=dbr">Getting Started with Xamarin.Forms</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/mobile/programming/cordova/?ver=latest&&product=dbr">Getting Started with Cordova</a>
