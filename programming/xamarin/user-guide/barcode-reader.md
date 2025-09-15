---
layout: default-layout
title: Getting Started with Barcode Reader - Dynamsoft Capture Vision Xamarin.Forms Edition
description: This is the user guide of Dynamsoft Capture Vision Xamarin edition - Barcode Reader module
keywords: User guide, Barcode Reader, Xamarin, Capture Vision, Dynamsoft
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Guide of Dynamsoft Barcode Reader Xamarin
---

# Barcode Reader User Guide for Xamarin

In this guide, we will explore the Barcode Reader module of the Dynamsoft Capture Vision library for Xamarin.

## Table of Contents

- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Build Your Barcode Scanner App](#build-your-barcode-scanner-app)
  - [Set up Development Environment](#set-up-development-environment)
  - [Initialize the Project](#initialize-the-project)
  - [Include the Library](#include-the-library)
  - [Initialize IDCVBarcodeReader and IDCVCameraEnhancer](#initialize-idcvbarcodereader-and-idcvcameraenhancer)
  - [License Activation](#license-activation)
  - [Add a Button to Start Scanning](#add-a-button-to-start-scanning)
  - [Configure the CameraView](#configure-the-cameraview)
  - [Open the Camera and Start Barcode Decoding](#open-the-camera-and-start-barcode-decoding)
  - [Obtaining Barcode Results](#obtaining-barcode-results)
  - [Add Camera Permission](#add-camera-permission)
  - [Run the Project](#run-the-project)
- [Customizing the Barcode Reader](#customizing-the-barcode-reader)
  - [Using the Settings Templates](#using-the-settings-templates)
  - [Using the DBRRuntimeSettings Interface](#using-the-dbrruntimesettings-interface)
  - [Customizing the Scan Region](#customizing-the-scan-region)
- [Licensing](#licensing)

## System Requirements

### Xamarin

- NETStandard.Library 2.0+
- Xamarin.Forms 5.0.0.2478+
- Xamarin.Essentials: 1.3.1+ (1.4.0+ Recommended)

### Android

- Supported OS: **Android 5.0** (API Level 21) or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Android Studio 3.4+ (Android Studio 4.2+ recommended).
- JDK: 1.8+

### iOS

- Supported OS: **iOS 9.0** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 10 and above.

## Installation

In the **NuGet Package Manager>Manage Packages for Solution** of your project, search for **Dynamsoft.CaptureVision.Xamarin.Forms**. Select all the modules of your project and click **install**.

<div align="center">
    <p><img src="../assets/install-nuget.png" width="40%" alt="run"></p>
    <p>Run Your Project</p>
</div>

## Build Your Barcode Scanner App

Now you will learn how to create a simple barcode scanner using Dynamsoft Capture Vision Xamarin SDK.

>Note: You can get the full source code of a similar project: <a href="https://github.com/Dynamsoft/capture-vision-xamarin-forms-samples/tree/main/BarcodeReaderSimpleSample" target="_blank">Barcode Reader Simple Sample</a>.

### Set up Development Environment

If you are a beginner with Xamarin, please follow the guide on the <a href="https://learn.microsoft.com/en-us/xamarin/get-started/installation/" target="_blank">Xamarin official website</a> to set up the development environment.

### Initialize the Project

#### Visual Studio

1. Open the Visual Studio and select **Create a new project**.
2. Select **Mobile App (Xamarin.Forms)** and click **Next**.
3. Name the project **SimpleBarcodeScanner**. Select a location for the project and click **Create**.
4. Select **Blank** and click **Create**.

#### Visual Studio for Mac

1. Open Visual Studio and select **New**.
2. Select **Multiplatform > App > Blank App > C#** and click **Next**.
3. Name the project **SimpleBarcodeScanner** and click **Next**.
4. Select a location for the project and click **Create**.

### Include the Library

Add NuGet package **Dynamsoft.CaptureVision.Xamarin.Forms** to your project. You can view the [installation section](#installation) on how to add the library.

### Initialize IDCVBarcodeReader and IDCVCameraEnhancer

You have to initialize the following two interfaces to decode barcodes with the library.

- `IDCVBarcodeReader`: The interface that defines barcode decoding APIs and helps set up barcode decoding configurations.
- `IDCVCameraEnhancer`: The interface that defines camera controlling APIs and helps you to set up a camera module to capture the video stream.

In **App.xaml.cs**, add the following code to initialize the `IDCVBarcodeReader` and `IDCVCameraEnhancer` objects.

```c#
using DCVXamarin;

namespace SimpleBarcodeScanner
{
    public partial class App : Application
    {
        public static IDCVCameraEnhancer camera;
        public static IDCVBarcodeReader barcodeReader;
        public App(IDCVCameraEnhancer dce, IDCVBarcodeReader dbr)
        {
            InitializeComponent();
            camera = dce;
            barcodeReader = dbr;
            MainPage = new NavigationPage(new MainPage());
        }
    }
}
```

#### Implement the Interfaces for Android

Open the **MainActivity.cs** in **SimpleBarcodeScanner.Android** folder. Change the code of `LoadApplication` to:

```c#
using DCVXamarin.Droid;

namespace SimpleBarcodeScanner.Droid
{
    ...
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnCreate(Bundle savedInstanceState)
        {
            base.OnCreate(savedInstanceState);
            DCVCameraEnhancer dce = new DCVCameraEnhancer(context: this);
            DCVBarcodeReader dbr = new DCVBarcodeReader();
            LoadApplication(new App(dce, dbr));
            ...
        }
        ...
    }
}
```

#### Implement the Interfaces for iOS

Open the **AppDelegate.cs** in **SimpleBarcodeScanner.iOS** folder. Change the code of `LoadApplication` to:

```c#
using DCVXamarin.iOS;

namespace SimpleBarcodeScanner.iOS
{
    ...
    public partial class AppDelegate : global::Xamarin.Forms.Platform.iOS.FormsApplicationDelegate
    {
        public override bool FinishedLaunching(UIApplication app, NSDictionary options)
        {
            global::Xamarin.Forms.Forms.Init();
            DCVCameraEnhancer dce = new DCVCameraEnhancer();
            DCVBarcodeReader dbr = new DCVBarcodeReader();
            LoadApplication(new App(dce, dbr));
            return base.FinishedLaunching(app, options);
        }
    }
}
```

### License Activation

The barcode reading module of Dynamsoft Capture Vision needs a valid license to work. Please refer to the [Licensing](#licensing) section for more info on how to obtain a license.

Go back to **App.xaml.cs**. Add the following code to activate the license:

```c#
namespace SimpleBarcodeScanner
{
    // Add ILicenseVerificationListener to the class and implement LicenseVerificationCallback.
    public partial class App : Application, ILicenseVerificationListener
    {
        public App(IDCVCameraEnhancer dce, IDCVBarcodeReader dbr)
        {
            ...
            // Initialize the license of barcode reader module. Please note that the following license is a public trial.
            barcodeReader.InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", this);
            // You can add any extra barcode reader settings configurations after the license initialization
            ...
        }

        // Implement LicenseVerificationCallback to get message from the license server.
        public void LicenseVerificationCallback(bool isSuccess, string msg)
        {
            if (!isSuccess)
            {
                System.Console.WriteLine(msg);
            }
        }
    }
}

```

### Add a Button to Start Scanning

In the **MainPage.xaml**, add the following code:

```xml
<StackLayout>
    <Button x:Name="startScanning" Text="Start Scanning" HorizontalOptions="Center" VerticalOptions="CenterAndExpand" Clicked="OnStartScanningButtonClicked" />
</StackLayout>
```

In the **MainPage.xaml.cs**, add the following code:

```c#
async void OnStartScanningButtonClicked(object sender, EventArgs e)
{
    await Navigation.PushAsync(new ScanningPage());
}
```

### Configure the CameraView

Create a new Xamarin.Forms content page in the project and name it *ScanningPage*. In the **ScanningPage.xaml** add the `CameraView`:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:dynamsoft = "clr-namespace:DCVXamarin;assembly=DCVXamarin"
             x:Class="SimpleBarcodeScanner.ScanningPage">
    <ContentPage.Content>
        <StackLayout>
            <Label x:Name="barcodeResultLabel" Text="No Barcode detected"></Label>
            <!-- Add DCECameraView. -->
            <dynamsoft:DCVCameraView OverlayVisible="True"
                            HorizontalOptions="FillAndExpand"
                            VerticalOptions="FillAndExpand" >
            </dynamsoft:DCVCameraView>
        </StackLayout>
    </ContentPage.Content>
</ContentPage>
```

### Open the Camera and Start Barcode Decoding

In this section, we are going to add code to start barcode decoding in the **ScanningPage** of the project. Open the **ScanningPage.xaml.cs** and add the following code:

```c#
using DCVXamarin;

namespace SimpleBarcodeScanner
{
    public partial class ScanningPage : ContentPage
    {
        public ScanningPage()
        {
            InitializeComponent();
            // Bind the CameraEnhancer to the BarcodeReader so that it can continuously obtain video stream from the camera for barcode decoding.
            App.barcodeReader.SetCameraEnhancer(App.camera);
        }

        protected override void OnAppearing()
        {
            base.OnAppearing();
            // Open the camera the the view appears.
            App.camera.Open();
            // Start barcode decoding thread when the view appears.
            App.barcodeReader.StartScanning();
        }

        protected override void OnDisappearing()
        {
            base.OnDisappearing();
            // Close the camera the the view appears.
            App.camera.Close();
            // Stop barcode decoding thread when the view appears.
            App.barcodeReader.StopScanning();
        }
    }
}
```

### Obtaining Barcode Results

With the barcode decoding thread now configured, the library will start decoding from the video steam when the **ScanningPage** appears. You can use the interface `IBarcodeResultListener` to obtain the decoded `BarcodeResults`.

In **ScanningPage.xaml**, add a label for displaying the barcode results

```xml
<StackLayout>
    <Label x:Name="barcodeResultLabel" Text="No Barcode detected"></Label>
    ...
</StackLayout>
```

In **ScanningPage.xaml.cs**, add configurations of `IBarcodeResultListener`.

```c#
namespace SimpleBarcodeScanner
{
    // Add IBarcodeResultListener to your ScanningPage so that you can receive the barcode results.
    public partial class ScanningPage : ContentPage, IBarcodeResultListener
    {
        public ScanningPage()
        {
            ...
            App.barcodeReader.AddResultlistener(this);
        }
        ...
        // Implement the BarcodeResultCallback so that you can receive the barcode results when the barcodes are decoded.
        public void BarcodeResultCallback(int frameID, BarcodeResult[] barcodeResults)
        {
            // Here is an example code on how to display the barcode results on the view.
            string newBarcodeText = "";
            // The parameter 'barcodeResults' is an Array of BarcodeResult object.
            // Parse the 'barcodeResults' when it is not null.
            if (barcodeResults != null && barcodeResults.Length>0)
            {
                for (int i=0; i<barcodeResults.Length; i++)
                {
                    {
                        //The BarcodeText property of BarcodeResult is the string of barcode text result.
                        newBarcodeText += barcodeResults[i].BarcodeText;
                        newBarcodeText += "; ";
                    }
                }
                // On UI thread, refresh the previously prepared label with new barcode results.
                Device.BeginInvokeOnMainThread(()=> {
                    barcodeResultLabel.Text = newBarcodeText;
                });
            }
        }
    }
}
```

### Add Camera Permission

#### Android

Add the following code in **MainActivity.cs** for requesting camera permission on Android devices.

```c#
using Xamarin.Essentials;

namespace SimpleBarcodeScanner.Droid
{
    ...
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnCreate(Bundle savedInstanceState)
        {
            ...
            // Add camera permission.
            Permissions.RequestAsync<Permissions.Camera>();
        }
        public override void OnRequestPermissionsResult(int requestCode, string[] permissions, [GeneratedEnum] Android.Content.PM.Permission[] grantResults)
        {
            ...
            base.OnRequestPermissionsResult(requestCode, permissions, grantResults);
        }
    }
}
```

#### iOS

Add **Privacy - Camera Usage Description** and your message to the **info.plist** of your project.

### Run the Project

#### Run Android on Windows

Select **SimpleBarcodeScanner.Android** and select your device. Run the project.

<div align="center">
    <p><img src="../assets/xamarin-run.png" width="70%" alt="run"></p>
    <p>Run Your Project</p>
</div>

#### Run iOS & Android on macOS

1. Right click on the **SimpleBarcodeReader.iOS** or **SimpleBarcodeReader.Android** and select **Set As Startup Project**.
2. In the menu, select and click **Run > Start Debugging**.

## Customizing the Barcode Reader

### Using the Settings Templates

DBR offers several preset templates for different popular scenarios. For example, to prioritize speed over accuracy, you can use one of the speed templates and choose the corresponding template for images or video, and vice versa if you're looking to prioritize read rate and accuracy over speed. For the full set of templates, please refer to `EnumPresetTemplate`. Here is a quick example of prioritizing read rate for image-based decoding:

```c#
BarcodeReader.UpdateRuntimeSettings(EnumDBRPresetTemplate.IMAGE_READ_RATE_FIRST);
```

### Using the DBRRuntimeSettings Interface

The SDK also supports a more granular control over the individual runtime settings rather than using a preset template. The main settings that you can control via this interface are which barcode formats to read, the expected number of barcodes to be read in a single image or frame, and the timeout. For more info on each, please refer to `DBRRuntimeSettings`. Here is a quick example:

```c#
DBRRuntimeSettings settings = barcodeReader.GetRuntimeSettings();
settings.BarcodeFormatIds = EnumBarcodeFormat.BF_ONED;
settings.ExpectedBarcodeCount = 0;
settings.Timeout = 1000;
barcodeReader.UpdateRuntimeSettings(settings);
```

### Customizing the Scan Region

You can also limit the scan region of the SDK so that it doesn't exhaust resources trying to read from the entire image or frame. In order to do this, we will need to use the `Region` class as well as the `IDCVCameraEnhancer` interface.

How to set scan region:

- Define a `Region` object via class Region.
- Configure the value of `Region`.
- Assign the `Region` to the `ScanRegion` property of the `IDCVCameraEnhancer` object.

```c#
DCVXamarin.Region region = new DCVXamarin.Region();
region.RegionTop = 30;
region.RegionBottom = 70;
region.RegionLeft = 15;
region.RegionRight = 85;
region.RegionMeasuredByPercentage = 1;
camera.ScanRegion(region);
```

## Licensing

- The `BarcodeReader` module of Dynamsoft Capture Vision needs a valid license to work.
- A one-day trial license is available by default for every new device to try Dynamsoft Capture Vision.
>- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=xamarin&version=9){:target="_blank"} link.
- [Contact us](https://www.dynamsoft.com/company/contact/) to purchase a full license.
