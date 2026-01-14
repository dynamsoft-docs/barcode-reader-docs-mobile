---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader for iOS (Ready to Use UI edition)
description: This is the user guide of Dynamsoft Barcode Reader for iOS SDK demonstrating the Ready to Use UI.
keywords: user guide, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# BarcodeScanner iOS User Guide

This user guide will walk through the [ScanSingleBarcode](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/BarcodeScannerAPISamples/) sample app. When creating your own project, please use this sample as a reference. This guide uses [`BarcodeScanner`](api-reference/barcode-scanner/index.md) API which aim to elevate the UI creation process with less code and offer a more pleasant and intuitive UI for your app.

<div class="blockquote-note"></div>
>
> This guide aims at scanning a single barcode with the `BarcodeScanner` component.
>
> - If you have requirement for scanning multiple barcodes, you may refer to the [ScanMultipleBarcodes](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/BarcodeScannerAPISamples/ScanMultipleBarcodes/) sample or read [Enable Multiple Barcode Scanning](user-guide/scanner-multi-barcodes.md) article.
> - If you have more complex customization requirements for the interface, you may refer to the [Foundational API Samples](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/) or [Build your APP with Foundational APIs]({{ site.oc }}foundational-guide.html) article.

## Requirements

- Supported OS: **iOS 13** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: **Xcode 13** and above (Xcode 14.1+ recommended).

## Add the SDK

There are three ways in which you can include the `DynamsoftBarcodeReaderBundle` library in your app:

### Option 1: Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> AddPackages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/barcode-reader-spm"

3. Select `barcode-reader-spm`, choose `Exact version`, enter **11.2.5000**, then click **Add Package**.

4. Check all the **xcframeworks** and add.

### Option 2: Add the Frameworks via CocoaPods

1. Add the frameworks in your **Podfile**, replace `TargetName` with your real target name.

   ```sh
   target 'ScanSingleBarcode' do
      use_frameworks!

   pod 'DynamsoftBarcodeReaderBundle','11.2.5000'

   end
   ```

2. Execute the pod command to install the frameworks and generate workspace(**[TargetName].xcworkspace**):

   ```sh
   pod install
   ```

### Option 3: Add Local xcframeworks files

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Dynamsoft Website</a>. After unzipping, you will find a collection of **xcframework** files under the **Dynamsoft\Frameworks** directory.

   - 📄 **DynamsoftBarcodeReaderBundle.xcframework**
   - 📄 **DynamsoftCaptureVisionBundle.xcframework**

2. Drag and drop the above **.xcframework** files into your Xcode project. Make sure to check `Copy items if needed` and `Create groups` to copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for all above **xcframeworks**.

## Build Your BarcodeScanner APP

### Step 1: Create a New Project

The first thing that we are going to do is to create a fresh new project. Here are the steps on how to quickly do that

1. Open Xcode and select create a new project.

2. Select **iOS > App** for your application.

3. Input your product name (ScanSingleBarcode), interface (StoryBoard) and select the language (Objective-C/Swift).

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

### Step 2: Include the Library

Add the SDK to your new project. Please read [Add the SDK](#add-the-sdk) section for more details.

### Step 3: Initialize the License

The first major step in code configuration is to include a valid license in the `BarcodeScannerConfig` object, which is used when launching the scanner. Let's break it down into two smaller steps:

1. Configure the *ViewController*

   There will be a single button that will start the operation as well as a label where the barcode results will be displayed as they are being scanned. The lciense initialization will happen on the button click, and so a valid license must be attached to the `BarcodeScannerConfig` object, which is used when launching the scanner.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   #import "ViewController.h"
   #import <DynamsoftBarcodeReaderBundle/DynamsoftBarcodeReaderBundle.h>
   #import <DynamsoftBarcodeReaderBundle/DynamsoftBarcodeReaderBundle-Swift.h>
   @interface ViewController ()
   @property (nonatomic, strong) UIButton *button;
   @property (nonatomic, strong) UILabel *label;
   @end
   @implementation ViewController
   - (void)viewDidLoad {
      [super viewDidLoad];
      [self setup];
   }
   - (void)buttonTapped {
      DSBarcodeScannerViewController *vc = [[DSBarcodeScannerViewController alloc] init];
      DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
      config.license = @"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9";
      vc.config = config;
   }
   - (void)setup {
      self.button = [UIButton buttonWithType:UIButtonTypeSystem];
      self.button.backgroundColor = [UIColor blackColor];
      [self.button setTitle:@"Scan a Barcode" forState:UIControlStateNormal];
      [self.button setTitleColor:[UIColor whiteColor] forState:UIControlStateNormal];
      self.button.layer.cornerRadius = 8;
      self.button.clipsToBounds = YES;
      [self.button addTarget:self action:@selector(buttonTapped) forControlEvents:UIControlEventTouchUpInside];
      self.button.translatesAutoresizingMaskIntoConstraints = NO;
      [self.view addSubview:self.button];
      self.label = [[UILabel alloc] init];
      self.label.numberOfLines = 0;
      self.label.textColor = [UIColor blackColor];
      self.label.textAlignment = NSTextAlignmentCenter;
      self.label.font = [UIFont systemFontOfSize:20];
      self.label.translatesAutoresizingMaskIntoConstraints = NO;
      [self.view addSubview:self.label];
      UILayoutGuide *safeArea = self.view.safeAreaLayoutGuide;
      [NSLayoutConstraint activateConstraints:@[
             [self.button.centerXAnchor constraintEqualToAnchor:self.view.centerXAnchor],
             [self.button.topAnchor constraintEqualToAnchor:safeArea.topAnchor constant:50],
             [self.button.heightAnchor constraintEqualToConstant:50],
             [self.button.widthAnchor constraintEqualToConstant:150],
             [self.label.centerXAnchor constraintEqualToAnchor:safeArea.centerXAnchor],
             [self.label.centerYAnchor constraintEqualToAnchor:safeArea.centerYAnchor],
             [self.label.leadingAnchor constraintEqualToAnchor:safeArea.leadingAnchor constant:30],
             [self.label.trailingAnchor constraintEqualToAnchor:safeArea.trailingAnchor constant:-30]
      ]];
   }
   @end
   ```
   2. 
   ```swift
   import UIKit
   import DynamsoftBarcodeReaderBundle
   class ViewController: UIViewController {
      let button = UIButton()
      let label = UILabel()
      override func viewDidLoad() {
             super.viewDidLoad()
             setup()
      }
      @objc func buttonTapped() {
             let vc = BarcodeScannerViewController()
             let config = BarcodeScannerConfig()
             config.license = "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9"
             vc.config = config
      }
      func setup() {
             button.backgroundColor = .black
             button.setTitle("Scan a Barcode", for: .normal)
             button.setTitleColor(.white, for: .normal)
             button.layer.cornerRadius = 8
             button.clipsToBounds = true
             button.addTarget(self, action: #selector(buttonTapped), for: .touchUpInside)
             button.translatesAutoresizingMaskIntoConstraints = false
             view.addSubview(button)
             label.numberOfLines = 0
             label.textColor = .black
             label.textAlignment = .center
             label.font = UIFont.systemFont(ofSize: 20)
             label.translatesAutoresizingMaskIntoConstraints = false
             view.addSubview(label)
             let safeArea = view.safeAreaLayoutGuide
             NSLayoutConstraint.activate([
                button.centerXAnchor.constraint(equalTo: view.centerXAnchor),
                button.topAnchor.constraint(equalTo: safeArea.topAnchor, constant: 50),
                button.heightAnchor.constraint(equalToConstant: 50),
                button.widthAnchor.constraint(equalToConstant: 150),
                label.centerXAnchor.constraint(equalTo: safeArea.centerXAnchor),
                label.centerYAnchor.constraint(equalTo: safeArea.centerYAnchor),
                label.leadingAnchor.constraint(equalTo: safeArea.leadingAnchor, constant: 30),
                label.trailingAnchor.constraint(equalTo: safeArea.trailingAnchor, constant: -30)
             ])
      }
   }
   ```

   <div class="blockquote-note"></div>
   >
   >- The license string here grants a time-limited free trial which requires network connection to work.
   >- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=ios){:target="_blank"} link.
   >- If you download the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Installation Package</a>, it comes with a 30-day trial license by default.

2. Configure *NavigationController*

   The license is initialized in another view. As a result, we must first define a couple of essential elements of the storyboard and the associated views that are required. We will only have one *ViewController*, with an associated *NavigationController* to allow the user to navigate back and forth from the home page to the main *ViewController* where the Barcode Scanner will operate.

### Step 4: Implementing the Barcode Scanner

Now that the license is configured and the license has been set, it is time to implement the actions to take when a barcode is scanned via the `onScannedResult` callback function. The callback function is triggered whenever a barcode is found, so we must implement the code that will display the barcode's text in the *label* that we previously defined.

Each result comes with a `DSResultStatus` that can be one of *finished*, *canceled*, or *exception*. The first, *finished*, indicates that the result has been decoded and is available - while *canceled* indicates that the operation has been halted. If *exception* is the result status, then that means that an error has occurred during the barcode detection process. Let us now continue the code of the `buttonTapped` method from step 3:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
/* CONTINUATION OF CODE FROM STEP 3 */
- (void)buttonTapped {
   DSBarcodeScannerViewController *vc = [[DSBarcodeScannerViewController alloc] init];
   DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
   config.license = @"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9";
   // some other settings
   vc.config = config;
   __weak typeof(self) weakSelf = self;
   vc.onScannedResult = ^(DSBarcodeScanResult *result) {
          switch (result.resultStatus) {
             case DSResultStatusFinished: {
                dispatch_async(dispatch_get_main_queue(), ^{
                   NSString *format = result.barcodes.firstObject.formatString ?: @"";
                   NSString *text = result.barcodes.firstObject.text ?: @"";
                   weakSelf.label.text = [NSString stringWithFormat:@"Result:\nFormat: %@\nText: %@", format, text];
                });
                break;
             }
             case DSResultStatusCanceled: {
                dispatch_async(dispatch_get_main_queue(), ^{
                   weakSelf.label.text = @"Scan canceled";
                });
                break;
             }
             case DSResultStatusException: {
                dispatch_async(dispatch_get_main_queue(), ^{
                    weakSelf.label.text = result.errorString;
                });
                break;
             }
             default:
                break;
          }
          dispatch_async(dispatch_get_main_queue(), ^{
             [weakSelf.navigationController popViewControllerAnimated:YES];
          });
   };
   dispatch_async(dispatch_get_main_queue(), ^{
          weakSelf.navigationController.navigationBar.hidden = YES;
          [weakSelf.navigationController pushViewController:vc animated:YES];
   });
}
```
2. 
```swift
class ViewController: UIViewController {
   /* CONTINUATION OF CODE FROM STEP 3 */
   @objc func buttonTapped() {
          let vc = BarcodeScannerViewController()
          let config = BarcodeScannerConfig()
          config.license = "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9"
          // some other settings
          vc.config = config
          vc.onScannedResult = { [weak self] result in
             guard let self = self else { return }
             switch result.resultStatus {
             /* if the result is valid, display it in the label */
             case .finished:
                DispatchQueue.main.async {
                   let format = result.barcodes?.first?.formatString ?? ""
                   self.label.text = "Result:\nFormat: " + (format) + "\n" + "Text: " + (result.barcodes?.first?.text ?? "")
                }
             /* if the scan operation is canceled by the user */
             case .canceled:
                DispatchQueue.main.async {
                   self.label.text = "Scan canceled"
                }
             /* if an error occurs during capture, display the error string in the label */
             case .exception:
                DispatchQueue.main.async {
                   self.label.text = result.errorString
                }
             @unknown default:
                break
             }
             /* return back to the home page to display the result/cancel message/error string */
             DispatchQueue.main.async {
                self.navigationController?.popViewController(animated: true)
             }
          }
          /* when the button is clicked, hide the navigation bar and push the newly created BarcodeScannerViewController to the main view */
          DispatchQueue.main.async {
             self.navigationController?.navigationBar.isHidden = true
             self.navigationController?.pushViewController(vc, animated: true)
          }
   }
}
```

### Step 5: Configure the Barcode Scanner (optional)

This next step, although optional, is highly recommended to help you achieve a smooth-looking UI. In this step, we will configure the `setup` method that was called in `viewDidLoad`. In `setup` we will define the styles of different UI elements including the main "Scan a Barcode" button as well as the results label. Please note that this UI setup can also be done directly in the *Main.storyboard* but in this guide we opted to have the entire configuration done via the code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
// You can use the following code to specify the barcode format. If you are using a template file, the "BarcodeFormat" can also be specified via the template file.
config.barcodeFormats = DSBarcodeFormatOneD | DSBarcodeFormatQRCode;
// If you have a customized template file, please put it under "DynamsoftResources.bundle\Templates\" and call the following code.
config.templateFile = @"ReadSingleBarcode.json";
// The following settings will display a scan region on the view. Only the barcode in the scan region can be decoded.
DSRect *region = [[DSRect alloc] init];
region.left = 0.15;
region.top = 0.3;
region.right = 0.85;
region.bottom = 0.7;
config.scanRegion = region;
// Add the following line to enable the beep sound when a barcode is scanned.
config.isBeepEnabled = true;
// Add the following line if you don't want to display the torch button.
config.isTorchButtonVisible = false;
// Add the following line if you don't want to display the close button.
config.isCloseButtonVisible = false;
// Add the following line if you want to hide the scan laser.
config.isScanLaserVisible = false;
// Add the following line if you want the camera to auto-zoom when the barcode is far away.
config.isAutoZoomEnabled = true;
```
2. 
```swift
let config = BarcodeScannerConfig()
// You can use the following code to specify the barcode format. If you are using a template file, the "BarcodeFormat" can also be specified via the template file.
config.barcodeFormats = [.oneD, .qrCode]
// If you have a customized template file, please put it under "DynamsoftResources.bundle\Templates\" and call the following code.
config.templateFile = "ReadSingleBarcode.json"
// The following settings will display a scan region on the view. Only the barcode in the scan region can be decoded.
let region = Rect()
region.left = 0.15
region.top = 0.3
region.right = 0.85
region.bottom = 0.7
config.scanRegion = region
// Add the following line to enable the beep sound when a barcode is scanned.
config.isBeepEnabled = true
// Add the following line if you don't want to display the torch button.
config.isTorchButtonVisible = false
// Add the following line if you don't want to display the close button.
config.isCloseButtonVisible = false
// Add the following line if you want to hide the scan laser.
config.isScanLaserVisible = false
// Add the following line if you want the camera to auto-zoom when the barcode is far away.
config.isAutoZoomEnabled = true
```

### Step 6: Manually Releasing Deep Learning Models (optional)

Starting from v11.2.1000, Dynamsoft Barcode Reader integrates deep learning models to enhance decoding ability. Once initialized, these models remain cached in memory until they are explicitly released. If the decoding task has finished, call `clearDLModelBuffers` to free the associated memory.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
vc.onScannedResult = ^(DSBarcodeScanResult *result) {
   [DSCaptureVisionRouter clearDLModelBuffers];
};
```
2. 
```swift
vc.onScannedResult = { [weak self] result in
   CaptureVisionRouter.clearDLModelBuffers()
}
```

### Step 7: Run the Project

Now that the code has been written, it's time to run the project. The first thing that needs to be done is to configure the *Signing & Capabilities* section of the project. After you complete this section, move to the *Info* section of the project settings. In the *Info* section, please make sure that the "Privacy - Camera Usage Description" key is included in the list.

In order to run the project, you will require a physical iOS device. Once the device is connected, you should see it as an available device in top bar. After selecting the device from the menu, all you need to do is click the Run button. 

<div class="blockquote-note"></div>
> If you try running the project on a simulator, you will encounter errors as this sample uses the device camera which is unavailable when using the simulator.

## Conclusion

Now that your `BarcodeScanner` project is up and running you should be able to see a clean and simplified UI that contains all the necessary UI elements that are needed to make the barcode scanning process as easy and intuitive for the user as it can be.

## Next Steps

For more configurations of the BarcodeScanner, please refer to the [Configure Barcode Scanner](user-guide/configure-barcode-scanner.md) section.

If you would like to work with the original framework and create your own customized UI, please refer to the [Build Your APP with Foundational APIs](foundational-guide.md).

If you have any questions in regards to the usage of the new specialized SDK, do not hesitate to get in touch with the [Dynamsoft Support Team](https://www.dynamsoft.com/contact/).
