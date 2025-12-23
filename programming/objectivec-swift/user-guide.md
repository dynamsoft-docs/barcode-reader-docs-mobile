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


# Getting Started with iOS

## Requirements

- Supported OS: **iOS 9** or higher (**iOS 11** and higher recommended).
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 7.1 and above (Xcode 13.0+ recommended).

## Add the SDK

The Dynamsoft Barcode Reader (DBR) iOS SDK comes with two modules:

- **DynamsoftBarcodeReader.framework** or **DynamsoftBarcodeReader.xcframework**: Main module. Provides APIs to easily scan 1D and 2D barcodes from image files and camera video.

   >Note:
   >
   >Starting from v8.8 of DBR, the SDK also offers **xcframeworks** for iOS development.

- **DynamsoftCameraEnhancer.framework** or **DynamsoftCameraEnhancer.xcframework** (Optional): <a href="https://www.dynamsoft.com/camera-enhancer/docs/mobile/programming/ios/?ver=2.3.21&&cVer=true" target="_blank"> Dynamsoft Camera Enhancer (DCE) module</a> for getting video frames from mobile cameras. Provides APIs for camera control, camera preview, and other advanced features.
   >Note:
   >
   >**DCE is optional.** If you want to use iOS AVFoundation framework to control camera, preview video, and read barcodes in the callback function that outputs a video frame, please refer to [DecodeWithAVCaptureSession sample]({{ site.oc }}samples/no-camera-enhancer.html).

There are three ways to add the SDK into your project - **Manually**, via **CocoaPods**, or via **Swift Package Manager**.

### Add the Frameworks Manually

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Dynamsoft Website</a>. After unzipping, you can find the following two **frameworks** under the **DynamsoftBarcodeReader\Frameworks** directory:
   - **DynamsoftBarcodeReader.framework**
   - **DynamsoftCameraEnhancer.framework** (Optional)
      >Note:
      >
      >If you want to use iOS AVFoundation framework or your own sdk to control camera, please ignore **DynamsoftCameraEnhancer.framework** in the following steps.

2. Drag and drop the above two **frameworks** into your Xcode project. Make sure to check `Copy items if needed` and `Create groups` to copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for **DynamsoftBarcodeReader** and **DynamsoftCameraEnhancer**.

### Add the Frameworks via CocoaPods

1. Add the frameworks in your **Podfile**, replace `TargetName` with your real target name.

   ```sh
   target 'TargetName' do
      use_frameworks!

   pod 'DynamsoftBarcodeReader','9.6.60'
   
   # Remove the following line if you want to use iOS AVFoundation framework or your own sdk to control camera.   
   pod 'DynamsoftCameraEnhancer','2.3.21'

   end
   ```

2. Execute the pod command to install the frameworks and generate workspace(**[TargetName].xcworkspace**):

   ```sh
   pod install
   ```

### Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> AddPackages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/barcode-reader-spm" and "https://github.com/Dynamsoft/camera-enhancer-spm"

3. Select `barcode-reader-spm` and `camera-enhancer-spm` then click **Add Package** to add the frameworks.

## Build Your First Application

In this section, let's create a **HelloWorld** app for reading barcodes from camera video input.

> Note:  
>  
>- XCode 13.0 is used here in this guide.
>- You can download the complete Objective-C source code from [Objective-C HelloWorld Sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.40/ios/Objective-C/HelloWorldObjC)
>- You can download the complete Swift source code from [Swift HelloWorld Sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.40/ios/Swift/HelloWorldSwift)
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
    @interface AppDelegate ()
    @end
    @implementation AppDelegate
    - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
      // Override point for customization after application launch.
      return YES;
    }
    // If you have methods 'application:configurationForConnectingSceneSession:options:' and 'application:didDiscardSceneSessions:', remove them.
    @end
    ```
    2. 
    ```swift
    import UIKit
    @main
    class AppDelegate: UIResponder, UIApplicationDelegate {
           // Add the following line
           var window: UIWindow?
           func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
              // Override point for customization after application launch.
              return true
           }
           // If you have methods 'application:configurationForConnectingSceneSession:options:' and 'application:didDiscardSceneSessions:', remove them.
    }
    ```

### Include the Frameworks

Add the SDK to your new project. Please go through [Add the SDK](#add-the-sdk) for more details.

### Initialize the License

Dynamsoft barcode reader needs a valid license to work. It is recommended to put the license activation code under the **AppDelegate** file.

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
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions 
   {
      // Initialize license for Dynamsoft Barcode Reader.
      // The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" is a time-limited public trial license. Note that network connection is required for this license to work.
      [DynamsoftBarcodeReader initLicense:@"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" verificationDelegate:self];
      return YES;
   }
   - (void)DBRLicenseVerificationCallback:(bool)isSuccess error:(NSError *)error
   {
      // Add your code to handle license callback message.
   }
    ```
    2. 
    ```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool
   {
      /* Initialize license for Dynamsoft Barcode Reader.*/
      /* The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" is a time-limited public trial license. Note that network connection is required for this license to work. */
      DynamsoftBarcodeReader.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", verificationDelegate: self)
      return true
   }
   func dbrLicenseVerificationCallback(_ isSuccess: Bool, error: Error?)
   {
      // Add your code to handle license callback message.
   }
    ```

   >Note:  
   >  
   >- Network connection is required for the license to work.
   >- The license string here will grant you a time-limited trial license.
   >- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=ios){:target="_blank"} link.
   >- If you download the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Installation Package</a>, it comes with a 30-day trial license by default.

### Configure the Camera to Get Video Streaming

1. Import the headers in the `ViewController` file.

    <div class="sample-code-prefix"></div>
    >- Objective-C
    >- Swift
    >
    >1. 
    ```objc
    #import <DynamsoftBarcodeReader/DynamsoftBarcodeReader.h>
    #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
    ```
    2. 
    ```swift
    import DynamsoftBarcodeReader
    import DynamsoftCameraEnhancer
    ```

2. Declare `DynamsoftCameraEnhancer` and `DCECameraView`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   /*Initialize DynamsoftCameraEnhancer and DCECameraView*/
   @property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
   @property(nonatomic, strong) DCECameraView *dceView;
   ```
   2. 
   ```swift
   /*Initialize DynamsoftCameraEnhancer and DCECameraView*/
   var dce:DynamsoftCameraEnhancer!
   var dceView:DCECameraView!
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
      [self configurationDCE];
   }
   /*Create method configurationDCE to configure the Camera Enhancer.*/
   - (void)configurationDCE{
      _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
      [self.view.addSubView:_dceView];
      /*Display overlays on the decoded barcodes*/
      [_dceView setOverlayVisible:true];
      _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
      [_dce open];
   }
   ```
   2. 
   ```swift
   override func viewDidLoad() {
      super.viewDidLoad()
      /** Add configurationDCE in viewDidLoad. */
      configurationDCE()
   }
   /*Create method configurationDCE to configure the Camera Enhancer.*/
   func configurationDCE() {
      dceView = DCECameraView.init(frame: self.view.bounds)
      self.view.addSubview(dceView)
      /*Display overlays on the decoded barcodes*/
      dceView.overlayVisible = true
      dce = DynamsoftCameraEnhancer.init(view: dceView)
      dce.open()
   }
   ```

### Configure the Barcode Reader and Start Decoding

1. Still in the `ViewController` file, declare and create the instance of `barcodeReader`:

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @property(nonatomic, strong) DynamsoftBarcodeReader *barcodeReader;
   - (void)viewDidLoad {
      [super viewDidLoad];
      [self configurationDBR];
   }
   - (void)configurationDBR {
      /* Create the instance */
      _barcodeReader = [[DynamsoftBarcodeReader alloc] init];
      /* You can add your barcode reader configurations here. */
   }
   ```
   2. 
   ```swift
   var barcodeReader:DynamsoftBarcodeReader! = nil
   override func viewDidLoad() {
      super.viewDidLoad()
      configurationDBR()
   }
   func configurationDBR(){
      /* Create the instance */
      barcodeReader = DynamsoftBarcodeReader.init()
      /* You can add your barcode reader configurations here. */
   }
   ```

2. After both of the barcode reader instance and the camera enhancer instance are created, let's bind the camera enhancer instance to the barcode reader so that the barcode reader can get video streaming for barcode decoding. Add the following to the `configurationDCE` method:

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)configurationDCE{
      // Bind the Camera Enhancer instance to the Barcode Reader instance.
      // The _dce is the instance of the Dynamsoft Camera Enhancer.
      // The Barcode Reader will use this instance to take control of the camera and acquire frames from the camera to start the barcode decoding process.
      [_barcodeReader setCameraEnhancer:_dce];
      // Start Scanning controls the process of video barcode decoding
      [_barcodeReader startScanning];
   }
   ```
   2. 
   ```swift
   /*Deploy the camera with Dynamsoft Camera Enhancer.*/
   func configurationDCE() {
      /*Bind the Camera Enhancer instance to the Barcode Reader instance.
      The _dce is the instance of the Dynamsoft Camera Enhancer.
      The Barcode Reader will use this instance to take control of the camera and acquire frames from the camera to start the barcode decoding process.*/
      barcodeReader.setCameraEnhancer(dce)
      /* Start Scanning controls the process of video barcode decoding. */
      barcodeReader.startScanning()
   }
   ```

3. Once you have start the video barcode decoding thread, we implement the protocol `DBRTextResultLisener` through class `ViewController` to receive the barcode results.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @interface ViewController ()<DBRTextResultListener>
   ```
   2. 
   ```swift
   class ViewController: DBRTextResultListener
   ```

   Then handle received barcode results in `textResultCallback` function of the class `ViewController`:

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)textResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iTextResult *> *)results{
      if (results.count > 0) {
             NSString *title = @"Results";
             NSString *msgText = @"";
             NSString *msg = @"Please visit: https://www.dynamsoft.com/customer/license/trialLicense?";
             for (NSInteger i = 0; i< [results count]; i++) {
                if (results[i].exception != nil && [results[i].exception containsString:msg]) {
                   msgText = [msg stringByAppendingString:@"product=dbr&utm_source=installer&package=ios to request for 30 days extension."];
                   title = @"Exception";
                   break;
                }
                if (results[i].barcodeFormat_2 != 0) {
                   msgText = [msgText stringByAppendingString:[NSString stringWithFormat:@"\nFormat: %@\nText: %@\n", results[i].barcodeFormatString_2, results[i].barcodeText]];
                }else{
                   msgText = [msgText stringByAppendingString:[NSString stringWithFormat:@"\nFormat: %@\nText: %@\n", results[i].barcodeFormatString, results[i].barcodeText]];
                }
             }
             [self showResult:title msg:msgText acTitle:@"OK" completion:^{}];
      }else{
             return;
      }
   }
   ```
   2. 
   ```swift
   func textResultCallback(_ frameId: Int, ImageData: iImageData, results: [iTextResult]?) {
      if results!.count > 0 {
             var msgText:String = ""
             var title:String = "Results"
             for item in results! {
                if item.barcodeFormat_2.rawValue != 0 {
                   msgText = msgText + String(format:"\nFormat: %@\nText: %@\n", item.barcodeFormatString_2!, item.barcodeText ?? "noResuslt")
                }else{
                   msgText = msgText + String(format:"\nFormat: %@\nText: %@\n", item.barcodeFormatString!,item.barcodeText ?? "noResuslt")
                }
             }
             showResult(title, msgText, "OK") {
             }
      }else{
             return
      }
   }
   ```

4. Bind the `TextResultListener` object to the barcode reader.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)configurationDCE{
      [_barcodeReader setCameraEnhancer:_dce];
      // Make this setting to get the result. The result will be an object that contains text results and other barcode information.
      [_barcodeReader setDBRTextResultListener:self];
      [_barcodeReader startScanning];
   }
   ```
   2. 
   ```swift
   func configurationDCE() {
      barcodeReader.setCameraEnhancer(dce)
      /* Make this setting to get the result. The result will be an object that contains text result and other barcode information. */
      barcodeReader.setDBRTextResultListener(self)
      barcodeReader.startScanning()
   }
   ```

5. Lastly, add the `showText` method to display the barcode results on the UI

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)showResult:(NSString *)title msg:(NSString *)msg acTitle:(NSString *)acTitle completion:(void (^)(void))completion {
          dispatch_async(dispatch_get_main_queue(), ^{
             UIAlertController *alert = [UIAlertController alertControllerWithTitle:title message:msg preferredStyle:UIAlertControllerStyleAlert];
             [alert addAction:[UIAlertAction actionWithTitle:acTitle style:UIAlertActionStyleDefault handler:^(UIAlertAction * action) {
                completion();
             }]];
             [self presentViewController:alert animated:YES completion:nil];
          });
   }
   ```
   2. 
   ```swift
   private func showResult(_ title: String, _ msg: String, _ acTitle: String, completion: @escaping () -> Void) {
      DispatchQueue.main.async {
             let alert = UIAlertController(title: title, message: msg, preferredStyle: .alert)
             alert.addAction(UIAlertAction(title: acTitle, style: .default, handler: { _ in completion() }))
             self.present(alert, animated: true, completion: nil)
      }
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

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.40/ios/Objective-C/HelloWorldObjC" target="_blank">Objective-C source code</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.40/ios/Swift/HelloWorldSwift" target="_blank">Swift source code</a>

## Next Steps

From this page, you have learned how to create a simple video barcode decoding app. In the next steps, the following pages will help you on adding configurations to enhance your barcode reader.

### Explore Features

If you want to explore the many features of the SDK and learn how to use them to best process the images you read in your application, read the articles in [Explore Features](user-guide/explore-features/index.html).

### Check Use Cases

If you want to check how the SDK works in popular use cases, read the articles in [Use Cases](user-guide/use-cases/index.html).

### Optimize Performance

If you have successfully integrated the SDK in your application but would like to get the best performance possible, read how to do this in [Optimize Performance](quick-performance-settings.html).

### Using AVFoundation with DBR

If you use the iOS AVFoundation framework, [DecodeWithAVCaptureSession sample]({{ site.oc }}samples/no-camera-enhancer.html) will guide you on how to add barcode scanning to your app.

### Other platforms

- <a target="_blank" href="https://www.dynamsoft.com/barcode-reader/docs/mobile/programming/android/?ver=latest">Getting Started with Android</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/react-native/?ver=latest">Getting Started with React Native</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/flutter/?ver=latest">Getting Started with Flutter</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/xamarin/?ver=latest">Getting Started with Xamarin.Forms</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/cordova/?ver=latest">Getting Started with Cordova</a>