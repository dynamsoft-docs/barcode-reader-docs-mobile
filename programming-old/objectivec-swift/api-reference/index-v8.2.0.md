---
layout: default-layout
title: Main Page - Dynamsoft Barcode Reader iOS API Reference
description: This is the main page of Dynamsoft Barcode Reader for iOS SDK API Reference.
keywords: api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: iOS API Reference
permalink: /programming/objectivec-swift/api-reference/index-v8.2.0.html
---

# iOS API Reference

## DynamsoftBarcodeReader Class

### Initialize
  
  | Method               | Description |
  |----------------------|-------------|
  | [`init`](primary-initialize.html#init) | Create an instance of Dynamsoft Barcode Reader. |

### Decode

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeFileWithName`](primary-decode.html#decodefilewithname) | Decode barcodes from a specified image file. |
  | [`decodeImage`](primary-decode.html#decodeimage) | Decode barcodes from an image file in memory. |
  | [`decodeBuffer`](primary-decode.html#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeBase64`](primary-decode.html#decodebase64) | Decode barcodes from a base64 encoded string. |

### License

  | Method               | Description |
  |----------------------|-------------|
  | [`license`](primary-license.html#license) | Stores the license used in DynamsoftBarcodeReader. |
  | [`initWithLicense`](primary-license.html#initwithlicense) | Read product key and activate the SDK. |
  | [`initWithLicenseFromServer`](primary-license.html#initwithlicensefromserver) | Initialize license and connect to the specified server for online verification. |
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
  | [`initRuntimeSettingsWithFile`](primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithfile) | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsWithString`](primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`appendTplFileToRuntimeSettings`](primary-parameter-and-runtime-settings-advanced.html#appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`appendTplStringToRuntimeSettings`](primary-parameter-and-runtime-settings-advanced.html#appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`allParameterTemplateNames`](primary-parameter-and-runtime-settings-advanced.html#allparametertemplatenames) | Get the count of the parameter templates. |
  | [`outputSettingsToFile`](primary-parameter-and-runtime-settings-advanced.html#outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputSettingsToString`](primary-parameter-and-runtime-settings-advanced.html#outputsettingstostring) | Output runtime settings to a string. |
  | [`setModeArgument`](primary-parameter-and-runtime-settings-advanced.html#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`getModeArgument`](primary-parameter-and-runtime-settings-advanced.html#getmodeargument) | Get argument value for the specified mode parameter. |

### Result

  | Method               | Description |
  |----------------------|-------------|
  | [`getIntermediateResult`](primary-result.html#getintermediateresult) | Get intermediate results. |
  | [`createIntermediateResult`](primary-result.html#createintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`decodeIntermediateResults`](primary-result.html#decodeintermediateresults) | Decodes barcode from intermediate results. |

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
  | [`getFrameDecodingParameters`](primary-video.html#getframedecodingparameters) | Initialize frame decoding parameter. |

#### Status retrieval

  | Method               | Description |
  |----------------------|-------------|
  | [`getLengthOfFrameQueue`](primary-video.html#getlengthofframequeue) | Get length of current inner frame queue. |

## [Error Code]({{ site.mobile_enum }}error-code.html?lang=objc,swift)

## Auxiliary Classes

- [`iAztecDetails`](auxiliary-iAztecDetails.html)
- [`iContour`](auxiliary-iContour.html)
- [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.html)
- [`iDMLTSConnectionParameters`](auxiliary-iDMDLSConnectionParameters.html)
- [`iExtendedResult`](auxiliary-iExtendedResult.html)
- [`iFrameDecodingParameters`](auxiliary-iFrameDecodingParameters.html)
- [`iFurtherModes`](auxiliary-iFurtherModes.html)
- [`iImageData`](auxiliary-iImageData.html)
- [`iIntermediateResult`](auxiliary-iIntermediateResult.html)
- [`iLineSegment`](auxiliary-iLineSegment.html)
- [`iLocalizationResult`](auxiliary-iLocalizationResult.html)
- [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.html)
- [`iPDF417Details`](auxiliary-iPDF417Details.html)
- [`iPublicRuntimeSettings`](auxiliary-iPublicRuntimeSettings.html)
- [`iQRCodeDetails`](auxiliary-iQRCodeDetails.html)
- [`iQuadrilateral`](auxiliary-iQuadrilateral.html)
- [`iRegionDefinition`](auxiliary-iRegionDefinition.html)
- [`iRegionOfInterest`](auxiliary-iRegionOfInterest.html)
- [`iSamplingImageData`](auxiliary-iSamplingImageData.html)
- [`iTextResult`](auxiliary-iTextResult.html)

## Protocol

  | Protocol | Description |
  | -------- | ----------- |
  | [`DBRTextResultDelegate`]({{ site.oc_api }}protocol-dbrtextresultdelegate.html) | Protocol for a delegate to handle callback when text result returned. |
  | [`DBRIntermediateResultDelegate`]({{ site.oc_api }}protocol-dbrintermediateresultdelegate.html) | Protocol for a delegate to handle callback when intermediate result returned. |
  | [`DBRErrorDelegate`]({{ site.oc_api }}protocol-dbrerrordelegate.html) | Protocol for a delegate to handle callback when an error returned. |
  | [`DBRServerLicenseVerificationDelegate`]({{ site.oc_api }}protocol-dbrserverlicenseverificationdelegate.html) | Protocol for a delegate to handle callback when license verification message returned. |
  | [`DMLTSLicenseVerificationDelegate`]({{ site.oc_api }}protocol-dmdlslicenseverificationdelegate.html) | Protocol for a delegate to handle callback when license verification message returned. |

## Enumerations

- [`EnumBarcodeColourMode`]({{ site.mobile_enum }}barcode-colour-mode.html?lang=objc,swift)
- [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift)
- [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift)
- [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift)
- [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift)
- [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift)
- [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift)
- [`EnumConflictMode`]({{ site.mobile_enum }}conflict-mode.html?lang=objc,swift)
- [`EnumDeblurMode`]({{ site.mobile_enum }}deblur-mode.html?lang=objc,swift)
- [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift)
- [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift)
- [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift)
- [`EnumImagePixelFormat`]({{ site.mobile_enum }}image-pixel-format.html?lang=objc,swift)
- [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift)
- [`EnumIMResultDataType`]({{ site.mobile_enum }}im-result-data-type.html?lang=objc,swift)
- [`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=objc,swift)
- [`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=objc,swift)
- [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift)
- [`EnumPDFReadingMode`]({{ site.mobile_enum }}pdf-reading-mode.html?lang=objc,swift)
- [`EnumQRCodeErrorCorrectionLevel`]({{ site.mobile_enum }}qr-code-error-correction-level.html?lang=objc,swift)
- [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift)
- [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift)
- [`EnumResultType`]({{ site.mobile_enum }}result-type.html?lang=objc,swift)
- [`EnumScaleUpMode`]({{ site.mobile_enum }}scale-up-mode.html?lang=objc,swift)
- [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift)
- [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift)
- [`EnumTextResultOrderMode`]({{ site.mobile_enum }}text-result-order-mode.html?lang=objc,swift)
- [`EnumTextureDetectionMode`]({{ site.mobile_enum }}texture-detection-mode.html?lang=objc,swift)
