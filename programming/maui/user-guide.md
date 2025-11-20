---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader for MAUI
description: This is the user guide of Dynamsoft Barcode Reader MAUI SDK.
keywords: user guide, maui
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---


# MAUI User Guide for Barcode Reader Integration

## Table of Contents

- [MAUI User Guide for Barcode Reader Integration](#maui-user-guide-for-barcode-reader-integration)
  - [Table of Contents](#table-of-contents)
  - [System Requirements](#system-requirements)
    - [.Net](#net)
    - [Android](#android)
    - [iOS](#ios)
  - [Installation](#installation)
    - [Visual Studio for Mac](#visual-studio-for-mac)
    - [Visual Studio for Windows](#visual-studio-for-windows)
  - [Build Your Barcode Scanner App](#build-your-barcode-scanner-app)
    - [Set up Development Environment](#set-up-development-environment)
    - [Initialize the Project](#initialize-the-project)
      - [Visual Studio](#visual-studio)
      - [Visual Studio for Mac](#visual-studio-for-mac-1)
    - [Include the Library](#include-the-library)
    - [Add Your Code for Barcode Scanning](#add-your-code-for-barcode-scanning)
    - [Configure the Camera Permission](#configure-the-camera-permission)
    - [Run the Project](#run-the-project)
  - [Customizing the Barcode Reader](#customizing-the-barcode-reader)
    - [Switching Preset Templates](#switching-preset-templates)
    - [Configuring the SimplifiedBarcodeReaderSettings](#configuring-the-simplifiedbarcodereadersettings)
    - [Customizing the Scan Region](#customizing-the-scan-region)
  - [Licensing](#licensing)

## System Requirements

### .Net

- .NET 8.0 and 9.0.

### Android

- Supported OS: **Android 5.0** (API Level 21) or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Visual Studio 2022 recommended.
- JDK: 1.8+

### iOS

- Supported OS: **iOS 13.0** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Visual Studio 2022 for Mac and Xcode 14.3+ recommended.

## Installation

### Visual Studio for Mac

In the **NuGet Package Manager>Manage Packages for Solution** of your project, search for **Dynamsoft.BarcodeReaderBundle.Maui**. Select Version **11.0.5200** and click **install**.

### Visual Studio for Windows

You need to add the library via the project file and complete additional steps for the installation.

1. Add the library in the project file:

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
        ...
        <ItemGroup>
            ...
            <PackageReference Include="Dynamsoft.BarcodeReaderBundle.Maui" Version="11.2.3000" />
        </ItemGroup>
    </Project>
    ```

2. Open the **Package Manager Console** and run the following commands:

    ```bash
    dotnet build
    ```

<div class="blockquote-note"></div>
>
> - Windows system have a limitation of 260 characters in the path. If you don't use console to install the package, you will receive error "Could not find a part of the path 'C:\Users\admin\.nuget\packages\dynamsoft.imageprocessing.ios\2.4.300\lib\net7.0-ios16.1\Dynamsoft.ImageProcessing.iOS.resources\DynamsoftImageProcessing.xcframework\ios-arm64\dSYMs\DynamsoftImageProcessing.framework.dSYM\Contents\Resources\DWARF\DynamsoftImageProcessing'"
> - The library only support Android & iOS platform. Be sure that you remove the other platforms like Windows, maccatalyst, etc.

## Build Your Barcode Scanner App

Now you will learn how to create a simple barcode scanner using Dynamsoft Barcode Reader MAUI SDK.

### Set up Development Environment

If you are a beginner with MAUI, please follow the guide on the <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation" target="_blank">.Net MAUI official website</a> to set up the development environment.

### Initialize the Project

#### Visual Studio

1. Open the Visual Studio and select **Create a new project**.
2. Select **.Net MAUI App** and click **Next**.
3. Name the project **ScanBarcodes**. Select a location for the project and click **Next**.
4. Select **.Net 9.0** and click **Create**.

#### Visual Studio for Mac

1. Open Visual Studio and select **New**.
2. Select **Multiplatform > App > .Net MAUI App > C#** and click **Continue**.
3. Select **.Net 9.0** and click **Continue**.
4. Name the project **ScanBarcodes** and select a location, click **Create**.

### Include the Library

View the [installation section](#installation) on how to add the library.

### Add Your Code for Barcode Scanning

1. Replace the **MainPage.xaml.cs** with the following code:

   ```csharp
   using Dynamsoft.BarcodeReaderBundle.Maui;
   
   namespace ScanBarcodes;
   public partial class MainPage : ContentPage
   {
   	public MainPage()
   	{
   		InitializeComponent();
   	}
   
   	private async void OnScanBarcode(object sender, EventArgs e)
       {
   		// Initialize the license.
           // The license string here is a trial license. Note that network connection is required for this license to work.
           // You can request an extension via the following link: https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=samples&package=mobile
           var config = new BarcodeScannerConfig("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
           var result = await BarcodeScanner.Start(config);
           var message = result.ResultStatus switch
           {
               EnumResultStatus.Finished => string.Join("\n",
                   result.Barcodes!.Select(item => item.FormatString + "\n" + item.Text)),
               EnumResultStatus.Canceled => "Scanning canceled",
               EnumResultStatus.Exception => result.ErrorString,
               _ => throw new ArgumentOutOfRangeException()
           };
   		label.Text = message;
       }
   }
   ```

2. Replace the **MainPage.xaml** with the following code:

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
                xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                x:Class="ScanBarcodes.MainPage">
   
       <Grid>
           <Grid.RowDefinitions>
               <RowDefinition Height="*" />
               <RowDefinition Height="Auto" />
               <RowDefinition Height="*" />
           </Grid.RowDefinitions>
   
           <Label
               Grid.Row="1"
               x:Name="label"
               Text="Click button to Scan a Barcode"
               Style="{StaticResource SubHeadline}"
               SemanticProperties.HeadingLevel="Level2"
               SemanticProperties.Description="Click button to Scan a Barcode"
               HorizontalOptions="Center"
               VerticalOptions="Center" />
   
           <Button
               Grid.Row="2"
               x:Name="ScanBtn"
               Text="Scan a Barcode"
               SemanticProperties.Hint="Click button to Scan a Barcode"
               Clicked="OnScanBarcode"
               HorizontalOptions="Center"
               VerticalOptions="Start"
               Margin="0,30" />
       </Grid>
   </ContentPage>
   ```

### Configure the Camera Permission

Open the **Info.plist** file under the **Platforms/iOS/** folder (Open with XML Text Editor). Add the following lines to request camera permission on iOS platform:

```xml
<key>NSCameraUsageDescription</key>
<string>The sample needs to access your camera.</string>
```

### Run the Project

Select your device and run the project.

<div class="blockquote-note"></div>
> If you are running Android only on Visual Studio Windows, please manually exclude iOS and Windows platforms. Otherwise, the Visual Studio will report type or namespace not found errors.

![Exclude iOS and Windows from targets](../assets/maui-exclude.png)

## Licensing

- A one-day trial license is available by default for every new device to try Dynamsoft Barcode Reader SDK.
- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&package=mobile&utm_source=docs){:target="_blank"} link.
- [Contact us](https://www.dynamsoft.com/company/contact/){:target="_blank"} to purchase a full license.
