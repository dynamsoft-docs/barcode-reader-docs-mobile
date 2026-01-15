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

## Build Your BarcodeScanner APP

### Step 1: Create a New Project

The first thing that we are going to do is to create a fresh new project. Here are the steps on how to quickly do that

1. Open Xcode and select create a new project.

2. Select **iOS > App** for your application.

3. Input your product name (ScanSingleBarcode), interface (StoryBoard) and select the language (Objective-C/Swift).

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

### Step 2: Add the SDK

There are three ways in which you can add the `DynamsoftBarcodeReaderBundle` SDK to your project:

#### Option 1: Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> AddPackages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/barcode-reader-spm"

3. Select `barcode-reader-spm`, choose `Exact version`, enter **11.2.5000**, then click **Add Package**.

4. Check all the **xcframeworks** and add.

#### Option 2: Add the Frameworks via CocoaPods

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

#### Option 3: Add Local xcframeworks files

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Dynamsoft Website</a>. After unzipping, you will find a collection of **xcframework** files under the **Dynamsoft\Frameworks** directory.

   - 📄 **DynamsoftBarcodeReaderBundle.xcframework**
   - 📄 **DynamsoftCaptureVisionBundle.xcframework**

2. Drag and drop the above **.xcframework** files into your Xcode project. Make sure to check `Copy items if needed` and `Create groups` to copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for all above **xcframeworks**.

### Step 3: Initialize the License

The first major step in code configuration is to include a valid license in the `BarcodeScannerConfig` object. Below is how to configure the **ViewController** with the license, a button to start scanning and a label to display barcode results:

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

### Step 4: Implementing the Barcode Scanner

Now that the license is configured, implement the `onScannedResult` callback function to handle barcode scan results. The callback receives a `DSBarcodeScanResult` object with `resultStatus` indicating whether the scan finished successfully, was canceled, or encountered an error.

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

### Step 5: Add Navigation Controller

In **Main.storyboard**, add a **Navigation Controller** from the Object Library.

### Step 6: Configure the Barcode Scanner (optional)

Optionally, customize the barcode scanning behavior by configuring the `DSBarcodeScannerConfig` object. You can specify barcode formats, define a scan region, enable audio/visual feedback, and control UI elements like the torch and close buttons.

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

### Step 7: Manually Releasing Deep Learning Models (optional)

To optimize memory usage with deep learning models (available since v11.2.1000), call `clearDLModelBuffers` after each barcode scan to free the cached model data.

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

### Step 8: Run the Project

Configure **Signing & Capabilities** in the project settings. Then, in the Info tab, add the "Privacy - Camera Usage Description" key if not already present. Connect a physical iOS device and select it from the top toolbar, then click Run. (Note: The app requires a physical device and won't work on the simulator.)

<div class="blockquote-note"></div>
> If you try running the project on a simulator, you will encounter errors as this sample uses the device camera which is unavailable when using the simulator.

## Conclusion

Now that your `BarcodeScanner` project is up and running you should be able to see a clean and simplified UI that contains all the necessary UI elements that are needed to make the barcode scanning process as easy and intuitive for the user as it can be.

## Next Steps

For more configurations of the BarcodeScanner, please refer to the [Configure Barcode Scanner](user-guide/configure-barcode-scanner.md) section.

If you would like to work with the original framework and create your own customized UI, please refer to the [Build Your APP with Foundational APIs](foundational-guide.md).

If you have any questions in regards to the usage of the new specialized SDK, do not hesitate to get in touch with the [Dynamsoft Support Team](https://www.dynamsoft.com/contact/).
