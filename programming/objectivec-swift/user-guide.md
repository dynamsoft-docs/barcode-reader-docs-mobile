---
layout: default-layout
title: Dynamsoft Barcode Reader for Objective-C & Swift - User Guide
description: This is the user guide of Dynamsoft Barcode Reader for iOS SDK.
keywords: user guide, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/objectivec-swift/user-guide.html
---


# Getting Started with iOS

## Requirements

- Supported OS: **iOS 9.0** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 7.1 and above (Xcode 13.0+ recommended).

## Add the SDK

The Dynamsoft Barcode Reader (DBR) iOS SDK comes with two modules:

- **DynamsoftBarcodeReader.framework** or **DynamsoftBarcodeReader.xcframework**: Main module. Provides APIs to easily scan 1D and 2D barcodes from image files and camera video.

   >Note:
   >
   >Starting from v8.8 of DBR, the SDK also offers **xcframeworks** for iOS development.

- **DynamsoftCameraEnhancer.framework** or **DynamsoftCameraEnhancer.xcframework** (Optional): <a href="https://www.dynamsoft.com/camera-enhancer/docs/introduction/" target="_blank"> Dynamsoft Camera Enhancer (DCE) module</a> for getting video frames from mobile cameras. Provides APIs for camera control, camera preview, and other advanced features.
   >Note:
   >
   >**DCE is optional.** If you want to use iOS AVFoundation framework to control camera, preview video, and read barcodes in the callback function that outputs a video frame, please refer to <a href="https://www.dynamsoft.com/barcode-reader/programming/objectivec-swift/samples/no-camera-enhancer.html" target="_blank">DecodeWithAVCaptureSession example</a>.

There are two ways to add the SDK into your project - **Manually** or via **CocoaPods**.

### Add the Frameworks Manually

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">Dynamsoft Website</a>. After unzipping, you can find the following two **frameworks** under the **DynamsoftBarcodeReader\Frameworks** directory:
   - **DynamsoftBarcodeReader.framework**
   - **DynamsoftCameraEnhancer.framework** (Optional)
      >Note:
      >
      >If you want to use iOS AVFoundation framework or your own sdk to control camera, please ignore **DynamsoftCameraEnhancer.framework** in the following steps.

2. Drag and drop the above two **frameworks** into your Xcode project. Make sure to check `Copy items if needed` and `Create groups` to copy the framework into your project’s folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for **DynamsoftBarcodeReader** and **DynamsoftCameraEnhancer**.

### Add the Frameworks via CocoaPods

1. Add the frameworks in your **Podfile**, replace `TargetName` with your real target name.

   ```sh
   target 'TargetName' do
      use_frameworks!

   pod 'DynamsoftBarcodeReader','9.2.10'
   
   # Remove the following line if you want to use iOS AVFoundation framework or your own sdk to control camera.   
   pod 'DynamsoftCameraEnhancer','2.3.0'

   end
   ```

2. Execute the pod command to install the frameworks and generate workspace(**[TargetName].xcworkspace**):

   ```sh
   pod install
   ```

## Build Your First Application

In this section, let's see how to create a **HelloWorld** app for reading barcodes from camera video input.

> Note:  
>  
>- XCode 13.0 is used here in this guide.
>- You can download the complete Objective-C source code from [Ojective-C HelloWorld Sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/HelloWorldObjC)
>- You can download the complete Swift source code from [Swift HelloWorld Sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Swift/HelloWorldSwift)
>- DCE is used for camera capture in this guide below. If you use the iOS AVFoundation framework for camera capture, check <a href="https://www.dynamsoft.com/barcode-reader/programming/objectivec-swift/samples/no-camera-enhancer.html" target="_blank">DecodeWithAVCaptureSession</a> on how to add barcode scanning to your app.

### Create a New Project

1. Open Xcode and select create a new project.

2. Select **iOS > App** for your application.

3. Input your product name (DBRHelloworld), interface (StoryBoard) and language (Objective-C/Swift).

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

### Include the Frameworks

Add the SDK to your new project. Please read [Add the SDK](#add-the-sdk) section for more details.

### Initialize the License

Dynamsoft barcode reader needs a valid license to work. It is recommended to put the license activation code under the **AppDelegate** file.

1. Add DBRLicenseVerificationListener to the **AppDelegate**:

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
    class AppDelegate: DBRLicenseVerificationListener{}
    ```

2. Add the following code to initialize the license in method `application:didFinishLaunchingWithOptions:`:

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
      // The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here is a time-limited public trial license. Note that network connection is required for this license to work.
      // You can also request an extension for your trial license in the customer portal: https://www.dynamsoft.com/customer/license/trialLicense?product=dce&utm_source=installer&package=ios
      [DynamsoftBarcodeReader initLicense:@"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" verificationDelegate:self];
      return YES;
   }
   - (void)DBRLicenseVerificationListener:(bool)isSuccess error:(NSError *)error
   {
   }
    ```
    2. 
    ```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool
   {
      /*Initialize license for Dynamsoft Barcode Reader.*/
      /* The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here is a time-limited public trial license. Note that network connection is required for this license to work.*/
      /* You can also request an extension for your trial license in the customer portal: https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=ios*/
      DynamsoftBarcodeReader.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", verificationDelegate: self)
      return true
   }
   func dbrLicenseVerificationCallback(_ isSuccess: Bool, error: Error?)
   {
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
    #import <DynamsoftBarcodeReader/DynamsoftBarcodeReader.h>
    #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
    ```
    2. 
    ```swift
    import DynamsoftBarcodeReader
    import DynamsoftCameraEnhancer
    ```

2. Create an instance of **DynamsoftCameraEnhancer** for getting video input.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   /*Initialize DynamsoftCameraEnhancer and DCECameraView*/
   @property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
   @property(nonatomic, strong) DCECameraView *dceView;
   - (void)viewDidLoad {
      [super viewDidLoad];
      [self configurationDCE];
   }
   ```
   2. 
   ```swift
   /*Initialize DynamsoftCameraEnhancer and DCECameraView*/
   var dce:DynamsoftCameraEnhancer! = nil
   var dceView:DCECameraView! = nil
   override func viewDidLoad() {
      super.viewDidLoad()
      configurationDCE()
   }
   ```

3. Add configurations for DynamsoftCameraEnhancer.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   /*Configure the Camera Enhancer.*/
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
   /*Configure the Camera Enhancer.*/
   func configurationDCE() {
      dceView = DCECameraView.init(frame: self.view.bounds)
      self.view.addSubview(dceView)
      /*Display overlays on the decoded barcodes*/
      dceView.setOverlayVisible(true)
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

3. Once you have start the video barcode decoding thread, `TextResultCallback` is then implemented when barcode result is detected.

   To acquire the barcode `TextResult` with `TextResultCallback`, please firstly add the `DBRTextResultListener` to the `ViewController`.

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
   class ViewController: DBRTextResultListener{}
   ```

   Then implement the listener in the `ViewController`:

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

4. Bind the TextResultListener to the barcode reader.

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


### Run the Project

1. Select the device that you want to run your app on.
2. Run the project, then your app will be installed on your device.

You can download the complete source code here:

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/HelloWorldObjC" target="_blank">Objective-C source code</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Swift/HelloWorldSwift" target="_blank">Swift source code</a>

## Next Steps

From this page, you have learned how to create a simple video barcode decoding app. In the next steps, the following pages will help you on adding configurations to enhance your barcode reader.

### Advanced Usage

Read [Advanced Usage](advanced-usage.md) to learn how to set barcode format, add expected barcode count and specify a scan region. For more information about the barcode formats, see <a href = "https://www.dynamsoft.com/barcode-types/barcode-types/" target = "_blank">Introduction of Barcode Formats</a>.

### Add UI Settings

If you are using Dynamsoft Camera Enhancer, there are some simple solution for you to add basic UI elements to visualize the barcode decoding result. Read [Add UI Settings](ui-configurations.md) for more information.

### Optimize Performance

If find the barcode decoding performance is not satisfying, please read [Optimize the Performance](quick-performance-settings.md) to see how to make a quick deployment on optimizing the performance.

### Using AVFoundation with DBR

If you use the iOS AVFoundation framework, <a href="https://www.dynamsoft.com/barcode-reader/programming/objectivec-swift/samples/no-camera-enhancer.html" target="_blank">DecodeWithAVCaptureSession</a> will guide you on how to add barcode scanning to your app.

## Known Issues

### "dyld: Library not loaded" error on app initialization

You might run into this error in the app initialization phase - and in order to resolve this, a slight change needs to be done to the build settings of the project. Please make sure that you take the following steps to avoid this error:

- When adding the Barcode Reader framework in step 2 of the above instructions, make sure to tick off the **Copy items if needed** and **Create groups** options.
- In the **Build Settings** of the project, find the **Validate Workspace** setting and make sure it is set to **Yes**.
- In **General > Frameworks > Libraries and Embedded Content**, make sure that the **DynamsoftBarcodeReader.framework** is set to **Embed & Sign**.

### "Unsupported Architectures" error when building and releasing the application for the App Store

The error seems to stem from the inclusion of the **x86_64** architecture in **DynamsoftBarcodeReader.framework**. This error can potentially happen with dynamic libraries (like DBR iOS) that have pieces for all architectures, including devices and simulators. This error can be easily resolved by opting to use the **.xcframework** instead of the **.framework**. However, if you would like to keep using the **.framework**, please keep reading.

This specific error references the **x86_64** architecture which is for the iPhone simulator. When releasing to the App Store, the simulator architectures (**x86_64**) need to be removed from the dynamic library before the project is built for the App Store.

In order to solve the issue, add a **Run Script** phase after the **Embed Frameworks** step of the **Build Phases**, set it to use **/bin/sh**, and use the following script:

```ruby
APP_PATH="${TARGET_BUILD_DIR}/${WRAPPER_NAME}"

# This script loops through the frameworks embedded in the application and
# removes unused architectures.
find "$APP_PATH" -name '*.framework' -type d | while read -r FRAMEWORK
do
    FRAMEWORK_EXECUTABLE_NAME=$(defaults read "$FRAMEWORK/Info.plist" CFBundleExecutable)
    FRAMEWORK_EXECUTABLE_PATH="$FRAMEWORK/$FRAMEWORK_EXECUTABLE_NAME"
    echo "Executable is $FRAMEWORK_EXECUTABLE_PATH"

    EXTRACTED_ARCHS=()

    for ARCH in $ARCHS
    do
        echo "Extracting $ARCH from $FRAMEWORK_EXECUTABLE_NAME"
        lipo -extract "$ARCH" "$FRAMEWORK_EXECUTABLE_PATH" -o "$FRAMEWORK_EXECUTABLE_PATH-$ARCH"
        EXTRACTED_ARCHS+=("$FRAMEWORK_EXECUTABLE_PATH-$ARCH")
    done

    echo "Merging extracted architectures: ${ARCHS}"
    lipo -o "$FRAMEWORK_EXECUTABLE_PATH-merged" -create "${EXTRACTED_ARCHS[@]}"
    rm "${EXTRACTED_ARCHS[@]}"

    echo "Replacing original executable with thinned version"
    rm "$FRAMEWORK_EXECUTABLE_PATH"
    mv "$FRAMEWORK_EXECUTABLE_PATH-merged" "$FRAMEWORK_EXECUTABLE_PATH"

done
```

The script looks through your built application's **Frameworks** folder and make sure only the architectures you're building for are the only ones included in each framework. This way, you don't have to worry about dealing with those arcitectures during the build process.
