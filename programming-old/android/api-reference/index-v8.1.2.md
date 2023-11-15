---
layout: default-layout
title: Main Page - Dynamsoft Barcode Reader Android API Reference
description: This is the main page of Dynamsoft Barcode Reader for Android SDK API Reference.
keywords: api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: Android API Reference
noTitleIndex: true
permalink: /programming/android/api-reference/index-v8.1.2.html
---

# Android API Reference

## BarcodeReader Class

### Initialize

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](primary-initialize-and-destroy.html#barcodereader) | Initialization of `BarcodeReader` object.|

### Decode

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeFile`](primary-decode.html#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](primary-decode.html#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`decodeBuffer`](primary-decode.html#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeBase64String`](primary-decode.html#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](primary-decode.html#decodebufferedimage) | Decodes barcode from a buffered image (bitmap). |

### License
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](primary-license.html#initlicense) | Read product key and activate the SDK. |
  | [`initLicenseFromServer`](primary-license.html#initlicensefromserver) | Initialize license and connect to the specified server for online verification. |
  | [`initLicenseFromLicenseContent`](primary-license.html#initlicensefromlicensecontent) | Initialize license from the license content on client machine for offline verification. |
  | [`outputLicenseToString`](primary-license.html#outputlicensetostring) | Output the license content to a string from the license server. |
  | [`initLicenseFromLTS`](primary-license.html#initlicensefromlts) | Initializes the barcode reader license and connects to the specified server for online verification. |

### Parameter and Runtime Settings

#### Basic

  | Method               | Description |
  |----------------------|-------------|
  | [`getRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`resetRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#resetruntimesettings) | Reset runtime settings to default. |

#### Advanced
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initRuntimeSettingsWithFile`](primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithfile)  | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsWithString`](primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`appendTplFileToRuntimeSettings`](primary-parameter-and-runtime-settings-advanced.html#appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`appendTplStringToRuntimeSettings`](primary-parameter-and-runtime-settings-advanced.html#appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`getAllParameterTemplateNames`](primary-parameter-and-runtime-settings-advanced.html#getallparametertemplatenames) | Gets the parameter templates name array. |
  | [`outputSettingsToFile`](primary-parameter-and-runtime-settings-advanced.html#outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputSettingsToString`](primary-parameter-and-runtime-settings-advanced.html#outputsettingstostring) | Output runtime settings to a string. |
  | [`setModeArgument`](primary-parameter-and-runtime-settings-advanced.html#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`getModeArgument`](primary-parameter-and-runtime-settings-advanced.html#getmodeargument) | Get argument value for the specified mode parameter. |

### Result

  | Method               | Description |
  |----------------------|-------------|
  | [`initIntermediateResult`](primary-result.html#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`getIntermediateResults`](primary-result.html#getintermediateresults) | Get intermediate results. |
  | [`decodeIntermediateResults`](primary-result.html#decodeintermediateresults) | Decodes barcode from intermediate results. |

### Status Retrieval

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](primary-status-retrieval.html#getversion) | Get version information of SDK.|

### Video

#### Decode

   | Method               | Description |
   |----------------------|-------------|
   | [`startFrameDecoding`](primary-video.html#startframedecoding) | Decode barcodes from inner frame queue. |
   | [`startFrameDecodingEx`](primary-video.html#startframedecodingex) | Decode barcodes from inner frame queue. |
   | [`appendFrame`](primary-video.html#appendframe) | Append a frame image buffer to the inner frame queue. |
   | [`stopFrameDecoding`](primary-video.html#stopframedecoding) | Stop thread used for frame decoding. |

#### Parameter

   | Method               | Description |
   |----------------------|-------------|
   | [`initFrameDecodingParameters`](primary-video.html#initframedecodingparameters) | Initialize frame decoding parameter. |

#### Callback

   | Method               | Description |
   |----------------------|-------------|
   | [`setErrorCallback`](primary-video.html#seterrorcallback) | Set callback interface to process errors generated during frame decoding. |
   | [`setTextResultCallback`](primary-video.html#settextresultcallback) | Set callback interface to process text results generated during frame decoding. |
   | [`setIntermediateResultCallback`](primary-video.html#setintermediateresultcallback) | Set callback interface to process intermediate results generated during frame decoding. |

#### Status retrieval

   | Method               | Description |
   |----------------------|-------------|
   | [`getLengthOfFrameQueue`](primary-video.html#getlengthofframequeue) | Get length of current inner frame queue. |

## [Error Code]({{ site.mobile_enum }}error-code.html?lang=android)

## Auxiliary Classes

- [`AztecDetails`](auxiliary-AztecDetails.html)
- [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)
- [`Contour`](auxiliary-Contour.html)
- [`DataMatrixDetails`](auxiliary-DataMatrixDetails.html)
- [`DMLTSConnectionParameters`](auxiliary-DMDLSConnectionParameters.html)
- [`ExtendedResult`](auxiliary-ExtendedResult.html)
- [`FrameDecodingParameters`](auxiliary-FrameDecodingParameters.html)
- [`FurtherModes`](auxiliary-FurtherModes.html)
- [`ImageData`](auxiliary-ImageData.html)
- [`IntermediateResult`](auxiliary-IntermediateResult.html)
- [`LineSegment`](auxiliary-LineSegment.html)
- [`LocalizationResult`](auxiliary-LocalizationResult.html)
- [`OneDCodeDetails`](auxiliary-OneDCodeDetails.html)
- [`PDF417Details`](auxiliary-PDF417Details.html)
- [`PublicRuntimeSettings`](auxiliary-PublicRuntimeSettings.html)
- [`QRCodeDetails`](auxiliary-QRCodeDetails.html)
- [`Quadrilateral`](auxiliary-Quadrilateral.html)
- [`RegionDefinition`](auxiliary-RegionDefinition.html)
- [`RegionOfInterest`](auxiliary-RegionOfInterest.html)
- [`SamplingImageData`](auxiliary-SamplingImageData.html)
- [`TextResult`](auxiliary-TextResult.html)

## Interfaces

  | Interfaces | Description |
  |----------|-------------|
  | [`TextResultCallback`](interface-textresultcallback.html) | The interface to handle callback when text results are returned. |
  | [`IntermediateResultCallback`](interface-intermediateresultcallback.html) | The interface to handle callback when intermediate results are returned. |
  | [`ErrorCallback`](interface-errorcallback.html) | The interface to handle callback when an error is returned. |
  | [`DBRServerLicenseVerificationListener`](interface-dbrserverlicenseverificationlistener.html) | The interface to handle callback when license verification messages are returned. |
  | [`DBRLTSLicenseVerificationListener`](interface-dbrdlslicenseverificationlistener.html) | The interface to handle callback when license verification messages are returned. |

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
