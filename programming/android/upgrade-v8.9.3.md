---
layout: default-layout
title: How to update - Dynamsoft Barcode Reader for Android
description: Follow the upgrade instructions to learn to upgrade Barcode Reader SDK Android edition from version 7.x & 8.0 to version 8.x with simple steps.
keywords: updates guide, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
pageStartVer: 8.0
permalink: /programming/android/upgrade-v8.9.3.html
---

# How to Upgrade

## From Version 8.0 to 8.x

### Update the SDK

Replace the old `DynamsoftBarcodeReaderAndroid.aar` file with the one in the latest version. If you are using Maven, then change the version number in the `app\build.gradle` file.

### API Changes

Change Name of Import from `import com.dynamsoft.barcode.***;` to `import com.dynamsoft.dbr.***;`, like this:

Change:

```java
import com.dynamsoft.barcode.BarcodeReader;
import com.dynamsoft.barcode.EnumBarcodeFormat;
import com.dynamsoft.barcode.EnumImagePixelFormat;
import com.dynamsoft.barcode.EnumIntermediateResultSavingMode;
import com.dynamsoft.barcode.EnumIntermediateResultType;
import com.dynamsoft.barcode.EnumBarcodeFormat_2;
import com.dynamsoft.barcode.EnumConflictMode;
import com.dynamsoft.barcode.FrameDecodingParameters;
import com.dynamsoft.barcode.IntermediateResult;
import com.dynamsoft.barcode.LocalizationResult;
import com.dynamsoft.barcode.Point;
import com.dynamsoft.barcode.PublicRuntimeSettings;
import com.dynamsoft.barcode.TextResult;
import com.dynamsoft.barcode.TextResultCallback;
```

to:

```java
import com.dynamsoft.dbr.BarcodeReader;
import com.dynamsoft.dbr.EnumBarcodeFormat;
import com.dynamsoft.dbr.EnumImagePixelFormat;
import com.dynamsoft.dbr.EnumIntermediateResultSavingMode;
import com.dynamsoft.dbr.EnumIntermediateResultType;
import com.dynamsoft.dbr.EnumBarcodeFormat_2;
import com.dynamsoft.dbr.EnumConflictMode;
import com.dynamsoft.dbr.FrameDecodingParameters;
import com.dynamsoft.dbr.IntermediateResult;
import com.dynamsoft.dbr.LocalizationResult;
import com.dynamsoft.dbr.Point;
import com.dynamsoft.dbr.PublicRuntimeSettings;
import com.dynamsoft.dbr.TextResult;
import com.dynamsoft.dbr.TextResultCallback;
```

## From Version 7.x to 8.x

You need to replace the old `DynamsoftBarcodeReaderAndroid.aar` file with the one in the latest version. Download the latest version [here](https://www.dynamsoft.com/Downloads/Dynamic-Barcode-Reader-Download.aspx).

Your previous SDK license for version 7.x is not compatible with version 8.x. Please [contact us](https://www.dynamsoft.com/Company/Contact.aspx) to upgrade your license.

In v8.0, we introduced a new license tracking mechanism, <a href="https://www.dynamsoft.com/license-tracking/docs/about/index.html" target="_blank">License 2.0</a>.


If you wish to use License 2.0, please refer to [this article]({{ site.license_activation }}set-full-license.html) to set the license.

After you upgraded your license to version 8.x:

- If you were using `initLicense`, please replace the old license with the newly generated one.

- If you were using `initLicenseFromServer` to connect to the Dynamsoft server for license verification, then no need to change the license key. But please make sure the device has an Internet connection.

## From Version 6.x to 8.x

We made some structural updates in the new version. To upgrade from 6.x to 8.x, we recommend you to review our sample code and re-write the barcode scanning module.
