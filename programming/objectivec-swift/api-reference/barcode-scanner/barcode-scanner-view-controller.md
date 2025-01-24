---
layout: default-layout
title: BarcodeScannerViewController Class - Dynamsoft Barcode Reader iOS Edition
description: BarcodeScannerViewController of Dynamsoft Barcode Reader iOS is a ViewController class that implements barcode decoding features.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScannerViewController
---

# Class BarcodeScannerViewController

`BarcodeScannerViewController` is an extension of the ViewController class that implements barcode decoding features.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface BarcodeScannerViewController: UIViewController
```
2. 
```swift
class BarcodeScannerViewController: UIViewController
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`config`](#config) | *DSBarcodeScannerConfig \** | Sets or returns the barcode scanner configurations. |
| [`onScannedResult`](#onscannedresult) | *void (^)(DSMRZScanResult *)* | A property that holds a Block. The block is a callback that takes a single parameter of type `DSMRZScanResult` and returns no value. |

### config

Sets or returns the barcode scanner configurations of type [`DSMRZScannerConfig`](barcode-scanner-config.md).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, strong, readwrite) DSMRZScannerConfig * config
```
1. 
```swift
var config: BarcodeScannerConfig = .init()
```

### onScannedResult

A property that holds a Block. The block is a callback that takes a single parameter of type [`DSMRZScanResult`](barcode-scan-result.md) and returns no value.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, copy, readwrite) void (^)(DSMRZScanResult *) onScannedResult
```
1. 
```swift
var onScannedResult: ((BarcodeScanResult) -> Void)?
```

## How to Use

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
#import "ViewController.h"
#import <DynamsoftLicense/DynamsoftLicense.h>
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
// Config a button on the UI. Pop the BarcodeScannerViewController when the button is clicked.
- (void)buttonTapped {
   DSBarcodeScannerViewController *vc = [[DSBarcodeScannerViewController alloc] init];
   DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
   config.license = @"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9";
   vc.config = config;
   __weak typeof(self) weakSelf = self;
   vc.onScannedResult = ^(DSBarcodeScanResult *result) {
          // The result have 3 status: finished (Successfully decoded), canceled (Quit by clicking close button), exception (error occurs when processing).
          switch (result.resultStatus) {
             case DSResultStatusFinished: {
                    // Add your code to do when the result status is finished.
             }
             case DSResultStatusCanceled: {
                    // Add your code to do when the result status is canceled.
             }
             case DSResultStatusException: {
                    // Add your code to do when the result status is exception.
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
@end
```
2. 
```swift
import UIKit
import DynamsoftLicense
import DynamsoftBarcodeReaderBundle
class ViewController: UIViewController {
   let button = UIButton()
   let label = UILabel()
   override func viewDidLoad() {
          super.viewDidLoad()
          setup()
   }
   // Config a button on the UI. Pop the BarcodeScannerViewController when the button is clicked.
   @objc func buttonTapped() {
          let vc = BarcodeScannerViewController()
          // Set up the license via the BarcodeScannerConfig
          let config = BarcodeScannerConfig()
          config.license = "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9"
          vc.config = config
          // Set up the result callback of BarcodeScannerViewController.
          vc.onScannedResult = { [weak self] result in
             guard let self = self else { return }
             // The result have 3 status: finished (Successfully decoded), canceled (Quit by clicking close button), exception (error occurs when processing).
             switch result.resultStatus {
             case .finished:
                    // Add your code to do when the result status is finished.
             case .canceled:
                    // Add your code to do when the result status is canceled.
             case .exception:
                    // Add your code to do when the result status is exception.
             @unknown default:
                    break
             }
             DispatchQueue.main.async {
                    self.navigationController?.popViewController(animated: true)
             }
          }
          DispatchQueue.main.async {
             self.navigationController?.navigationBar.isHidden = true
             self.navigationController?.pushViewController(vc, animated: true)
          }
   }
}
```
