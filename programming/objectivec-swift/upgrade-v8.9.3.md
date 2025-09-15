---
layout: default-layout
title: How to Upgrade - Dynamsoft Barcode Reader for iOS
description: Follow the upgrade instructions to learn to upgrade Barcode Reader SDK iOS edition from version 7.x & 8.0 to version 8.x with simple steps.
keywords: How to upgrade, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
pageStartVer: 8.0
permalink: /programming/objectivec-swift/upgrade-v8.9.3.html
---

# How to Upgrade

## From Version 8.0 to 8.x

You need to replace the old `DynamsoftBarcodeReader.framework` file with the one in the latest version. Download the latest version [here](https://www.dynamsoft.com/Downloads/Dynamic-Barcode-Reader-Download.aspx). You could also download it via terminal `pod install 'DynamsoftBarcodeReader'`. For v8.9 or higher v8.x versions, you have to include `DynamsoftCameraEnhancer.framework` as well.

## From Version 7.x to 8.x

You need to replace the old `DynamsoftBarcodeReader.framework` file with the one in the latest version. Download the latest version [here](https://www.dynamsoft.com/Downloads/Dynamic-Barcode-Reader-Download.aspx).

Your previous SDK license for version 7.x is not compatible with version 8.x. Please [contact us](https://www.dynamsoft.com/Company/Contact.aspx) to upgrade your license.

In v8.0, we introduced a new license tracking mechanism, <a href="https://www.dynamsoft.com/license-tracking/docs/about/index.html" target="_blank">License 2.0</a>.

If you wish to use License 2.0, please refer to [this article]({{ site.license_activation }}set-full-license.html) to set the license.

After you upgraded your license to version 8.x:

- If you were using `initWithLicense`, please replace the old license with the newly generated one.

- If you were using `initWithLicenseFromServer` to connect to the Dynamsoft server for license verification, then no need to change the license key. But please make sure the device has an Internet connection.

## From Version 6.x to 8.x

We made some structural updates in the new version. To upgrade from 6.x to 8.x, we recommend you to review our sample code and re-write the barcode scanning module.
