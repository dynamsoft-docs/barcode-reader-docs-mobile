---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader for Android
description: This is the user guide of Dynamsoft Barcode Reader for Android SDK.
keywords: user guide, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/android/user-guide-v8.4.0.html
---


# User Guide for Android Edition

## System Requirements

- Operating systems:
  - Supported OS: Android 5 or higher (Android 7 or higher recommended)
  - Supported ABI: armeabi-v7a, arm64-v8a, x86 and x86_64

## Installation

### Option 1: Download from website

To install Dynamsoft Barcode Reader for Android on your development machine, you can download the SDK from the [Dynamsoft website](https://www.dynamsoft.com/Downloads/Dynamic-Barcode-Reader-Download.aspx) and unzip `dbr-android-{version-number}.zip`.

After decompression, you can find samples in the **DBRSamples** folder under the **dbr-android-{version-number}** folder.

### Option 2: Build with Maven

You can add Dynamsoft Barcode Reader like below:

1. Add download URL in your project's `build.gradle`.

   ```groovy
    allprojects {
      repositories {
         google()
         jcenter()
         maven {
            url "http://download2.dynamsoft.com/maven/dbr/aar"
         }
      }
   }
   ```

2. Implement Dynamsoft Barcode Reader at dependencies in your module's `build.gradle`.

   ```groovy
   implementation 'com.dynamsoft:dynamsoftbarcodereader:{version-number}@aar'
   ```

   Please replace `{version-number}` with the correct version number, e.g.

   ```groovy
   implementation 'com.dynamsoft:dynamsoftbarcodereader:{version-number}@aar'
   ```

## Getting Started: HelloWorld

1. Create a new Android project in Android Studio.
2. Import the `DynamsoftBarcodeReaderAndroid.aar` package into the new project. You can manually import the `.aar` file or use maven import.

   To manually import the `.aar` :

      i. Decompress the dbr-android-{version number}.zip file and you will find DynamsoftBarcodeReaderAndroid.aar in the decompressed folder.
      ii. Put the .aar file under the directory libs in the project.
      iii. In the project, open build.gradle(Module: app) and add the following code:

      ```groovy
      repositories {
         flatDir {
            dirs 'libs'
         }
      }
      ```

      ii. Add `.aar` reference in the dependencies:

      ```groovy
      implementation(name: 'DynamsoftBarcodeReaderAndroid', ext: 'aar')
      ```

      iii. Click **Sync Now**. After the synchronization completes, `DynamsoftBarcodeReaderAndroid.aar` is added to the project.

   Or you can use maven import the `.aar` file into the project.

      i. In the new project, open `build.gradle(module:app)` and add the following code:

      ```groovy
      allprojects {
         repositories {
            maven {
               url "http://download.dynamsoft.com/maven/dbr/aar"
            }
         }
      }
      ```

      ii. Then add `.aar` reference in the dependencies as below:

      ```groovy
      implementation 'com.dynamsoft:dynamsoftbarcodereader:{version number}@aar'
      ```

      iii. Click Sync Now. After the synchronization completes, `DynamsoftBarcodeReaderAndroid.aar` is added to the project.

3. Add the following code to initiate and use the Dynamsoft Barcode Reader SDK.

   ```java
   import com.dynamsoft.dbr.BarcodeReader;
   import com.dynamsoft.dbr.TextResult;
   import android.util.Log;
   public class MainActivity extends AppCompatActivity {
      @Override
      protected void onCreate(Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);
         try {
            BarcodeReader dbr = new BarcodeReader("your license here");
            // Note: If you do not have a valid license for the SDK, some characters of the barcode results will be replaced with "***".
            // Leave the template name empty ("") will use the settings from PublicRuntimeSettings.
            TextResult[] results = dbr.decodeFile("put your file path here", "");
            // e.g. TextResult[] results = dbr.decodeFile("/storage/dbr-preview-img/test.jpg", "");
            if (results.length > 0) {
               String resultContent = "Found " + results.length + " barcode(s):\n";
               for (int i = 0; i < results.length; i++) {
                  resultContent += results[i].barcodeText + "\n";
               }
               Log.i("DBR", resultContent);
            } else {
               Log.i("DBR", "No barcode found");
            }
         } catch (Exception ex) {
            ex.printStackTrace();
         }
      }
   }
   ```

4. Run the project.

## Decoding Methods

The SDK provides multiple decoding methods that support reading barcodes from different sources, including static images, video stream, files in memory, base64 string, bitmap, etc. Here is a list of all decoding methods:

- [decodeBuffer](api-reference/primary-decode.html#decodebuffer): Reads barcodes from raw buffer.
- [decodeFile](api-reference/primary-decode.html#decodefile): Reads barcodes from a specified file (BMP, JPEG, PNG, GIF, TIFF or PDF).
- [decodeFileInMemory](api-reference/primary-decode.html#decodefileinmemory): Decodes barcodes from an image file in memory.
- [decodeBase64String](api-reference/primary-decode.html#decodebase64string): Reads barcodes from a base64 encoded string of a file.
- [decodeBufferedImage](api-reference/primary-decode.html#decodebufferedimage): Reads barcodes from a bitmap. When handling multi-page images, it will only decode the current page.

You can find more samples in more programming languages at [Code Gallery](https://www.dynamsoft.com/Downloads/Dynamic-Barcode-Reader-Sample-Download.aspx) or [Github Repositories](https://github.com/dynamsoft-dbr?q=java&type=&language=).

## Barcode Reading Settings

Calling the [decoding methods](#decoding-methods) directly will use the default scanning modes and it will satisfy most of the needs. The SDK also allows you to adjust the scanning settings to optimize the scanning performance for different usage scenarios.

There are two ways to change the barcode reading settings - using the `PublicRuntimeSettings` class or template. For new developers, We recommend you to start with the `PublicRuntimeSettings` class; For those who are experienced with the SDK, you may use a template which is more flexible and easier to update.

- [Use `PublicRuntimeSettings` class to Change Settings](#use-publicruntimesettings-class-to-change-settings)
- [Use A Template to Change Settings](#use-a-template-to-change-settings)

### Use [`PublicRuntimeSettings`](api-reference/auxiliary-PublicRuntimeSettings.html) class to Change Settings

Here are some common scanning settings you might find helpful:

- [Specify Barcode Type to Read](#specify-barcode-type-to-read)
- [Specify Maximum Barcode Count](#specify-maximum-barcode-count)
- [Specify a Scan Region](#specify-a-scan-region)  

For more scanning settings guide, check out the [How To](#how-to-guide) section.

#### Specify Barcode Type to Read

By default, the SDK will read all the supported barcode formats except Postal Codes and Dotcode from the image. (See [Product Overview]({{ site.introduction }}) for the full supported barcode list.)

If your full license only covers some barcode formats, you can use `BarcodeFormatIds` and `BarcodeFormatIds_2` to specify the barcode format(s). Check out [`BarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android) and [`BarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android).

For example, to enable only 1D barcode reading, you can use the following code:

```java
BarcodeReader dbr = new BarcodeReader();
dbr.initLicense("<Put your license key here>"); //Replace "<Put your license key here>" with your own license
// Set barcodeFromatIds via PublicRuntimeSettings instance and update it to BarcodeReader instance
PublicRuntimeSettings runtimeSettings = dbr.getRuntimeSettings();
runtimeSettings.barcodeFormatIds = 0x7FF;// OneD barcode
dbr.updateRuntimeSettings(runtimeSettings);
// Replace "<Put the path of your file here>" with your own file path
TextResult[] result = dbr.decodeFile("<Put your file path here>","");
```

#### Specify maximum barcode count

By default, the SDK will read as many barcodes as it can. To increase the recognition efficiency, you can use `expectedBarcodesCount` to specify the maximum number of barcodes to recognize according to your scenario.

```java
BarcodeReader dbr = new BarcodeReader();
dbr.initLicense("<Put your license key here>"); //Replace "<Put your license key here>" with your own license
PublicRuntimeSettings rts = dbr.getRuntimeSettings();
rts.expectedBarcodesCount = 10;
dbr.updateRuntimeSettings(rts);
//Replace "<Put the path of your file here>" with your own file path
TextResult[] result = dbr.decodeFile("<Put your file path here>","");
```

#### Specify a scan region

By default, the barcode reader will search the whole image for barcodes. This can lead to poor performance especially when
dealing with high-resolution images. You can speed up the recognition process by restricting the scanning region.

To specify a region, you will need to define an area. The following code shows how to create a template string and define the region.  

```java
BarcodeReader dbr = new BarcodeReader();
dbr.initLicense("<Put your license key here>"); //Replace "<Put your license key here>" with your own license
PublicRuntimeSettings runtimeSettings = dbr.getRuntimeSettings();
runtimeSettings.region.regionBottom = 100;
runtimeSettings.region.regionLeft = 0;
runtimeSettings.region.regionRight = 50;
runtimeSettings.region.regionTop = 0;
runtimeSettings.region.regionMeasuredByPercentage = 1; //The region is determined by percentage
dbr.updateRuntimeSettings(runtimeSettings);
//Replace "<Put the path of your file here>" with your own file path
TextResult[] result = dbr.decodeFile("<Put your file path here>","");
```

### Use A Template to Change Settings

Besides the option of using the PublicRuntimeSettings class, the SDK also provides [`initRuntimeSettingsWithString`](api-reference/primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithstring) and [`initRuntimeSettingsWithFile`](api-reference/primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithfile) APIs that enable you to use a template to control all the runtime settings. With a template, instead of writing many codes to modify the settings, you can manage all the runtime settings in a JSON file/string.

```java
BarcodeReader dbr = new BarcodeReader();
dbr.initLicense("<Put your license key here>"); //Replace "<Put your license key here>" with your own license
br.initRuntimeSettingsWithFile("<put your json file here>", EnumConflictMode.CM_OVERWRITE);
//Replace "<Put the path of your file here>" with your own file path
TextResult[] result = dbr.decodeFile("<Put your file path here>","");
```

Below is a template for your reference. To learn more about the APIs, you can check out [`PublicRuntimeSettings`](api-reference/auxiliary-PublicRuntimeSettings.html) Class.

```json
{
   "ImageParameter" : {
      "BarcodeFormatIds" : [ "BF_ALL" ],
      "BinarizationModes" : [
         {
            "BlockSizeX" : 0,
            "BlockSizeY" : 0,
            "EnableFillBinaryVacancy" : 1,
            "ImagePreprocessingModesIndex" : -1,
            "Mode" : "BM_LOCAL_BLOCK",
            "ThreshValueCoefficient" : 10
         }
      ],
      "DeblurLevel" : 9,
      "Description" : "",
      "ExpectedBarcodesCount" : 0,
      "GrayscaleTransformationModes" : [
         {
            "Mode" : "GTM_ORIGINAL"
         }
      ],
      "ImagePreprocessingModes" : [
         {
            "Mode" : "IPM_GENERAL"
         }
      ],
      "IntermediateResultSavingMode" : {
         "Mode" : "IRSM_MEMORY"
      },
      "IntermediateResultTypes" : [ "IRT_NO_RESULT" ],
      "MaxAlgorithmThreadCount" : 4,
      "Name" : "runtimesettings",
      "PDFRasterDPI" : 300,
      "Pages" : "",
      "RegionDefinitionNameArray" : null,
      "RegionPredetectionModes" : [
         {
            "Mode" : "RPM_GENERAL"
         }
      ],
      "ResultCoordinateType" : "RCT_PIXEL",
      "ScaleDownThreshold" : 2300,
      "TerminatePhase" : "TP_BARCODE_RECOGNIZED",
      "TextFilterModes" : [
         {
            "MinImageDimension" : 65536,
            "Mode" : "TFM_GENERAL_CONTOUR",
            "Sensitivity" : 0
         }
      ],
      "TextResultOrderModes" : [
         {
            "Mode" : "TROM_CONFIDENCE"
         },
         {
            "Mode" : "TROM_POSITION"
         },
         {
            "Mode" : "TROM_FORMAT"
         }
      ],
      "TextureDetectionModes" : [
         {
            "Mode" : "TDM_GENERAL_WIDTH_CONCENTRATION",
            "Sensitivity" : 5
         }
      ],
      "Timeout" : 10000
   },
   "Version" : "3.0"
}
```

## How to Upgrade

### From x8.0 to 8.x

**Update the SDK**

Replace the old `DynamsoftBarcodeReaderAndroid.aar` file with the one in the latest version. If you are using Maven, then change the version number in the `build.gradle` file.

**API changes**

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

### From v7.x to 8.x

You need to replace the old `DynamsoftBarcodeReaderAndroid.aar` file with the one in the latest version. Download the latest version [here](https://www.dynamsoft.com/Downloads/Dynamic-Barcode-Reader-Download.aspx).

Your previous SDK license for version 7.x is not compatible with the version 8.x. Please [contact us](https://www.dynamsoft.com/Company/Contact.aspx) to upgrade your license.

In v8.0, we introduced a new license tracking mechanism, <a href="https://www.dynamsoft.com/license-tracking/docs/about/index.html" target="_blank">License 2.0</a>.

If you wish to use License 2.0, please refer to [this article]({{ site.license_activation }}set-full-license-8.html) to set the license.

After you upgraded your license to version 8.x:

- If you were using `initLicense`, please replace the old license with the newly generated one.

- If you were using `initLicenseFromServer` to connect to Dynamsoft server for license verification, then no need to change the license key. But please make sure the device has Internet connection.

### From v6.x to 8.x

We made some structural updates in the new version. To upgrade from 6.x to 8.x, we recommend you to review our sample code and re-write the barcode scanning module.
