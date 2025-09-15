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

- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Build Your Barcode Scanner App](#build-your-barcode-scanner-app)
  - [Set up Development Environment](#set-up-development-environment)
  - [Initialize the Project](#initialize-the-project)
  - [Include the Library](#include-the-library)
  - [Configure the Barcode Reader](#configure-the-barcode-reader)
  - [Rendering the UI](#rendering-the-ui)
  - [Configure Camera Permissions](#configure-camera-permissions)
  - [Run the Project](#run-the-project)
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

Let's now walk through the steps needed in order to create a simple barcode scanning React Native project using the Dynamsoft Capture Vision SDK.

>Note: If you would like the full source code of the sample that we will walk through, please visit:  [Barcode Reader Simple Sample](https://github.com/Dynamsoft/capture-vision-react-native-samples/tree/v1.1.14/BarcodeReaderSimpleSample)

### Set up Development Environment

If you are a beginner with React Native, please follow the guide on the <a href="https://reactnative.dev/docs/environment-setup" target="_blank">React Native official website</a> to set up the development environment.

### Initialize the Project

Create a new React Native project.

```bash
npx react-native init SimpleBarcodeScanner
```

>Note: This sample uses React 18.3.1 and React Native 0.75.2. We recommend using the latest of these libraries to make the process as easy as possible.

### Include the Library

First thing we need to do is to add the SDK to the new project. There are two ways in which you can add the SDK

#### via package.json

All you need to do is to open the **package.json** which already should be populated with all the core packages needed to run a React Native project. Once that is open, simply add the `dynamsoft-capture-vision-react-native` package to the dependencies as such

```json
"dynamsoft-capture-vision-react-native": "^1.1.17",
```

Once you're done, save the file and run `npm install` or `yarn install` (depending on your preferred package manager) in the project's root directory.

#### via command-line

You can also install the package directly from the command-line as such

- **yarn**

  ```bash
  yarn add dynamsoft-capture-vision-react-native
  ```

- **npm**

  ```bash
  npm install dynamsoft-capture-vision-react-native
  ```

For iOS, you must install the necessary native frameworks from cocoapods by running the `pod install` command as below:

```bash
cd ios
```

```bash
pod install
```

### Configure the Barcode Reader

Now that the pckage is added, it's time to start building the barcode reader component using the DCV API. So the first thing that we will do is create a file named *BarcodeScanner.tsx* which will represent the component that we are going to create and use in the main *App.tsx*. 

#### Imports

Let's first start by importing all of the modules that we need

```ts
import React from 'react';
import {
  DCVCameraView,
  BarcodeResult,
  EnumTorchState,
  DCVBarcodeReader,
} from 'dynamsoft-capture-vision-react-native';
import {Button, Modal, StyleSheet, Text, TouchableOpacity, View} from 'react-native';
import {
  EnumBarcodeFormat,
  EnumDBRPresetTemplate,
} from 'dynamsoft-capture-vision-react-native/js/BarcodeSettings';
// @ts-ignore
import {TorchButton} from 'dynamsoft-capture-vision-react-native/js/CameraSettings';
```

>Note: Certain modules such as `EnumBarcodeFormat` and `TorchButton` from  dynamsoft-capture-vision-react-native need to be imported from the specific folders that they reside in.

#### Creating the BarcodeScanner.tsx

Next up, we will walk through each of the functions and objects in *BarcodeScanner.tsx* and how they are used in the BarcodeScanner class. Before we start implementing the BarcodeScanner class, let's define a couple of functions and the *option* struct which will go right after the import section

```ts
const mergeResultsText = (results: BarcodeResult[]) => {
  let str = '';
  if (results && results.length > 0) {
    for (let i = 0; i < results.length; i++) {
      str +=
        results[i].barcodeFormatString + ': ' + results[i].barcodeText + ' \n';
    }
  } else {
    str = 'No barcode detected.';
  }
  return str;
};

const initSettingForVideo = async (reader: DCVBarcodeReader) => {
  await reader.resetRuntimeSettings();

  await reader.updateRuntimeSettings(EnumDBRPresetTemplate.VIDEO_READ_RATE_FIRST);

  let settings = await reader.getRuntimeSettings();

  // Set the expected barcode count to 0 when you are not sure how many barcodes you are scanning.
  // Set the expected barcode count to 1 can maximize the barcode decoding speed.
  //settings.expectedBarcodesCount = 0;

  // Set the barcode format to read.
  settings.barcodeFormatIds =
    EnumBarcodeFormat.BF_ONED |
    EnumBarcodeFormat.BF_QR_CODE |
    EnumBarcodeFormat.BF_PDF417;

  // Apply the new runtime settings to the barcode reader.
  await reader.updateRuntimeSettings(settings);
};
```

- *mergeResultsText*: The purpose of this function is pretty simple - should there be multiple barcode results (meaning there are multiple barcodes in the frame or on the image), this function concatenates them all, with each result being on a separate line. This way, the user sees all of the barcode results at once in the results area.

- *initSettingForVideo*: This function configures the Barcode Reader settings when the user is live video decoding, which is the core use case of this sample. By default, the sample uses the VIDEO_READ_RATE_FIRST preset template. Afterwards, we define the barcode format(s) that we want the SDK to pick up. This can be changed to which set of formats you want the app to support.
 
Next in `App.tsx`, let's now implement the main BarcodeScanner class. Similar to the section above, we will post the entire code block of this class below and break down each of the functions that make it up.

```ts
class BarcodeScanner extends React.Component<any, any> {
  reader: DCVBarcodeReader | null = null;
  state = {
    resultsText: '',
    isVisible: false,
    modalText: '',
  };

  async componentDidMount() {
    // Create a barcode reader instance.
    this.reader = await DCVBarcodeReader.createInstance();

    await initSettingForVideo(this.reader);

    this.reader.addResultListener((results: BarcodeResult[]) => {
      // Update the newly detected barcode results to the state.
      if (!this.ifDecodingFile) {
        this.setState({resultsText: mergeResultsText(results)});
      }
    });

    // Enable video barcode scanning.
    // If the camera is opened, the barcode reader will start the barcode decoding thread when you triggered the startScanning.
    // The barcode reader will scan the barcodes continuously before you trigger stopScanning.
    this.reader.startScanning();
  }

  async componentWillUnmount() {
    // Stop the barcode decoding thread when your component is unmount.
    await this.reader?.stopScanning();
    // Remove the result listener when your component is unmount.
    this.reader?.removeAllResultListeners();
  }

}
```

- *componentDidMount*: This is where the majority of the work goes. First, we start by creating the Barcode Reader instance, followed by configuring the settings via the *initSettingForVideo* method. Each Barcode Reader instance must have an attached results listener to deal with any incoming results - and that is done via the *addResultListener* method. Once all that setup is done, we call the *startScanning* method to open the camera and start barcode reading. Lastly, we set up the navigation options for the open camera page so that the user can go back to the home screen or open the photo library if needed.

- *componentWillUnmount*: Now we need to configure what happens when the component unmounts. The main things that we need to do here is to call stopScanning followed by detaching any result listeners from the Barcode Reader instance to make sure that the resources are released properly.

### Rendering the UI

Now that we have configured the Barcode Reader, it is time to set up the UI that the Barcode Reader will occupy. `DCVCameraView` is the class that represents the UI component and so we will set it up in the `render` function of the `BarcodeScanner` class that we just created.

```ts
render() {
    return (
      <DCVCameraView
        style={styles.container}
        overlayVisible={true}
        torchButton={
          {
            visible: true,
          } as TorchButton
        }
        torchState={EnumTorchState.OFF}>
        <Text style={styles.bottomText}>{this.state.resultsText}</Text>
      </DCVCameraView>
    );
  }
```

While the snippet above does show a very basic version of the UI, it is indeed cuztomizable and so you can add React Native elements in there to make it look how you want it. In this simple snippet, we configure the `DCVCameraView` properties, but we do not set a scan region (which you can learn to do [here](#customizing-the-scan-region)). If no region is set, the entire video frame will be the scan region by default. The other elements that are included in there are used to display the barcode result(s) as they come in.

### Configure Camera Permissions

You need to set the *Privacy - Camera Usage Description* field in the `Info.plist` file for iOS. If this property is not set, the iOS application will fail at runtime. In order to set this property, you might need to use Xcode and open the corresponding `.xcworkspace` located in the `ios` folder. Once open, you can edit the `Info.plist` to include this property.

>Note: If there is no *.xcworkspace* in the ios folder, make sure to run `pod install` in the ios folder so that native iOS cocoapods are installed and that will create the *.xcworkspace* file.

### Run the Project

#### Run Android on Windows

In the command line interface (Powershell recommended), go to your project folder and run the following command:

```bash
npx react-native run-android
```

>Note: If you would like to make sure that the project is deployed to a physical Android device that is connected to your computer, you should use the following command: `npx react-native run-android --deviceId=<insert device ID here>`
>
>To find the device ID of your connected Android phone, you will need to use the *adb* library. Once you have *adb* installed and configured, you simply need to run `adb devices` in the terminal to output a list of the Android devices connected to your machine as well as their corresponding IDs.

#### Run iOS on macOS

In the terminal, go to the project folder in your project:

```bash
npx react-native run-ios
```

> Note:
>
>- The application needs to run on a physical device rather than a simulator as it requires the use of the camera. If you try running it on a simulator, you will most likely run into a number of errors/failures.
>- On iOS, in order to run the React Native app on a physical device you will need to install the [`ios-deploy`](https://www.npmjs.com/package/ios-deploy) library. Afterwards, you can run the react native app from the terminal as such `npx react-native run-ios --device` assuming it's the only device connected to the Mac.
>- Alternatively on iOS, you can simply open the `.xcworkspace` of the project found in the `ios` folder using Xcode and run the sample on your connected iOS device from there. The advantage that this offers is that it is easier to deal with the developer signatures for deployment in there.

>Note: You can get the full source code of the project above:  [Barcode Reader Simple Sample](https://github.com/Dynamsoft/capture-vision-react-native-samples/tree/v1.1.14/BarcodeReaderSimpleSample)

## Customizing the Barcode Reader

There are several ways in which you can customize the Barcode Reader - but what they all have in common is that each involves the [`updateRuntimeSettings`](../api-reference/barcode-reader.md#updateruntimesettings) method. There are currently three methods in which you can update the runtime settings.

### Using the settings templates

Dynamsoft Barcode Reader offers several preset templates for different popular scenarios. To prioritize speed over accuracy, then you will want to use one of the speed templates, choosing the corresponding template for images or video, respectively. And vice versa if you're looking to prioritize read rate and accuracy over speed. For the full set of templates, please refer to [`EnumPresetTemplate`](../api-reference/enum-dbr-preset-template.md). Here is a quick example:

```ts
componentDidMount() {
  ...
  (async () => {
      await reader.updateRuntimeSettings(EnumDBRPresetTemplate.VIDEO_SPEED_FIRST);
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
      await reader.updateRuntimeSettings(settings);
  })();
}
```

### Customizing the scan region

You can also limit the scan region of the SDK so that it doesn't exhaust resources trying to read from the entire image or frame. In order to do this, we will need to use the [`Region`](../api-reference/interface-region.md) interface as well as the [`DCVCameraView`](../api-reference/camera-view.md) component.

First, the region must be defined using the `Region` interface. In this example, we demonstrate how the region is first defined in the `render()` function and then assigned to the `scanRegion` parameter of the `DCVCameraView` component. Please note that in order to show the region, `scanRegionVisible` must be set to true:

```jsx
class App extends React.Component {
    render() {
      // Define the scan region.
      let region = {
          regionTop: 30,
          regionLeft: 15,
          regionBottom: 70,
          regionRight: 85,
          regionMeasuredByPercentage: true
      }

      return (
        <DCVCameraView
          style={styles.container}
          overlayVisible={true}
          scanRegion={region}
          scanRegionVisible={true}
          torchButton={
            {
              visible: true,
            } as TorchButton
          }
          torchState={EnumTorchState.OFF}>
          <Text style={styles.bottomText}>{this.state.resultsText}</Text>
        </DCVCameraView>
      );
        
    }
}
```

## Licensing

- The `BarcodeReader` module of Dynamsoft Capture Vision needs a valid license to work.
- A one-day trial license is available by default for every new device to try Dynamsoft Capture Vision.
>- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=react-native&version=9){:target="_blank"} link.
- [Contact us](https://www.dynamsoft.com/company/contact/) to purchase a full license.
