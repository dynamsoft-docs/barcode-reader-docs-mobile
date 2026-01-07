---
layout: default-layout
title: How to update - Dynamsoft Barcode Reader for iOS
description: Follow the upgrade instructions to learn to upgrade Barcode Reader SDK iOS edition from 10 to 11.
keywords: updates guide, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
pageStartVer: 10.0
---

# How to Upgrade

## From Version 10.x to 11.x

### Update the Libraries

There are three ways in which you can include the `DynamsoftBarcodeReaderBundle` library in your app:

#### Option 1: Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> AddPackages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/barcode-reader-spm"

3. Select `barcode-reader-spm`, choose `Up to Next Major Version`, then click **Add Package**.

4. Check all the **xcframeworks** and add.

#### Option 2: Add the Frameworks via CocoaPods

1. Add the frameworks in your **Podfile**, replace `TargetName` with your real target name.

   ```sh
   target 'ScanSingleBarcode' do
      use_frameworks!

   pod 'DynamsoftBarcodeReaderBundle','{version-number}'

   end
   ```

   <div class="blockquote-note"></div>
   > Please view [user guide](user-guide.md#option-1-add-the-library-via-maven) for the correct version number.


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

### Update the Template File

You can use the template converter to upgrade your template. View the [online template converter](https://www.dynamsoft.com/tools/template-upgrade/)

## From version 9.x or earlier

Dynamsoft Barcode Reader SDK has been refactored to integrate with DynamsoftCaptureVision (DCV) architecture since version 10. To upgrade from version 9.x or earlier to 11.x, we recommend you to follow the [User Guide](user-guide.md) and re-write your codes. This section highlights only the key changes and necessary actions for upgrading the SDK.
