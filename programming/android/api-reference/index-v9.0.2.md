---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader for Android SDK API Reference.
keywords: api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: Android API Reference
noTitleIndex: true
permalink: /programming/android/api-reference/index-v9.0.2.html
---

# Android API Reference

## BarcodeReader Class

### Initialize

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](primary-initialize-and-destroy.md#barcodereader) | Initialization of `BarcodeReader` object.|

&nbsp;

### Video Decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`setCameraEnhancer`](primary-video.md#setcameraenhancer) | Bind a Camera Enhancer instance to the Barcode Reader.  |
  | [`startScanning`](primary-video.md#startscanning) | Start the barcode reading thread. |
  | [`stopScanning`](primary-video.md#stopscanning) | Stop the barcode reading thread. |
  | [`setTextResultListener`](primary-video.md#settextresultlistener) | Set TextResult listener to get result from the callback method when barcode is decoded. |
  | [`setIntermediateResultListener`](primary-video.md#setintermediateresultlistener) | Set intermediateResult listener to get intermediate result from the callback method. |

> Note:  
>
> - `setTextResultCallback` is deprecated, please use [`setTextResultListener`](primary-video.md#settextresultlistener) instead.
> - `setIntermediateResultCallback` is deprecated, please use [`setIntermediateResultListener`](primary-video.md#setintermediateresultlistener) instead.

&nbsp;

### Image Decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeBuffer`](primary-decode.md#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeFile`](primary-decode.md#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](primary-decode.md#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`decodeBase64String`](primary-decode.md#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](primary-decode.md#decodebufferedimage) | Decodes barcode from a buffered image (bitmap). |
  | [`initIntermediateResult`](primary-decode.md#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`decodeIntermediateResults`](primary-decode.md#decodeintermediateresults) | Decodes barcode from intermediate results. |

&nbsp;

### License
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](primary-license.md#initlicense) | Read product key and activate the SDK. |

> Note:  
>  
> The following license activation methods are deprecated:
>
> - `outputLicenseToString`
> - `initLicenseFromDLS`
> - `initLicenseFromServer`
> - `initLicenseFromLicenseContent`
>
> Please use [`initLicense`](primary-license.md#initlicense) to activate the license.

&nbsp;

### Parameter and Runtime Settings

#### Basic

  | Method               | Description |
  |----------------------|-------------|
  | [`getRuntimeSettings`](primary-parameter-and-runtime-settings-basic.md#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings (with struct)`](primary-parameter-and-runtime-settings-basic.md#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`updateRuntimeSettings (with preset template)`](primary-parameter-and-runtime-settings-basic.md#with-a-preset-template) | Update runtime settings from one of the preset templates. |
  | [`resetRuntimeSettings`](primary-parameter-and-runtime-settings-basic.md#resetruntimesettings) | Reset runtime settings to default. |

#### Advanced
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initRuntimeSettingsWithFile`](primary-parameter-and-runtime-settings-advanced.md#initruntimesettingswithfile)  | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsWithString`](primary-parameter-and-runtime-settings-advanced.md#initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`appendTplFileToRuntimeSettings`](primary-parameter-and-runtime-settings-advanced.md#appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`appendTplStringToRuntimeSettings`](primary-parameter-and-runtime-settings-advanced.md#appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`getAllParameterTemplateNames`](primary-parameter-and-runtime-settings-advanced.md#getallparametertemplatenames) | Gets the parameter templates name array. |
  | [`outputSettingsToFile`](primary-parameter-and-runtime-settings-advanced.md#outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputSettingsToString`](primary-parameter-and-runtime-settings-advanced.md#outputsettingstostring) | Output runtime settings to a string. |
  | [`setModeArgument`](primary-parameter-and-runtime-settings-advanced.md#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`getModeArgument`](primary-parameter-and-runtime-settings-advanced.md#getmodeargument) | Get argument value for the specified mode parameter. |

&nbsp;

### Result

  | Method               | Description |
  |----------------------|-------------|
  | [`getIntermediateResults`](primary-result.md#getintermediateresults) | Get intermediate results. |
  | [`enableResultVerification`](primary-result.md#enableresultverification) | Verify the results before output. |
  | [`enableDuplicateFiter`](primary-result.md#enableduplicatefiter) | Output the duplicated result only once for every 3 seconds. |

&nbsp;

### Status Retrieval

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](primary-status-retrieval.md#getversion) | Get version information of SDK.|

&nbsp;

## Auxiliary Classes

- [`AztecDetails`](auxiliary-AztecDetails.md)
- [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md)
- [`Contour`](auxiliary-Contour.md)
- [`DataMatrixDetails`](auxiliary-DataMatrixDetails.md)
- [`ExtendedResult`](auxiliary-ExtendedResult.md)
- [`FurtherModes`](auxiliary-FurtherModes.md)
- [`ImageData`](auxiliary-ImageData.md)
- [`IntermediateResult`](auxiliary-IntermediateResult.md)
- [`LineSegment`](auxiliary-LineSegment.md)
- [`LocalizationResult`](auxiliary-LocalizationResult.md)
- [`OneDCodeDetails`](auxiliary-OneDCodeDetails.md)
- [`PDF417Details`](auxiliary-PDF417Details.md)
- [`PublicRuntimeSettings`](auxiliary-PublicRuntimeSettings.md)
- [`QRCodeDetails`](auxiliary-QRCodeDetails.md)
- [`Quadrilateral`](auxiliary-Quadrilateral.md)
- [`RegionDefinition`](auxiliary-RegionDefinition.md)
- [`RegionOfInterest`](auxiliary-RegionOfInterest.md)
- [`SamplingImageData`](auxiliary-SamplingImageData.md)
- [`TextResult`](auxiliary-TextResult.md)

> Note:  
>
> - `DMDLSConnectionParameters` is deprecated due to the update of the license. Please use the method [`initLicense`](primary-license.md#initlicense) to activate the license instead.

&nbsp;

## Interfaces

  | Interfaces | Description |
  |----------|-------------|
  | [`TextResultListener`](interface-textresultcallback.md) | The interface to handle callback when text results are returned. |
  | [`IntermediateResultListener`](interface-intermediateresultcallback.md) | The interface to handle callback when intermediate results are returned. |
  | [`DBRLicenseVerificationListener`](interface-dbrdlslicenseverificationlistener.md) | The interface to handle callback for method [`initLicense`](primary-license.md#initlicense). |

> Note:
>
> - `TextResultCallback` is deprecated, please use [`TextResultListener`](interface-textresultcallback.md) instead.
> - `IntermediateResultCallback` is deprecated, please use [`IntermediateResultListener`](interface-intermediateresultcallback.md) instead.
> - [`DBRServerLicenseVerificationListener`](interface-dbrserverlicenseverificationlistener.md) is deprecated. It handles callback when using method `initLicenseFromServer`, which is also deprecated. Please use [`initLicense`](primary-license.md#initlicense) instead.
> - [`DBRDLSLicenseVerificationListener`](interface-dbrdlslicenseverificationlistener.md) is deprecated. It handles callback when using method `initLicenseFromDLS`, which is also deprecated. Please use [`initLicense`](primary-license.md#initlicense) instead.

&nbsp;

## Enumerations

- [`EnumBarcodeColourMode`]({{ site.mobile-enum }}barcode-colour-mode.html?lang=android)
- [`EnumBarcodeComplementMode`]({{ site.mobile-enum }}barcode-complement-mode.html?lang=android)
- [`EnumBarcodeFormat`]({{ site.mobile-enum }}barcode-format.html?lang=android)
- [`EnumBarcodeFormat_2`]({{ site.mobile-enum }}barcode-format2.html?lang=android)
- [`EnumBinarizationMode`]({{ site.mobile-enum }}binarization-mode.html?lang=android)
- [`EnumColourClusteringMode`]({{ site.mobile-enum }}colour-clustering-mode.html?lang=android)
- [`EnumColourConversionMode`]({{ site.mobile-enum }}colour-conversion-mode.html?lang=android)
- [`EnumConflictMode`]({{ site.mobile-enum }}conflict-mode.html?lang=android)
- [`EnumDeblurMode`]({{ site.mobile-enum }}deblur-mode.html?lang=android)
- [`EnumDeformationResistingMode`]({{ site.mobile-enum }}deformation-resisting-mode.html?lang=android)
- [`EnumDPMCodeReadingMode`]({{ site.mobile-enum }}dpm-code-reading-mode.html?lang=android)
- [`EnumGrayscaleTransformationMode`]({{ site.mobile-enum }}grayscale-transformation-mode.html?lang=android)
- [`EnumImagePixelFormat`]({{ site.mobile-enum }}image-pixel-format.html?lang=android)
- [`EnumImagePreprocessingMode`]({{ site.mobile-enum }}image-preprocessing-mode.html?lang=android)
- [`EnumIMResultDataType`]({{ site.mobile-enum }}im-result-data-type.html?lang=android)
- [`EnumIntermediateResultSavingMode`]({{ site.mobile-enum }}intermediate-result-saving-mode.html?lang=android)
- [`EnumIntermediateResultType`]({{ site.mobile-enum }}intermediate-result-type.html?lang=android)
- [`EnumLocalizationMode`]({{ site.mobile-enum }}localization-mode.html?lang=android)
- [`EnumPDFReadingMode`]({{ site.mobile-enum }}pdf-reading-mode.html?lang=android)
- [`EnumQRCodeErrorCorrectionLevel`]({{ site.mobile-enum }}qr-code-error-correction-level.html?lang=android)
- [`EnumRegionPredetectionMode`]({{ site.mobile-enum }}region-predetection-mode.html?lang=android)
- [`EnumResultCoordinateType`]({{ site.mobile-enum }}result-coordinate-type.html?lang=android)
- [`EnumResultType`]({{ site.mobile-enum }}result-type.html?lang=android)
- [`EnumScaleUpMode`]({{ site.mobile-enum }}scale-up-mode.html?lang=android)
- [`EnumTerminatePhase`]({{ site.mobile-enum }}terminate-phase.html?lang=android)
- [`EnumTextFilterMode`]({{ site.mobile-enum }}text-filter-mode.html?lang=android)
- [`EnumTextResultOrderMode`]({{ site.mobile-enum }}text-result-order-mode.html?lang=android)
- [`EnumTextureDetectionMode`]({{ site.mobile-enum }}texture-detection-mode.html?lang=android)
- [`EnumPresetTemplate`]({{ site.mobile-enum }}preset-template.html?lang=android)

> Note:  
>  
> The following Enumerations are deprecated and will be removed in the future.
>
> - `EnumProduct`
> - `EnumDMChargeWay`
> - `EnumDMLicenseModule`
> - `EnumDMUUIDGenerationMethod`

&nbsp;

## Others

View the [Error Codes]({{ site.mobile-enum }}error-code.html?lang=android)
