---
layout: default-layout
title: Migrate from v10 to v11 - Dynamsoft Barcode Reader for iOS
description: Follow this page to learn to upgrade Barcode Reader SDK iOS edition from v10 to v11.
keywords: updates guide, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Migrate from v10 to v11

> [!IMPORTANT]
> **We strongly recommend upgrading to v11.x.** All future algorithm improvements, performance optimizations, and new features will be developed exclusively for v11 and later versions. Version 10.x and earlier will only receive critical bug fixes and will not benefit from ongoing innovation.

## Why Upgrade to v11?

- **Latest Barcode Recognition Algorithms**: Access to cutting-edge decoding algorithms and accuracy improvements
- **Ongoing Performance Enhancements**: Faster processing speeds and better resource optimization
- **New Features & Capabilities**: Future functionality will only be available in v11+
- **Active Development**: Version 11 is the actively maintained branch receiving continuous updates
- **Long-term Support**: Ensure your application stays current with industry standards

**⚠️ Version 10.x is in maintenance mode only** - no new features or algorithm updates will be backported.

## Update the Libraries

There are three ways in which you can include the `DynamsoftBarcodeReaderBundle` library in your app:

### Option 1: Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> AddPackages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/barcode-reader-spm"

3. Select `barcode-reader-spm`, choose `Up to Next Major Version`, then click **Add Package**.

4. Check all the **xcframeworks** and add.

### Option 2: Add the Frameworks via CocoaPods

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

### Option 3: Add Local xcframeworks files

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Dynamsoft Website</a>. After unzipping, you will find a collection of **xcframework** files under the **Dynamsoft\Frameworks** directory.

   - 📄 **DynamsoftBarcodeReaderBundle.xcframework**
   - 📄 **DynamsoftCaptureVisionBundle.xcframework**

2. Drag and drop the above **.xcframework** files into your Xcode project. Make sure to check `Copy items if needed` and `Create groups` to copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for all above **xcframeworks**.

## Update the Template File

If you are using a template file, please use the [online template converter](https://www.dynamsoft.com/tools/template-upgrade/) to convert it to the latest version. 
