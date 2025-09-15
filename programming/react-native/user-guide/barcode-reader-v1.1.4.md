---
layout: default-layout
title: Getting Started with Barcode Reader - Dynamsoft Capture Vision React Native Edition
description: This page is the user guide of Dynamsoft Capture Vision - Barcode Reader module
keywords: User guide, Barcode Reader
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Guide of Barcode Reader
---

# Barcode Reader User Guide for React Native

In this guide, we will explore the Barcode Reader module of the Dynamsoft Capture Vision library.

<span style="font-size:20px">Table of Contents</span>

- [Barcode Reader User Guide for React Native](#barcode-reader-user-guide-for-react-native)
  - [System Requirements](#system-requirements)
    - [React Native](#react-native)
    - [Android](#android)
    - [iOS](#ios)
    - [Others](#others)
  - [Installation](#installation)
  - [Build Your Barcode Scanner App](#build-your-barcode-scanner-app)
    - [Set up Development Environment](#set-up-development-environment)
    - [Initialize the Project](#initialize-the-project)
    - [Include the Library](#include-the-library)
    - [Configure the Barcode Reader](#configure-the-barcode-reader)
    - [Rendering the UI](#rendering-the-ui)
    - [Configure Camera Permissions](#configure-camera-permissions)
    - [Run the Project](#run-the-project)
      - [Run Android on Windows](#run-android-on-windows)
      - [Run iOS on macOS](#run-ios-on-macos)
  - [Customizing the Barcode Reader](#customizing-the-barcode-reader)
    - [Using the settings templates](#using-the-settings-templates)
    - [Using the DBRRuntimeSettings interface](#using-the-dbrruntimesettings-interface)
    - [Customizing the scan region](#customizing-the-scan-region)
  - [Licensing](#licensing)

## System Requirements

### React Native

- Supported Version: 0.60 or higher

### Android

- Supported OS: Android 5.0 (API Level 21) or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Android Studio 3.4+ (Android Studio 4.2+ recommended).
- JDK: 1.8+

### iOS

- Supported OS: **iOS 10.0** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 7.1 and above (Xcode 13.0+ recommended), CocoaPods 1.11.0+.

### Others

- Node: 16.15.1+ recommended

## Installation

- **yarn**

  ```bash
  yarn add dynamsoft-capture-vision-react-native
  ```

- **npm**

  ```bash
  npm install dynamsoft-capture-vision-react-native
  ```

## Build Your Barcode Scanner App

Now you will learn how to create a simple barcode scanner using Dynamsoft Capture Vision SDK.

>Note: You can get the full source code of a similar project:  [Barcode Reader Simple Sample](https://github.com/Dynamsoft/capture-vision-react-native-samples/tree/v1.1.14/BarcodeReaderSimpleSample)

### Set up Development Environment

If you are a beginner with React Native, please follow the guide on the <a href="https://reactnative.dev/docs/environment-setup" target="_blank">React Native official website</a> to set up the development environment.

### Initialize the Project

Create a new React Native project.

```bash
npx react-native init SimpleBarcodeScanner
```

>Note: This sample uses React 17.0.2 and React Native 0.65.0.

### Include the Library

Add the SDK to your new project. Once the SDK is added, you will see a reference to it in the **package.json**.

- **yarn**

  ```bash
  yarn add dynamsoft-capture-vision-react-native
  ```

- **npm**

  ```bash
  npm install dynamsoft-capture-vision-react-native
  ```

For iOS, you can install the necessary native frameworks from cocoapods by running the `pod install` command as below:

```bash
cd ios
```

```bash
pod install
```

### Configure the Barcode Reader

In `App.js`, import the following components:

```js
import React from 'react';
import {Text} from 'react-native';
import {
    DynamsoftBarcodeReader,
    DynamsoftCameraView,
    EnumBarcodeFormat
} from 'dynamsoft-capture-vision-react-native';
```

Next in `App.js`, let's define the `state` to your component. In the `state`, add a `results` variable, initialized to `null`. In the following steps, we will store the newly decoded barcodes to `results`.

```js
class App extends React.Component {
    state = {
        results: null
    };
}
export default App;
```

Next is the `componentDidMount` implementation. First up is adding the code to start barcode decoding:

```js
class App extends React.Component {
    ...
    componentDidMount() {
        (async () => {
            // Initialize the license so that you can use full feature of the Barcode Reader module.
            try {
                await DynamsoftBarcodeReader.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
            } catch (e) {
                console.log(e);
            }
            // Create a barcode reader instance.
            this.reader = await DynamsoftBarcodeReader.createInstance();

            // Add a result listener. The result listener will handle callback when barcode result is returned. 
            this.reader.addResultListener((results) => {
                // Update the newly detected barcode results to the state.
                this.setState({results});
            });

            // Enable video barcode scanning.
            // If the camera is opened, the barcode reader will start the barcode decoding thread when you triggered the startScanning.
            // The barcode reader will scan the barcodes continuously before you trigger stopScanning.
            this.reader.startScanning();
        })();
    }
    ...
}
```

After implementing `componentDidMount`, `componentWillUnmount` will then include code to stop the barcode decoding and remove the result listener.

```js
class App extends React.Component {
    ...
    async componentWillUnmount() {
        // Stop the barcode decoding thread when your component is unmount.
        await this.reader.stopScanning();
        // Remove the result listener when your component is unmount.
        this.reader.removeAllResultListeners();
    }
    ...
}
```

### Rendering the UI

Lastly, let's create the `DynamsoftCameraView` UI component in the `render` function.

```jsx
class App extends React.Component {
    ...
    render() {
        // Add code to fetch barcode text and format from the BarcodeResult
        let results = this.state.results;
        let resultBoxText = "";
        if (results && results.length>0){
            for (let i=0;i<results.length;i++){
                resultBoxText+=results[i].barcodeFormatString+"\n"+results[i].barcodeText+"\n";
            }
        }
        // Render DynamsoftCameraView componment.
        return (
            <DynamsoftCameraView
                style={
                    {
                        flex: 1
                    }
                }
                ref = {(ref)=>{this.scanner = ref}}
                overlayVisible={true}
            >
                {/*Add a text box to display the barcode result.*/}
                <Text style={
                    {
                        flex: 0.9,
                        marginTop: 100,
                        textAlign: "center",
                        color: "white",
                        fontSize: 18,
                    }
                }>{results && results.length > 0 ? resultBoxText : "No Barcode Detected"}</Text>
            </DynamsoftCameraView>
        );
    }
}
```

### Configure Camera Permissions

You need to set the "Privacy - Camera Usage Description" field in the `Info.plist` file for iOS. If this property is not set, the iOS application will fail at runtime. In order to set this property, you might need to use Xcode and open the corresponding `.xcworkspace` located in the `ios` folder. Once open, you can edit the `Info.plist` to include this property.

### Run the Project

#### Run Android on Windows

In the command line interface (Powershell recommended), go to your project folder and run the following command:

```bash
npx react-native run-android
```

#### Run iOS on macOS

In the terminal, go to the project folder in your project:

```bash
npx react-native run-ios
```

> Note:
>
>- The application needs to run on a physical device rather than a simulator as it requires the use of the camera. If you try running it on a simulator, you will most likely run into a number of errors/failures.
>- On iOS, in order to run the React Native app on a physical device you will need to install the [`ios-deploy`](https://www.npmjs.com/package/ios-deploy) library. Afterwards, you can run the react native app from the terminal as such `npx react-native run-ios --device` assuming it's the only device connected to the Mac.
>- Alternatively on iOS, you can simply open the `xcworkspace` of the project found in the `ios` folder using Xcode and run the sample on your connected iOS device from there. The advantage that this offers is that it is easier to deal with the developer signatures for deployment in there.

>Note: You can get the full source code of a similar project:  [Barcode Reader Simple Sample](https://github.com/Dynamsoft/capture-vision-react-native-samples/tree/v1.1.14/BarcodeReaderSimpleSample)

## Customizing the Barcode Reader

There are several ways in which you can customize the Barcode Reader - but what they all have in common is that each involves the [`updateRuntimeSettings`](../api-reference/barcode-reader.md#updateruntimesettings) method. There are currently three methods in which you can update the runtime settings.

### Using the settings templates

Dynamsoft barcode reader offers several preset templates for different popular scenarios. To prioritize speed over accuracy, then you will want to use one of the speed templates, choosing the corresponding template for images or video, respectively. And vice versa if you're looking to prioritize read rate and accuracy over speed. For the full set of templates, please refer to [`EnumPresetTemplate`](../api-reference/enum-dbr-preset-template.md). Here is a quick example:

```js
componentDidMount() {
    ...
    (async () => {
        await this.reader.updateRuntimeSettings(EnumDBRPresetTemplate.VIDEO_SPEED_FIRST);
    })();
    ...
}
```

### Using the DBRRuntimeSettings interface

The SDK also supports a more granular control over the individual runtime settings rather than using a preset template. The main settings that you can control via this interface are which barcode formats to read, the expected number of barcodes to be read in a single image or frame, and the timeout. For more info on each, please refer to [`DBRRuntimeSettings`](../api-reference/interface-dbr-runtime-settings.md). Here is a quick example:

```js
componentDidMount() {
    (async () => {
        // Get the current runtime settings of the barcode reader.
        let settings = await this.reader.getRuntimeSettings();
        // Set the expected barcode count to 0 when you are not sure how many barcodes you are scanning.
        // Set the expected barcode count to 1 can maximize the barcode decoding speed.
        settings.expectedBarcodesCount = 0;
        // Set the barcode formats to read.
        settings.barcodeFormatIds = EnumBarcodeFormat.BF_ONED | EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_PDF417 | EnumBarcodeFormat.BF_DATAMATRIX;
        // Apply the new settings to the barcode reader.
        await this.reader.updateRuntimeSettings(settings);
    })();
}
```

### Customizing the scan region

You can also limit the scan region of the SDK so that it doesn't exhaust resources trying to read from the entire image or frame. In order to do this, we will need to use the [`Region`](../api-reference/interface-region.md) interface as well as the [`DynamsoftCameraView`](../api-reference/camera-view.md) component.

First, the region must be defined using the `Region` interface. In this example, we demonstrate how the region is first defined in the `render()` function and then assigned to the `scanRegion` parameter of the `DynamsoftCameraView` component:

```jsx
class App extends React.Component {
    render() {
        let barcode_text = "";
        // Define the scan region.
        let region = {
            regionTop: 30,
            regionLeft: 15,
            regionBottom: 70,
            regionRight: 85,
            regionMeasuredByPercentage: true
        }
        ...
        return (
            <DynamsoftCameraView
                style={
                    {
                        flex: 1
                    }
                }
                ref = {(ref)=>{this.scanner = ref}}
                overlayVisible={true}
                scanRegionVisible={true}
                scanRegion={region}
            >
            ...
            </DynamsoftCameraView>
        );
    }
}
```

## Licensing

- The `BarcodeReader` module of Dynamsoft Capture Vision needs a valid license to work.
- A one-day trial license is available by default for every new device to try Dynamsoft Capture Vision.
>- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=react_native&version=9){:target="_blank"} link.
- [Contact us](https://www.dynamsoft.com/company/contact/) to purchase a full license.
