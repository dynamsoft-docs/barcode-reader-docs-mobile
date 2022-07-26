---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader for Android SDK API Reference.
keywords: api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: Android API Reference
noTitleIndex: true
permalink: /programming/android/api-reference/
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
  | [`setMinImageReadingInterval`](primary-video.md#setminimagereadinginterval) | Set the minimum interval between two barcode decoding. |
  | [`getMinImageReadingInterval`](primary-video.md#getminimagereadinginterval) | Get the minimum interval between two barcode decoding. |
  | [`setImageSource`](primary-video.md#setimagesource) | Set the ImageSource as the source of video streaming. |

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
  | [`setDeviceFriendlyName`](primary-license.md#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |

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
  | [`ImageSource`](interface-imagesource.md) | Interface for producers of images. It can be implemented by programmers to support other image sources, such as external cameras or image filesets. |

> Note:
>
> - `TextResultCallback` is deprecated, please use [`TextResultListener`](interface-textresultcallback.md) instead.
> - `IntermediateResultCallback` is deprecated, please use [`IntermediateResultListener`](interface-intermediateresultcallback.md) instead.
> - [`DBRServerLicenseVerificationListener`](interface-dbrserverlicenseverificationlistener.md) is deprecated. It handles callback when using method `initLicenseFromServer`, which is also deprecated. Please use [`initLicense`](primary-license.md#initlicense) instead.
> - [`DBRDLSLicenseVerificationListener`](interface-dbrdlslicenseverificationlistener.md) is deprecated. It handles callback when using method `initLicenseFromDLS`, which is also deprecated. Please use [`initLicense`](primary-license.md#initlicense) instead.

&nbsp;

## Enumerations

- [`EnumBarcodeColourMode`]({{ site.mobile-enum }}barcode-colour-mode.html)
- [`EnumBarcodeComplementMode`]({{ site.mobile-enum }}barcode-complement-mode.html)
- [`EnumBarcodeFormat`]({{ site.mobile-enum }}barcode-format.html)
- [`EnumBarcodeFormat_2`]({{ site.mobile-enum }}barcode-format2.html)
- [`EnumBinarizationMode`]({{ site.mobile-enum }}binarization-mode.html)
- [`EnumClarityCalculationMethod`]({{ site.mobile-enum }}frame-decoding-enums.html#claritycalculationmethod)
- [`EnumClarityFilterMode`]({{ site.mobile-enum }}frame-decoding-enums.html#clarityfiltermode)
- [`EnumColourClusteringMode`]({{ site.mobile-enum }}colour-clustering-mode.html)
- [`EnumColourConversionMode`]({{ site.mobile-enum }}colour-conversion-mode.html)
- [`EnumConflictMode`]({{ site.mobile-enum }}conflict-mode.html)
- [`EnumDeblurMode`]({{ site.mobile-enum }}deblur-mode.html)
- [`EnumDeformationResistingMode`]({{ site.mobile-enum }}deformation-resisting-mode.html)
- [`EnumDPMCodeReadingMode`]({{ site.mobile-enum }}dpm-code-reading-mode.html)
- [`EnumGrayscaleTransformationMode`]({{ site.mobile-enum }}grayscale-transformation-mode.html)
- [`EnumImagePixelFormat`]({{ site.mobile-enum }}image-pixel-format.html)
- [`EnumImagePreprocessingMode`]({{ site.mobile-enum }}image-preprocessing-mode.html)
- [`EnumIMResultDataType`]({{ site.mobile-enum }}im-result-data-type.html)
- [`EnumIntermediateResultSavingMode`]({{ site.mobile-enum }}intermediate-result-saving-mode.html)
- [`EnumIntermediateResultType`]({{ site.mobile-enum }}intermediate-result-type.html)
- [`EnumLocalizationMode`]({{ site.mobile-enum }}localization-mode.html)
- [`EnumPDFReadingMode`]({{ site.mobile-enum }}pdf-reading-mode.html)
- [`EnumQRCodeErrorCorrectionLevel`]({{ site.mobile-enum }}qr-code-error-correction-level.html)
- [`EnumRegionPredetectionMode`]({{ site.mobile-enum }}region-predetection-mode.html)
- [`EnumResultCoordinateType`]({{ site.mobile-enum }}result-coordinate-type.html)
- [`EnumResultType`]({{ site.mobile-enum }}result-type.html)
- [`EnumScaleUpMode`]({{ site.mobile-enum }}scale-up-mode.html)
- [`EnumTerminatePhase`]({{ site.mobile-enum }}terminate-phase.html)
- [`EnumTextFilterMode`]({{ site.mobile-enum }}text-filter-mode.html)
- [`EnumTextResultOrderMode`]({{ site.mobile-enum }}text-result-order-mode.html)
- [`EnumTextureDetectionMode`]({{ site.mobile-enum }}texture-detection-mode.html)
- [`EnumPresetTemplate`]({{ site.mobile-enum }}preset-template.html)

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

View the [Error Codes]({{ site.mobile-enum }}error-code.html)
