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
---

# Build Your App with Foundational APIs

## Requirements

- Supported OS: **iOS 11** or higher (**iOS 13** and higher recommended).
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 13 and above (Xcode 14.1+ recommended).

## Build Your First Application

In this section, let's create a **HelloWorld** app for reading barcodes from camera video input.

<div class="blockquote-note"></div>
>  
>- XCode 14.2 is used here in this guide.
>- You can download the complete Swift source code from [DecodeWithCameraEnhancer Sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeWithCameraEnhancer){:target="_blank"}
>- DCE is used for camera capture in this guide below. If you use the iOS AVFoundation framework for camera capture, check [DecodeWithAVCaptureSession sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeWithAVCaptureSession){:target="_blank"} on how to add barcode scanning to your app.

### Step 1: Create a New Project

1. Open Xcode and select create a new project.

2. Select **iOS > App** for your application.

3. Input your product name (DBRHelloworld), interface (StoryBoard) and select the language (Objective-C/Swift).

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

### Step 2: Add the SDK

There are three ways to add the SDK into your project - **Manually**, via **CocoaPods**, or via **Swift Package Manager**.

#### Option 1: Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> AddPackages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/barcode-reader-spm"

3. Select `barcode-reader-spm`, choose `Exact version`, enter **11.2.5000**, then click **Add Package**.

4. Check all the **xcframeworks** and add.

#### Option 2: Add the Frameworks via CocoaPods

1. Add the frameworks in your **Podfile**, replace `TargetName` with your real target name.

   ```sh
   target 'HelloWorld' do
      use_frameworks!

   pod 'DynamsoftBarcodeReaderBundle','11.2.5000'

   end
   ```

   > Read more about the modules of [DynamsoftBarcodeReaderBundle](api-reference/index.html)

2. Execute the pod command to install the frameworks and generate workspace(**[TargetName].xcworkspace**):

   ```sh
   pod install
   ```

#### Option 3: Add Local xcframeworks files

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Dynamsoft Website</a>. After unzipping, you can find the following **xcframeworks** under the **Dynamsoft\Frameworks** directory:

- DynamsoftBarcodeReaderBundle.xcframework
- DynamsoftCaptureVisionBundle.xcframework

2. Drag and drop the **xcframeworks** into your Xcode project. Make sure to check `Copy items if needed` and `Create groups` to copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for all above **xcframeworks**.

### Step 3: Initialize the License

Dynamsoft Barcode Reader needs a valid license to work.

1. Implement the protocol `LicenseVerificationListener` through class **ViewController**:

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   #import "ViewController.h"
   #import <DynamsoftCaptureVisionBundle/DynamsoftCaptureVisionBundle.h>
   @interface ViewController ()<DSLicenseVerificationListener>
   @end
   ```
   2. 
   ```swift
   import DynamsoftCaptureVisionBundle
   class ViewController: UIViewController, LicenseVerificationListener
   ```

2. Add the following code to initialize the license in method `application:didFinishLaunchingWithOptions:` and receive the callback message :

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @implementation ViewController
   - (void)setLicense {
      [DSLicenseManager initLicense:@"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" verificationDelegate:self];
   }
   - (void)onLicenseVerified:(BOOL)isSuccess error:(nullable NSError *)error {
      if (!isSuccess && error != nil) {
             NSLog(@"error: %@", error);
      }
   }
   @end
   ```
   2. 
   ```swift
   func setLicense() {
      LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", verificationDelegate: self)
   }
   func onLicenseVerified(_ isSuccess: Bool, error: Error?) {
      if !isSuccess {
             if let error = error {
                print("\(error.localizedDescription)")
             }
      }
   }
   ```

   <div class="blockquote-note"></div>
   >  
   >- Network connection is required for the license to work.
   >- The license string here will grant you a time-limited trial license.
   >- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=ios){:target="_blank"} link.
   >- If you download the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Installation Package</a>, it comes with a 30-day trial license by default.

### Step 4: Configure the Camera Enhancer

Initialize `CameraEnhancer` and `CameraView` and add configurations for the `CameraEnhancer`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface ViewController () <DSLicenseVerificationListener>
@property (nonatomic, strong) DSCameraView *cameraView;
@property (nonatomic, strong) DSCameraEnhancer *dce;
@end
...
@implementation ViewController
- (void)setUpCamera {
   self.cameraView = [[DSCameraView alloc] initWithFrame:self.view.bounds];
   self.cameraView.autoresizingMask = UIViewAutoresizingFlexibleWidth | UIViewAutoresizingFlexibleHeight;
   [self.view insertSubview:self.cameraView atIndex:0];
   self.dce = [[DSCameraEnhancer alloc] init];
   self.dce.cameraView = self.cameraView;
}
...
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

### Step 5: Configure the Barcode Decoding Task via CaptureVisionRouter

1. Initialize the `CaptureVisionRouter` and bind with the `CameraEnhancer` instance.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @interface ViewController () <DSLicenseVerificationListener>
   @property (nonatomic, strong) DSCaptureVisionRouter *cvr;
   @end
   ...
   @implementation ViewController
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
   @interface ViewController () <DSLicenseVerificationListener, DSCapturedResultReceiver>
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
   class ViewController: UIViewController, CapturedResultReceiver, LicenseVerificationListener {
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
      private func showResult(_ title: String, _ message: String?, completion: (() -> Void)? = nil) {
             DispatchQueue.main.async {
                let alert = UIAlertController(title: title, message: message, preferredStyle: .alert)
                alert.addAction(UIAlertAction(title: "OK", style: .default, handler: { _ in completion?() }))
                self.present(alert, animated: true, completion: nil)
             }
      }
   }
   ```

### Step 6: Configure viewDidLoad, viewWillAppear, viewWillDisappear

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
   [self setLicense];
   [self setUpCamera];
   [self setUpDCV];
}
- (void)viewWillAppear:(BOOL)animated {
   [self.dce open];
   [self.cvr startCapturing:DSPresetTemplateReadBarcodes completionHandler:^(BOOL isSuccess, NSError * _Nullable error) {
          if (!isSuccess && error != nil) {
             [self showResult:@"Error" message:error.localizedDescription completion:nil];
          }
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
   setLicense()
   setUpCamera()
   setUpDCV()
}
override func viewWillAppear(_ animated: Bool) {
   dce.open()
   // Start capturing when the view will appear. If success, you will receive results in the CapturedResultReceiver. Otherwise you will receive the error message in a dialog.
   cvr.startCapturing(PresetTemplate.readBarcodes.rawValue) { isSuccess, error in
          if (!isSuccess) {
             if let error = error {
                self.showResult("Error", error.localizedDescription)
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

### Step 7: Configure Camera Permissions

Add **Privacy - Camera Usage Description** to the `info.plist` of your project to request camera permission. An easy way to do this is to access your project settings, go to *Info* and then add this Privacy property to the iOS target properties list.

### Step 8: Additional Steps for iOS 12 or Lower Versions

If your iOS version is less than 13, please add the following additional steps:

1. Remove the methods `application:didDiscardSceneSessions:` and `application:configurationForConnectingSceneSession:options:` from your `AppDelegate` file.
2. Remove the `SceneDelegate.Swift` file (`SceneDelegate.h` & `SceneDelegate.m` for Objective-C).
3. Remove the `Application Scene Manifest` from your info.plist file.
4. Declare the window in your `AppDelegate.Swift` file (`AppDelegate.h` for Objective-C).

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @interface AppDelegate : UIResponder <UIApplicationDelegate>
   @property (strong, nonatomic) UIWindow *window;
   @end
   ```
   2. 
   ```swift
   import UIKit
   @main
   class AppDelegate: UIResponder, UIApplicationDelegate {
      var window: UIWindow?
   }
   ```

### Step 9: (Optional) Manually Releasing Deep Learning Models

Starting from v11.2.1000, Dynamsoft Barcode Reader integrates deep learning models to enhance decoding ability. Once initialized, these models remain cached in memory until they are explicitly released. If the decoding task has finished, call `clearDLModelBuffers` to free the associated memory.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)dealloc {
   [DSCaptureVisionRouter clearDLModelBuffers];
}
```
2. 
```swift
deinit
{
   CaptureVisionRouter.clearDLModelBuffers()
}
```

### Step 10: Run the Project

1. Select the device that you want to run your app on. **Please note that you will require a physical device to run the application on.** If you run the app on a simulator, you will experience some errors at runtime as a physical camera component is required. *If you have an M1 Macbook (or a later model) you can run the app on your Macbook directly as it has the same architecture as your iPhone/iPad.*
2. Run the project, then your app will be installed on your device.

You can download the complete source code here:

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeWithCameraEnhancer" target="_blank">Swift source code</a>

## Next Steps

From this page, you have learned how to create a simple video barcode decoding app. In the next steps, the following pages will help you on adding configurations to enhance your barcode reader.

### Explore Features

If you want to explore the many features of the SDK and learn how to use them to best process the images you read in your application, read the articles in [Explore Features](user-guide/explore-features/index.html).

### Check Use Cases

If you want to check how the SDK works in popular use cases, read the articles in [Use Cases](user-guide/use-cases/index.html).

### Using AVFoundation with DBR

If you use the iOS AVFoundation framework to activate the camera (instead of the Dynamsoft Camera Enhancer), [DecodeWithAVCaptureSession sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeWithAVCaptureSession){:target="_blank"} will guide you on how to add barcode scanning to your app.

### Other platforms

- [Getting Started with Android](https://www.dynamsoft.com/barcode-reader/docs/mobile/programming/android/?ver=latest){:target="_blank"}
- [Getting Started with MAUI](https://www.dynamsoft.com/capture-vision/docs/programming/maui/?ver=latest){:target="_blank"}
- [Getting Started with React Native](https://www.dynamsoft.com/capture-vision/docs/programming/react-native/?ver=latest){:target="_blank"}
- [Getting Started with Flutter](https://www.dynamsoft.com/capture-vision/docs/programming/flutter/?ver=latest){:target="_blank"}
- [Getting Started with C++]({{ site.dbr_cpp }}){:target="_blank"}
- [Getting Started with Python]({{ site.dbr_python }}){:target="_blank"}
- [Getting Started with Java]({{ site.dbr_java }}){:target="_blank"}
- [Getting Started with .NET]({{ site.dbr_dotnet }}){:target="_blank"}
- [Getting Started with JS]({{ site.dbr_js }}){:target="_blank"}
