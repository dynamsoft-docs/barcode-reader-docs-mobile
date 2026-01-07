---
layout: default-layout
title: How to update - Dynamsoft Barcode Reader for MAUI
description: Follow the upgrade instructions to learn to upgrade Barcode Reader SDK MAUI edition from 10 to 11.
keywords: updates guide, MAUI
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
pageStartVer: 10.0
---

# How to Upgrade

## From Version 10.x to 11.x

### Update the Libraries

#### Visual Studio for Mac

In the **NuGet Package Manager>Manage Packages for Solution** of your project, search for **Dynamsoft.BarcodeReaderBundle.Maui**. Select the latest version and click **install**.

#### Visual Studio for Windows

You need to add the library via the project file and complete additional steps for the installation.

1. Add the library in the project file:

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
        ...
        <ItemGroup>
            ...
            <PackageReference Include="Dynamsoft.BarcodeReaderBundle.Maui" Version="{version-number}" />
        </ItemGroup>
    </Project>
    ```

2. Open the **Package Manager Console** and run the following commands:

    ```bash
    dotnet build
    ```

    <div class="blockquote-note"></div>
    > 
    > - Please view [user guide](user-guide.md#option-1-add-the-library-via-maven) for the correct version number.
    > - Windows system have a limitation of 260 characters in the path. If you don't use console to install the package, you will receive error "Could not find a part of the path 'C:\Users\admin\.nuget\packages\dynamsoft.imageprocessing.ios\2.4.300\lib\net7.0-ios16.1\Dynamsoft.ImageProcessing.iOS.resources\DynamsoftImageProcessing.xcframework\ios-arm64\dSYMs\DynamsoftImageProcessing.framework.dSYM\Contents\Resources\DWARF\DynamsoftImageProcessing'"
    > - The library only support Android & iOS platform. Be sure that you remove the other platforms like Windows, maccatalyst, etc.

### Update the Template File

You can use the template converter to upgrade your template. View the [online template converter](https://www.dynamsoft.com/tools/template-upgrade/)

## From version 9.x or earlier

Dynamsoft Barcode Reader SDK has been refactored to integrate with DynamsoftCaptureVision (DCV) architecture since version 10. To upgrade from version 9.x or earlier to 11.x, we recommend you to follow the [User Guide](user-guide.md) and re-write your codes. This section highlights only the key changes and necessary actions for upgrading the SDK.
