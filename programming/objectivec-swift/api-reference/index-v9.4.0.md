---
layout: default-layout
title: Main Page - Dynamsoft Barcode Reader iOS API Reference
description: This is the main page of Dynamsoft Barcode Reader for iOS SDK API Reference.
keywords: api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: iOS API Reference
permalink: /programming/objectivec-swift/api-reference/index-v9.4.0.html
---

# iOS API Reference

## DynamsoftBarcodeReader Class

### Initialize
  
  | Method               | Description |
  |----------------------|-------------|
  | [`init`](primary-initialize.html#init) | Create an instance of Dynamsoft Barcode Reader. |

&nbsp;

### Video decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`setCameraEnhancer`](primary-video.html#setcameraenhancer) | Bind a Camera Enhancer instance to the Barcode Reader.  |
  | [`startScanning`](primary-video.html#startscanning) | Start the barcode reading thread. |
  | [`stopScanning`](primary-video.html#stopscanning) | Stop the barcode reading thread. |
  | [`setDBRTextResultListener`](primary-video.html#setdbrtextresultlistener) | Set callback function to process text results generated during frame decoding. |
  | [`setDBRIntermediateResultListener`](primary-video.html#setdbrintermediateresultlistener) | Set callback function to process intermediate results generated during frame decoding. |
  | [`minImageReadingInterval`](primary-video.html#minimagereadinginterval) | The property indicates the minimum interval between two barcode decoding. |
  | [`setImageSource`](primary-video.html#setimagesource) | Set the ImageSource as the source of video streaming. |

  | Property             | Description |
  |----------------------|-------------|
  | [`enableResultVerification`](primary-video.html#enableresultverification) | Enable **Result Verification** feature to improve the accuracy of barcode results for video streaming barcode decoding. |
  | [`enableDuplicateFilter`](primary-video.html#enableduplicatefilter) | Enable **Duplicate Filter** feature to filter out the duplicate results in the period of 3000ms for video barcode decoding. |

> Note:
>
> - `setDBRTextResultDelegate` is deprecated, please use `setDBRTextResultListener` instead.
> - `setDBRIntermediateResultDelegate` is deprecated, please use `setDBRIntermediateResultListener` instead.

&nbsp;

### Image decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeBuffer`](primary-decode.html#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeFileWithName`](primary-decode.html#decodefilewithname) | Decode barcodes from a specified image file. |
  | [`decodeImage`](primary-decode.html#decodeimage) | Decode barcodes from an image file in memory. |
  | [`decodeBase64`](primary-decode.html#decodebase64) | Decode barcodes from a base64 encoded string. |
  | [`decodeFileInMemory`](primary-decode.html#decodefileinmemory) | Decode barcodes from a file that is read in the memory. |

&nbsp;

### License

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](primary-license.html#initlicense) | Read product key and activate the SDK. |
  | [`setDeviceFriendlyName`](primary-license.html#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |

> Note:  
>  
> The following license activation methods are deprecated:
>
> - `license`
> - `outputLicenseToString`
> - `initLicenseFromDLS`
> - `initWithLicenseFromServer`
>
> Please use [`initLicense`](primary-license.html#initlicense) to activate the license.

&nbsp;

### Parameter and Runtime Settings

#### Basic
  
  | Method               | Description |
  |----------------------|-------------|
  | [`getRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings (with struct)`](primary-parameter-and-runtime-settings-basic.html#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`updateRuntimeSettings (with preset template)`](primary-parameter-and-runtime-settings-basic.html#with-a-preset-template) | Update runtime settings from one of the preset templates. |
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

&nbsp;

### Result

  | Method               | Description |
  |----------------------|-------------|
  | [`createIntermediateResult`](primary-result.html#createintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`getIntermediateResult`](primary-result.html#getintermediateresult) | Get intermediate results. |
  | [`decodeIntermediateResults`](primary-result.html#decodeintermediateresults) | Decodes barcode from intermediate results. |

&nbsp;

### Status Retrieval

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](primary-status-retrieval.html#getversion) | Get version information of SDK.|

&nbsp;

## Auxiliary Classes

- [`iAztecDetails`](auxiliary-iAztecDetails.html)
- [`iContour`](auxiliary-iContour.html)
- [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.html)
- [`iExtendedResult`](auxiliary-iExtendedResult.html)
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

> Note:  
>
> - `iDMDLSConnectionParameters` is deprecated due to the update of the license. Please use the method [`initLicense`](primary-license.html#initlicense) to activate the license instead.

&nbsp;

## Protocol

  | Protocol | Description |
  | -------- | ----------- |
  | [`DBRTextResultListener`]({{ site.oc_api }}protocol-dbrtextresultdelegate.html) | Protocol for a delegate to handle callback when text result returned. |
  | [`DBRIntermediateResultListener`]({{ site.oc_api }}protocol-dbrintermediateresultdelegate.html) | Protocol for a delegate to handle callback when intermediate result returned. |
  | [`DBRLicenseVerificationDelegate`]({{ site.oc_api }}protocol-dmdlslicenseverificationdelegate.html) | Protocol for a delegate to handle callback when license verification message returned. |
  | [`ImageSource`]({{ site.oc_api }}protocol-imagesource.html) | Protocol for producers of images. It can be implemented by programmers to support other image sources, such as external cameras or image filesets. |

> Note:  
>  
> - `DBRTextResultDelegate` is deprecated, please use [`DBRTextResultListener`]({{ site.oc_api }}protocol-dbrtextresultdelegate.html) instead.
> - `DBRIntermediateResultDelegate` is deprecated, please use [`DBRIntermediateResultListener`]({{ site.oc_api }}protocol-dbrintermediateresultdelegate.html) instead.
> - [`DBRServerLicenseVerificationDelegate`](protocol-dbrserverlicenseverificationdelegate.html) is deprecated. It handles callback when using `initWithLicenseFromServer`, which is also deprecated. Please use [`initLicense`](primary-license.html#initlicense) instead.
> - [`DMDLSLicenseVerificationDelegate`](protocol-dmdlslicenseverificationdelegate.html) is deprecated. It handles callback when using `initLicenseFromDLS`, which is also deprecated. Please use [`initLicense`](primary-license.html#initlicense) instead.

&nbsp;

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
- [`EnumIMResultDataType`]({{ site.mobile_enum }}im-result-data-type.html?lang=objc,swift)
- [`EnumImagePixelFormat`]({{ site.mobile_enum }}image-pixel-format.html?lang=objc,swift)
- [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift)
- [`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=objc,swift)
- [`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=objc,swift)
- [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift)
- [`EnumPDFReadingMode`]({{ site.mobile_enum }}pdf-reading-mode.html?lang=objc,swift)
- [`EnumPresetTemplate`]({{ site.mobile_enum }}preset-template.html?lang=objc,swift)
- [`EnumQRCodeErrorCorrectionLevel`]({{ site.mobile_enum }}qr-code-error-correction-level.html?lang=objc,swift)
- [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift)
- [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift)
- [`EnumResultType`]({{ site.mobile_enum }}result-type.html?lang=objc,swift)
- [`EnumScaleUpMode`]({{ site.mobile_enum }}scale-up-mode.html?lang=objc,swift)
- [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift)
- [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift)
- [`EnumTextResultOrderMode`]({{ site.mobile_enum }}text-result-order-mode.html?lang=objc,swift)
- [`EnumTextureDetectionMode`]({{ site.mobile_enum }}texture-detection-mode.html?lang=objc,swift)

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

View the [Error Code]({{ site.mobile_enum }}error-code.html?lang=objc,swift)
