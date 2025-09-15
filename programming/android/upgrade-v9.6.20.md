---
layout: default-layout
title: How to Upgrade to 9.x - Dynamsoft Barcode Reader for Android
description: Update your Barcode Reader SDK Android edition to version 9.x along with your license activation code, decoding code, and default settings.
keywords: updates guide, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
pageStartVer: 9.0
permalink: /programming/android/upgrade-v9.6.20.html
---

# How to Upgrade

## From Version 8.x to 9.x

### Update the SDK to 9.x Version

- Local Dependency
  - If you are referencing only `DynamsoftBarcodeReader` SDK, replace the old `DynamsoftBarcodeReaderAndroid.aar` file with the latest version.

  - If you are referencing both `DynamsoftBarcodeReader` and `DynamsoftCameraEnhancer` SDK, please replace the old `DynamsoftBarcodeReaderAndroid.aar` and `DynamsoftCameraEnhancerAndroid.aar` files with the latest version.

- Remote Dependency(Maven)
  - If you are referencing only `DynamsoftBarcodeReader` SDK, update the version of `DynamsoftBarcodeReader` to the latest version in the `app\build.gradle`.
    ```groovy
    dependencies {
        implementation 'com.dynamsoft:dynamsoftbarcodereader:{version-number}@aar'
    }
    ```
    >Note:Please replace {version-number} with the correct version numbers.

  - If you are referencing both `DynamsoftBarcodeReader` and `DynamsoftCameraEnhancer` SDK, update the version of `DynamsoftBarcodeReader` and `DynamsoftCameraEnhancer` to the latest version in the `app\build.gradle`.
    ```groovy
    dependencies {
        implementation 'com.dynamsoft:dynamsoftbarcodereader:{version-number}@aar'
        implementation 'com.dynamsoft:dynamsoftcameraenhancer:{version-number}@aar'
    }
    ```
    >Note:Please replace {version-number} with the correct version number.


### Update the License Activation Code

Starting with 9.0, we unify the API for setting offline and online licenses.

- Java code in 8.x:

```java
BarcodeReader reader = new BarcodeReader();
// offline license
reader.initLicense("t0260NwAAAHV***************");
```

or

```java
BarcodeReader reader = new BarcodeReader();
DMDLSConnectionParameters dbrParameters = new DMDLSConnectionParameters();
dbrParameters.organizationID = "Your Organization Id";
// online license
reader.initLicenseFromLTS(dbrParameters, new DBRLTSLicenseVerificationListener(){
    //...
});
```

Please replace your license activation code with the following code. You can get the `3.0 license` from [customer portal-->License detail](https://www.dynamsoft.com/customer/index){:target="_blank"}.

- Java code in 9.x:

```java
BarcodeReader.initLicense("Put your 3.0 license", new DBRLicenseVerificationListener() {
    @Override
    public void DBRLicenseVerificationCallback(boolean isSuccess, Exception error) {
        if(!isSuccess){
            error.printStackTrace();
        }
    }
});
```

> Note:  
>
> 1.The following license activation method are removed, you should make the changes in 9.x upgrade:
> - `initLicenseFromLTS`
>
> 2.The following license activation methods are deprecated, they will be removed in version 10.0. We recommend that you upgrade to the new license API, but this is optional during the upgrade to 9.x.:
>  
> - `initLicenseFromDLS`
> - `initLicenseFromServer`
> - `initLicenseFromLicenseContent`


### Update the default runtime settings

In 9.0, the default preset template `EnumPresetTemplate.DEFAULT` will be changed to `EnumPresetTemplate.VIDEO_SINGLE_BARCODE` internally to better suit mobile scenarios. We also added template `EnumPresetTemplate.IMAGE_DEFAULT` to store the legacy configurations of `EnumPresetTemplate.DEFAULT`.

If the default template is not specified in the previous code (the default template is still used internally) or the default template is used explicitly, and you want to keep the original running logic, you need to call the following function after creating the barcode reader instance:

```java
BarcodeReader barcodereader = new BarcodeReader();

// add the following code to change to the legacy default settings
barcodereader.updateRuntimeSettings(EnumPresetTemplate.IMAGE_DEFAULT);

// change the settings based on the legacy default template...

```

### Update the Video Barcode Decoding Code

Some of the legacy video barcode decoding methods are removed. Make sure to change your code if you were using the following APIs:

- Legacy Frame Decoding APIs:
  - Class `FrameDecodingParameters`
  - interface `ErrorCallback`
  - `BarcodeReader.startFrameDecoding`
  - `BarcodeReader.startFrameDecodingEx`
  - `BarcodeReader.appendFrame`
  - `BarcodeReader.setErrorCallback`
  - `BarcodeReader.stopFrameDecoding`
  - `BarcodeReader.initFrameDecodingParameters`
  - `BarcodeReader.getLengthOfFrameQueue`
  
- Legacy Camera Enhancer supporting APIs
  - Class `DCESettingParameters`
  - `BarcodeReader.SetCameraEnhancerParam`
  - `BarcodeReader.StartCameraEnhancer`
  - `BarcodeReader.StopCameraEnhancer`
  - `BarcodeReader.PauseCameraEnhancer`
  - `BarcodeReader.ResumeCameraEnhancer`

> Note:  
>
> - If you are upgrading from v8.9.0 or higher versions, you might not need to make any changes on video barcode decoding APIs.


## From version 7.x to 9.x

We made some structural updates in the new version. To upgrade from 7.x to 9.x, we recommend you to review our sample code and re-write the barcode scanning module.
