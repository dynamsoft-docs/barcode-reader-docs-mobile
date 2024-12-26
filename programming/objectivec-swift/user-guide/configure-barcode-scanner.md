---
layout: default-layout
title: Configure Barcode Scanner - Dynamsoft Barcode Reader iOS Edition
description: Configure the barcode scan settings via BarcodeScannerConfig class when using Barcode Scanner iOS Edition
keywords: Configure, config, BarcodeScannerConfig, iOS
breadcrumbText: Configure Barcode Scanner
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Configure the barcode scan settings

When developing with `BarcodeScannerViewController`, you can add configurations via the `BarcodeScannerConfig` class. This page will guide you on how to configure the settings.

## Barcode Decode Settings

### Set the barcode format via APIs

Set the supported barcode format is always the first step when creating a barcode scanner. It improves the processing speed and the accuracy.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.barcodeFormats = DSBarcodeFormatOneD | DSBarcodeFormatQRCode;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.barcodeFormats = [.oneD, .qrCode]
```

### Setup a customized template file

A template file is a JSON file that includes a series of algorithm parameter settings. It is always used to customize the performance for different usage scenarios. [Contact us](https://www.dynamsoft.com/company/customer-service/#contact) to get a customized template for your scanner.

1. Create a DynamsoftResources folder in the finder. Under the DynamsoftResources folder create a new folder, Templates.

2. Put your .json template file under the Templates folder. Here we suppose you are adding a template file named ReadPDF417.json.

3. Rename the DynamsoftResources folder’s extension name to .bundle and drag the DynamsoftResources.bundle into your project on Xcode. Select Create groups for the Added folders option.

   <div align="left">
      <p><img src="../../assets/init-settings-from-file-ios.png" alt="initSettings" width="50%" /></p>
   </div>

4. Specify the template file via setTemplateFilePath

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
   config.templateFilePath = @"ReadPDF417.json";
   ```
   2. 
   ```swift
   let config = BarcodeScannerConfig()
   config.templateFilePath = "ReadPDF417.json"
   ```

**Related APIs**

- [`barcodeFormats`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#barcodeformats)
- [`templateFilePath`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#templatefilepath)

## Configure the UI Elements

<div align="center">
    <p><img src="../../assets/barcode-scanner-ui.png" width="70%" alt="barcode-scanner"></p>
    <p>Barcode Scanner UI Components</p>
</div>

- Close button: Stop barcode scanning and go back to the previous activity.
- Scan Region: Set a region of interest so that the algorithm focus on this region only. It can sharpenly improve the processing speed. For some special barcode types like DotCode the scan region improves the read-rate as well.
- Torch button: A clickable button that can turn on/off the torch.
- Scan Laser: A line that moving up and down. Its moving area is limited in the scan region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.isCloseButtonVisible = false;
DSRect *region = [[DSRect alloc] init];
region.left = 0.15;
region.top = 0.3;
region.right = 0.85;
region.bottom = 0.7;
config.scanRegion = region;
config.isTorchButtonVisible = false;
config.isScanLaserVisible = false;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.isCloseButtonVisible = false
let region = Rect()
region.left = 0.15
region.top = 0.3
region.right = 0.85
region.bottom = 0.7
config.scanRegion = region
config.isTorchButtonVisible = false
config.isScanLaserVisible = false
```

**Related APIs**

- [`scanRegion`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#scanregion)
- [`torchButtonVisible`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#torchbuttonvisible)
- [`scanLaserVisible`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#scanlaservisible)
- [`closeButtonVisible`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#closebuttonvisible)

## Additional Settings

### Auto Zoom Feature

Enable the camera to zoom-in automatically when:

- The barcodes are too small.
- The barcodes are farway from the camera.

<div align="center">
    <p><img src="../../assets/auto-zoom.gif" width="30%" alt="auto-zoom"></p>
    <p>Auto Zoom</p>
</div>

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.isAutoZoomEnabled = true;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.isAutoZoomEnabled = true
```

**Related API**

- [`autoZoomEnabled`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#autozoomenabled)

### Beep

Let the app to trigger a beep sound when a barcode is decoded.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.isBeepEnabled = true;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.isBeepEnabled = true
```

**Related API**

- [`beepEnabled`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#beepenabled)

## Further Customization

If you have other customization requirements on the `BarcodeScanner` component, you can modify it with the [open source code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile/).
