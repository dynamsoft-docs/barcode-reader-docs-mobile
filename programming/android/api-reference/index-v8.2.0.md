---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader for Android SDK API Reference.
keywords: api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: Android API Reference
noTitleIndex: true
permalink: /programming/android/api-reference/index-v8.2.0.html
---

# Android API Reference

## BarcodeReader Class

### Initialize

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](primary-initialize-and-destroy.md#barcodereader) | Initialization of `BarcodeReader` object.|

### Decode

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeFile`](primary-decode.md#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](primary-decode.md#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`decodeBuffer`](primary-decode.md#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeBase64String`](primary-decode.md#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](primary-decode.md#decodebufferedimage) | Decodes barcode from a buffered image (bitmap). |

### License
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](primary-license.md#initlicense) | Read product key and activate the SDK. |
  | [`initLicenseFromServer`](primary-license.md#initlicensefromserver) | Initialize license and connect to the specified server for online verification. |
  | [`initLicenseFromLicenseContent`](primary-license.md#initlicensefromlicensecontent) | Initialize license from the license content on client machine for offline verification. |
  | [`outputLicenseToString`](primary-license.md#outputlicensetostring) | Output the license content to a string from the license server. |
  | [`initLicenseFromLTS`](primary-license.md#initlicensefromlts) | Initializes the barcode reader license and connects to the specified server for online verification. |

### Parameter and Runtime Settings

#### Basic

  | Method               | Description |
  |----------------------|-------------|
  | [`getRuntimeSettings`](primary-parameter-and-runtime-settings-basic.md#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings`](primary-parameter-and-runtime-settings-basic.md#updateruntimesettings) | Modify and update the current runtime settings. |
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

### Result

  | Method               | Description |
  |----------------------|-------------|
  | [`initIntermediateResult`](primary-result.md#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`getIntermediateResults`](primary-result.md#getintermediateresults) | Get intermediate results. |
  | [`decodeIntermediateResults`](primary-result.md#decodeintermediateresults) | Decodes barcode from intermediate results. |

### Status Retrieval

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](primary-status-retrieval.md#getversion) | Get version information of SDK.|

### Video

#### Decode

   | Method               | Description |
   |----------------------|-------------|
   | [`startFrameDecoding`](primary-video.md#startframedecoding) | Decode barcodes from inner frame queue. |
   | [`startFrameDecodingEx`](primary-video.md#startframedecodingex) | Decode barcodes from inner frame queue. |
   | [`appendFrame`](primary-video.md#appendframe) | Append a frame image buffer to the inner frame queue. |
   | [`stopFrameDecoding`](primary-video.md#stopframedecoding) | Stop thread used for frame decoding. |

#### Parameter

   | Method               | Description |
   |----------------------|-------------|
   | [`initFrameDecodingParameters`](primary-video.md#initframedecodingparameters) | Initialize frame decoding parameter. |

#### Callback

   | Method               | Description |
   |----------------------|-------------|
   | [`setErrorCallback`](primary-video.md#seterrorcallback) | Set callback interface to process errors generated during frame decoding. |
   | [`setTextResultCallback`](primary-video.md#settextresultcallback) | Set callback interface to process text results generated during frame decoding. |
   | [`setIntermediateResultCallback`](primary-video.md#setintermediateresultcallback) | Set callback interface to process intermediate results generated during frame decoding. |

#### Status retrieval

   | Method               | Description |
   |----------------------|-------------|
   | [`getLengthOfFrameQueue`](primary-video.md#getlengthofframequeue) | Get length of current inner frame queue. |

## [Error Code]({{ site.mobile_enum }}error-code.html?lang=android)

## Auxiliary Classes

- [`AztecDetails`](auxiliary-AztecDetails.md)
- [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md)
- [`Contour`](auxiliary-Contour.md)
- [`DataMatrixDetails`](auxiliary-DataMatrixDetails.md)
- [`DMLTSConnectionParameters`](auxiliary-DMLTSConnectionParameters.md)
- [`ExtendedResult`](auxiliary-ExtendedResult.md)
- [`FrameDecodingParameters`](auxiliary-FrameDecodingParameters.md)
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

## Interfaces

  | Interfaces | Description |
  |----------|-------------|
  | [`TextResultCallback`](interface-textresultcallback.md) | The interface to handle callback when text results are returned. |
  | [`IntermediateResultCallback`](interface-intermediateresultcallback.md) | The interface to handle callback when intermediate results are returned. |
  | [`ErrorCallback`](interface-errorcallback.md) | The interface to handle callback when an error is returned. |
  | [`DBRServerLicenseVerificationListener`](interface-dbrserverlicenseverificationlistener.md) | The interface to handle callback when license verification messages are returned. |
  | [`DBRLTSLicenseVerificationListener`](interface-dbrdlslicenseverificationlistener.md) | The interface to handle callback when license verification messages are returned. |

## Enumerations

- [`EnumBarcodeColourMode`]({{ site.mobile_enum }}barcode-colour-mode.html?lang=android)
- [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=android)
- [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android)
- [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android)
- [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=android)
- [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=android)
- [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=android)
- [`EnumConflictMode`]({{ site.mobile_enum }}conflict-mode.html?lang=android)
- [`EnumDeblurMode`]({{ site.mobile_enum }}deblur-mode.html?lang=android)
- [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=android)
- [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=android)
- [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=android)
- [`EnumImagePixelFormat`]({{ site.mobile_enum }}image-pixel-format.html?lang=android)
- [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=android)
- [`EnumIMResultDataType`]({{ site.mobile_enum }}im-result-data-type.html?lang=android)
- [`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=android)
- [`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=android)
- [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=android)
- [`EnumPDFReadingMode`]({{ site.mobile_enum }}pdf-reading-mode.html?lang=android)
- [`EnumQRCodeErrorCorrectionLevel`]({{ site.mobile_enum }}qr-code-error-correction-level.html?lang=android)
- [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=android)
- [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=android)
- [`EnumResultType`]({{ site.mobile_enum }}result-type.html?lang=android)
- [`EnumScaleUpMode`]({{ site.mobile_enum }}scale-up-mode.html?lang=android)
- [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=android)
- [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=android)
- [`EnumTextResultOrderMode`]({{ site.mobile_enum }}text-result-order-mode.html?lang=android)
- [`EnumTextureDetectionMode`]({{ site.mobile_enum }}texture-detection-mode.html?lang=android)
