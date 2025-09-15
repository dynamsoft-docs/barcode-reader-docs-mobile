---
layout: default-layout
title: Getting Started with Barcode Reader - Dynamsoft Capture Vision Cordova Edition
description: This is the user guide of Dynamsoft Capture Vision Cordova edition - Barcode Reader module
keywords: User guide, Barcode Reader, Cordova, Capture Vision, Dynamsoft
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Guide of Dynamsoft Barcode Reader Cordova
---

# Barcode Reader User Guide for Cordova

In this guide, we will explore the Barcode Reader module of the Dynamsoft Capture Vision library for Cordova.

## Table of Contents

- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Build Your Barcode Scanner App](#build-your-barcode-scanner-app)
  - [Set up Development Environment](#set-up-development-environment)
  - [Initialize the Project](#initialize-the-project)
  - [Include the Library](#include-the-library)
  - [Initialize the License](#initialize-the-license)
  - [Initialize the Camera Module](#initialize-the-camera-module)
  - [Configure the Barcode Reader Module](#configure-the-barcode-reader-module)
  - [Run the Project](#run-the-project)
- [Customizing the Barcode Reader](#customizing-the-barcode-reader)
  - [Using the Settings Templates](#using-the-settings-templates)
  - [Using the DBRRuntimeSettings Interface](#using-the-dbrruntimesettings-interface)
  - [Customizing the Scan Region](#customizing-the-scan-region)
- [Licensing](#licensing)

## System Requirements

### Cordova Platforms

- Cordova Android: 10.1.1+
- Cordova iOS: 6.2.0

### Android

- Supported OS: Android 5.0 (API Level 21) or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Android Studio 3.4+ (Android Studio 4.2+ recommended).
- JDK: 1.8+

### iOS

- Supported OS: **iOS 11.0** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 7.1 and above (Xcode 13.0+ recommended), CocoaPods 1.11.0+.

## Installation

- **npm**

```bash
cordova plugin add dynamsoft-capture-vision-cordova
```

## Build Your Barcode Scanner App

Now you will learn how to create a simple barcode scanner using Dynamsoft Capture Vision for Cordova.

>Note: Instead of following this guide, you can also initialize a project with this template to get started: <a href="https://github.com/Dynamsoft/capture-vision-cordova-samples/tree/main/BarcodeReaderSimpleSample" target="_blank">Barcode Reader Simple Sample</a>.

### Set up Development Environment

If you are a beginner with Cordova, please follow the guide on the <a href="https://cordova.apache.org/docs/en/11.x/guide/cli/index.html" target="_blank">Cordova official website</a> to set up the development environment.

### Initialize the Project

Use the following command to create a new project.

```bash
cordova create SimpleBarcodeScanner
```

### Include the Library

Use the following command to include the library.

```bash
cordova plugin add dynamsoft-capture-vision-cordova
```

### Initialize the License

The Barcode Reader module of Dynamsoft Capture Vision needs a valid license to work. Add the following code in **www/js/index.js** to initialize the license of the Barcode Reader module

```js
// Register the event of device ready.
document.addEventListener('deviceready', onDeviceReady, false)

async function onDeviceReady() {
    ...
    // Here we use a public trial key as an example.
    try {
        await Dynamsoft.DCVBarcodeReader.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9")
    } catch (e) {
        console.log(e)
    }
}
```

### Initialize the Camera Module

Dynamsoft Capture Vision provides a build-in camera module for you to capture and display the video stream. The following two classes are used when initializing the camera module:

- [`DCVCameraEnhancer`](../api-reference/camera-enhancer.md): The class that provides camera controlling APIs. Please visit the link to learn more.
- [`DCVCameraView`](../api-reference/camera-view.md): The camera view that will display the video stream and other UI elements. Please visit the link to learn more.

1. Find the **www/index.html** file in your project. Replace the original content with the following code:

    ```html
    <!DOCTYPE html>
    <html>
        <body style="margin: 0;">
            <div id="camera_view" style="width: 100vw; height: 100vh; z-index: -1;">
                <div id="show_result" style="position: fixed; width: 100vw; bottom: 10vh;  text-align:center; color: white; "></div>
            </div>
            <script src="cordova.js"></script>
            <script src="js/index.js"></script>
        </body>
    </html>
    ```

2. Open **www/js/index.js** and add code to initialize `DCVCameraEnhancer` and `DCVCameraView`

    ```js
    var dcvCameraEnhancer
    // Get the camera_view <div> we created in the previous step.
    const cameraViewElement = document.getElementById("camera_view")

    async function onDeviceReady() {
        // Create the instance of DCVCameraEnhancer.
        dcvCameraEnhancer = await Dynamsoft.DCVCameraEnhancer.createInstance()
        // Create the instance of DCVCameraView.
        var cameraView = new Dynamsoft.DCVCameraView()
        // Bind the instance of DCVCameraView with the div you created before.
        cameraView.bindToHtmlElement(cameraViewElement)
        // Display overlays on the detected barcodes.
        cameraView.setOverlayVisible(true)
    }
    ```

### Configure the Barcode Reader Module

1. Initialize the barcode reader module. Register a result listener for obtaining the barcode results.

    ```js
    ...
    var dcvBarcodeReader
    async function onDeviceReady() {
        ...
        // Create the instance of DCVBarcodeReader.
        dcvBarcodeReader = await Dynamsoft.DCVBarcodeReader.createInstance()
        dcvBarcodeReader.addResultListener((results) => {
            const resultElement = document.getElementById('show_result')
            var resultStr = ""
            if (results && results.length > 0) {
                for (i = 0; i < results.length; i++) {
                    resultStr=resultStr + results[i].barcodeFormatString+":"+results[i].barcodeText+'\n'
                }
                resultElement.innerHTML = (resultStr)
            } else {
                resultElement.innerHTML = "No barcode detected in this frame."
            }
            document.querySelector('#camera_view').appendChild(resultElement)
        })
    }
    ```

2. Open the camera and start barcode scanning. You will receive the barcode results from the result listener.

    ```js
    async function onDeviceReady() {
        ...
        dcvCameraEnhancer.open()
        dcvBarcodeReader.startScanning()
    }
    ```

3. Register the event listeners `onResume` and `onPasue` so that the library can stop/restart barcode decoding when the user pauses or resumes the feature.

    ```js
    document.addEventListener('resume', onResume, false)
    document.addEventListener('pause', onPause, false)

    ...

    function onResume() {
        dcvCameraEnhancer.open()
        dcvBarcodeReader.startScanning()
    }

    function onPause() {
        dcvCameraEnhancer.close()
        dcvBarcodeReader.stopScanning()
    }
    ```

### Run the Project

#### Run Android on Windows or macOS

1. Add the platform first with the following command.

    ```bash
    cordova platform add android
    ```

2. Run the Project with the following command.

    ```bash
    cordova run android
    ```

> You might meet issues on gradle path if it is the first time to run Cordova on your Windows system. The following steps will help you on solving this issue:
>
> - Open **Environment Variables**
> - Look for **Path** in the **System variables**, open it.
> - Click **New** and add the path of your gradle bin folder to the environment variables. For exmaple: "C:\Users\admin\\.gradle\wrapper\dists\gradle-6.4-all\gradle-6.4\bin".

#### Run iOS on macOS

1. Add the platform first.

    ```bash
    cordova platform add ios
    ```

2. Open the **platforms/ios/SimpleBarcodeScanner.xcworkspace** with xcode. Complete the *Signing & Capabilities* section of the project configuration via Xcode to avoid any signature errors during build.

## Customizing the Barcode Reader

### Using the Settings Templates

DBR offers several preset templates for different popular scenarios. For example, to prioritize speed over accuracy, you can use one of the speed templates and choose the corresponding template for images or video, and vice versa if you're looking to prioritize read rate and accuracy over speed. For the full set of templates, please refer to [`EnumDBRPresetTemplate`](../api-reference/enum-dbr-preset-template.md). Here is a quick example of prioritizing read rate for image-based decoding:

```js
dcvBarcodeReader.updateRuntimeSettings(Dynamsoft.EnumDBRPresetTemplate.IMAGE_READ_RATE_FIRST)
```

### Using the DBRRuntimeSettings Interface

The SDK also supports a more granular control over the individual runtime settings rather than using a preset template. The main settings that you can control via this interface are which barcode formats to read, the expected number of barcodes to be read in a single image or frame, and the timeout. For more info on each, please refer to [`DBRRuntimeSettings`](../api-reference/interface-dbr-runtime-settings.md). Here is a quick example:

```js
// Get the current runtime settings of the barcode reader.
let settings = await reader.getRuntimeSettings()
// Set the expected barcode count to 0 when you are not sure how many barcodes you are scanning.
// Set the expected barcode count to 1 can maximize the barcode decoding speed.
settings.expectedBarcodesCount = 0
// Set the barcode formats to read.
settings.barcodeFormatIds = EnumBarcodeFormat.BF_ONED | EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_PDF417 | EnumBarcodeFormat.BF_DATAMATRIX
// Apply the new settings to the barcode reader.
await reader.updateRuntimeSettings(settings)
```

### Customizing the Scan Region

You can also limit the scan region of the SDK so that it doesn't exhaust resources trying to read from the entire image or frame. In order to do this, we will need to use the [`Region`](../api-reference/interface-region.md) interface along with the `DCVCameraEnhancer` class.

How to set scan region:

- Define a `Region` object.
- Configure the value of `Region`.
- Assign the `Region` to the `ScanRegion` property of the `DCVCameraEnhancer` object.

```js
dcvCameraEnhancer.setScanRegion({
    regionLeft: 15,
    regionRight: 85,
    regionTop: 30,
    regionBottom: 70,
    regionMeasuredByPercentage: true
})
```

## Licensing

- The `BarcodeReader` module of Dynamsoft Capture Vision needs a valid license to work.
- A one-day trial license is available by default for every new device to try Dynamsoft Capture Vision.
>- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=cordova&version=9){:target="_blank"} link.
- [Contact us](https://www.dynamsoft.com/company/contact/) to purchase a full license.
