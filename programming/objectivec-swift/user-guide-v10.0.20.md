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
permalink: /programming/objectivec-swift/user-guide-v10.0.20.html
---


# Getting Started with iOS

## Requirements

- Supported OS: **iOS 11** or higher (**iOS 13** and higher recommended).
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 13 and above (Xcode 14.1+ recommended).

## Add the SDK

There are three ways to add the SDK into your project - **Manually**, via **CocoaPods**, or via **Swift Package Manager**.

### Add the Frameworks Manually

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Dynamsoft Website</a>. After unzipping, you can find the following **xcframeworks** under the **Dynamsoft\Frameworks** directory:

   | File | Description | Mandatory/Optional |
   |:-----|:------------|:-------------------|
   | `DynamsoftBarcodeReader.xcframework` | The Dynamsoft Barcode Reader module recognizes and decodes multiple barcode formats such as QR codes, Code 39, Code 128, and Data Matrix, among many others. | Mandatory |
   | `DynamsoftCore.xcframework`  | The Dynamsoft Core module lays the foundation for Dynamsoft SDKs based on the DCV (Dynamsoft Capture Vision) architecture. It encapsulates the basic classes, interfaces, and enumerations shared by these SDKs. | Mandatory |
   | `DynamsoftCaptureVisionRouter.xcframework` | The Dynamsoft Capture Vision Router module is the cornerstone of the Dynamsoft Capture Vision (DCV) architecture. It focuses on coordinating batch image processing and provides APIs for setting up image sources and result receivers, configuring workflows with parameters, and controlling processes. | Mandatory |
   | `DynamsoftImageProcessing.xcframework` | The Dynamsoft Image Processing module facilitates digital image processing and supports operations for other modules, including the Barcode Reader, Label Recognizer, and Document Normalizer. | Mandatory |
   | `DynamsoftLicense.xcframework` | The Dynamsoft License module manages the licensing aspects of Dynamsoft SDKs based on the DCV (Dynamsoft Capture Vision) architecture. | Mandatory |
   | `DynamsoftCameraEnhancer.xcframework` | The Dynamsoft Camera Enhancer module controls the camera, transforming it into an image source for the DCV (Dynamsoft Capture Vision) architecture through ISA implementation. It also enhances image quality during acquisition and provides basic viewers for user interaction. | Optional |
   | `DynamsoftUtility.xcframework` | The Dynamsoft Utility module defines auxiliary classes, including the ImageManager, and implementations of the CRF (Captured Result Filter) and ISA (Image Source Adapter) . These are shared by all Dynamsoft SDKs based on the DCV (Dynamsoft Capture Vision) architecture. | Optional |

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
   pod 'DynamsoftUtility','1.0.20'

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
>- XCode 14.2 is used here in this guide.
>- You can download the complete Objective-C source code from [HelloWorld/DecodeWithCameraEnhancerObjc Sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.0.20/ios/HelloWorld/DecodeWithCameraEnhancerObjc)
>- You can download the complete Swift source code from [HelloWorld/DecodeWithCameraEnhancer Sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.0.20/ios/HelloWorld/DecodeWithCameraEnhancer)
>- DCE is used for camera capture in this guide below. If you use the iOS AVFoundation framework for camera capture, check [DecodeWithAVCaptureSession sample]({{ site.oc }}samples/no-camera-enhancer.html) on how to add barcode scanning to your app.

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
   #import <DynamsoftLicense/DynamsoftLicense.h>
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

Add the SDK to your new project. There are several ways to do this, all of which are explained in [this section](#add-the-sdk) for more details.

### Initialize the License

Dynamsoft Barcode Reader needs a valid license to work. It is recommended to put the license activation code in the **AppDelegate** file.

1. Implement the protocol `LicenseVerificationListener` through class **AppDelegate**:

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   #import <DynamsoftLicense/DynamsoftLicense.h>
   @interface AppDelegate ()<LicenseVerificationListener>
   ```
   2. 
   ```swift
   import DynamsoftLicense
   @main
   class AppDelegate: LicenseVerificationListener
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
   >- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=ios){:target="_blank"} link.
   >- If you download the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Installation Package</a>, it comes with a 30-day trial license by default.

### Configure the Camera Enhancer

1. Import all the headers that you will need in the `ViewController` file.

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

2. Initialize `DynamsoftCameraEnhancer` and `CameraView` and add configurations for DynamsoftCameraEnhancer.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @property (nonatomic, strong) DSCameraView *cameraView;
   @property (nonatomic, strong) DSCameraEnhancer *dce;
   ...
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
   var cameraView:CameraView!
   let dce = CameraEnhancer()
   ...
   func setUpCamera() {
      cameraView = .init(frame: view.bounds)
      cameraView.autoresizingMask = [.flexibleWidth, .flexibleHeight]
      view.insertSubview(cameraView, at: 0)
      dce.cameraView = cameraView
   }
   ```

### Configure the Barcode Decoding Task via CaptureVisionRouter

1. Initialize the `CaptureVisionRouter` and bind with the `CameraEnhancer` instance.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @property (nonatomic, strong) DSCaptureVisionRouter *cvr;
   ...
   - (void)setUpDCV {
      self.cvr = [[DSCaptureVisionRouter alloc] init];
      NSError *error;
      [self.cvr setInput:self.dce error:&error];
      if (error != nil) {
             NSLog(@"error: %@", error);
      }
   }
   ```
   2. 
   ```swift
   let cvr = CaptureVisionRouter()
   ...
   func setUpDCV() {
      try! cvr.setInput(dce)
   }
   ```

2. Implement `onDecodedBarcodesReceived` to receive the barcode decoding results and add this result receiver to the current CVR object.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   /**Add CapturedResultReceiver to your ViewController.*/
   @interface ViewController () <DSCapturedResultReceiver>
   ...
   - (void)setUpDCV {
      ...
      [self.cvr addResultReceiver:self];
   }
   /**Implement onDecodedBarcodesReceived method of CaptureResultReceiver to receive the barcode decoding results.*/
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
   /**Add CapturedResultReceiver to your ViewController.*/
   class ViewController: UIViewController, CapturedResultReceiver {
      ...
      func setUpDCV() {
             ...
             /**Add your CaptureResultReceiver to the CaptureVisionRouter.*/
             cvr.addResultReceiver(self)
      }
      /**Implement onDecodedBarcodesReceived method of CaptureResultReceiver to receive the barcode decoding results.*/
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

### Configure viewDidLoad, viewWillAppear, viewWillDisappear

Now that all of the main functions are defined and configured, let's finish things off on the code side of things by completing the `viewDidLoad`, `viewWillAppear`, and `viewWillDisappear` functions.

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
   [self.cvr startCapturing:DSPresetTemplateReadBarcodes completionHandler:^(BOOL isSuccess, NSError *_Nullable error) {
          NSAssert((error == nil), error.description);
   }];
   [super viewWillAppear:animated];
}
- (void)viewWillDisappear:(BOOL)animated {
   [self.dce close];
   [self.cvr stopCapturing];
   [super viewWillDisappear:animated];
}
...
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
...
```

### Configure Camera Permissions

Add **Privacy - Camera Usage Description** to the `info.plist` of your project to request camera permission. An easy way to do this is to access your project settings, go to *Info* and then add this Privacy property to the iOS target properties list.

### Run the Project

1. Select the device that you want to run your app on. **Please note that you will require a physical device to run the application on.** If you run the app on a simulator, you will experience some errors at runtime as a physical camera component is required. *If you have an M1 Macbook (or a later model) you can run the app on your Macbook directly as it has the same architecture as your iPhone/iPad.*
2. Run the project, then your app will be installed on your device.

You can download the complete source code here:

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.0.20/ios/HelloWorld/DecodeWithCameraEnhancerObjc" target="_blank">Objective-C source code</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.0.20/ios/HelloWorld/DecodeWithCameraEnhancer" target="_blank">Swift source code</a>

## Next Steps

From this page, you have learned how to create a simple video barcode decoding app. In the next steps, the following pages will help you on adding configurations to enhance your barcode reader.

### Explore Features

If you want to explore the many features of the SDK and learn how to use them to best process the images you read in your application, read the articles in [Explore Features](user-guide/explore-features/index.html).

### Check Use Cases

If you want to check how the SDK works in popular use cases, read the articles in [Use Cases](user-guide/use-cases/index.html).

### Optimize Performance

If you have successfully integrated the SDK in your application but would like to get the best performance possible, read how to do this in [Optimize Performance](user-guide/quick-performance-settings.html).

### Using AVFoundation with DBR

If you use the iOS AVFoundation framework to activate the camera (instead of the Dynamsoft Camera Enhancer), [DecodeWithAVCaptureSession sample]({{ site.oc }}samples/no-camera-enhancer.html) will guide you on how to add barcode scanning to your app.

### Other platforms

- <a target="_blank" href="https://www.dynamsoft.com/barcode-reader/docs/mobile/programming/android/?ver=latest">Getting Started with Android</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/mobile/programming/react-native/?ver=latest&&product=dbr">Getting Started with React Native</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/mobile/programming/flutter/?ver=latest&&product=dbr">Getting Started with Flutter</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/mobile/programming/xamarin/?ver=latest&&product=dbr">Getting Started with Xamarin.Forms</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/mobile/programming/cordova/?ver=latest&&product=dbr">Getting Started with Cordova</a>
