---
layout: default-layout
title: Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows all methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
breadcrumbText: Methods
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/primary-index-v8.4.0.html
---

# BarcodeReader Class

## Initialize
  
  | Method               | Description |
  |----------------------|-------------|
  | [`init`](primary-initialize.html#init) | Create an instance of Dynamsoft Barcode Reader. |

## Decode

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeFileWithName`](primary-decode.html#decodefilewithname) | Decode barcodes from a specified image file. |
  | [`decodeImage`](primary-decode.html#decodeimage) | Decode barcodes from an image file in memory. |
  | [`decodeBuffer`](primary-decode.html#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeBase64`](primary-decode.html#decodebase64) | Decode barcodes from a base64 encoded string. |

### Camera Enhancer
  
   | Method               | Description |
   |----------------------|-------------|
   | [`SetCameraEnhancerParam`](primary-camera.html#setcameraenhancerparam) | Set the parameters for Dynamsoft Camera Enhancer in Barcode reader |

## License

  | Method               | Description |
  |----------------------|-------------|
  | [`initWithLicense`](primary-license.html#initwithlicense) | Read product key and activate the SDK. |
  | [`initWithLicenseFromServer`](primary-license.html#initwithlicensefromserver) | Initialize license and connect to the specified server for online verification. |
  | [`outputLicenseToString`](primary-license.html#outputlicensetostring) | Output the license content to a string from the license server. |
  | [`initLicenseFromLTS`](primary-license.html#initlicensefromlts) | Initializes the barcode reader license and connects to the specified server for online verification. |

## Parameter and Runtime Settings

### Basic
  
  | Method               | Description |
  |----------------------|-------------|
  | [`getRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`resetRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#resetruntimesettings) | Reset runtime settings to default. |

### Advanced
  
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

## Result

  | Method               | Description |
  |----------------------|-------------|
  | [`createIntermediateResult`](primary-result.html#createintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`getIntermediateResult`](primary-result.html#getintermediateresult) | Get intermediate results. |
  | [`decodeIntermediateResults`](primary-result.html#decodeintermediateresults) | Decodes barcode from intermediate results. |

## Video

### Decode

  | Method               | Description |
  |----------------------|-------------|
  | [`startFrameDecoding`](primary-video.html#startframedecoding) | Decode barcodes from inner frame queue. |
  | [`startFrameDecodingEx`](primary-video.html#startframedecodingex) | Decode barcodes from inner frame queue. |
  | [`appendFrame`](primary-video.html#appendframe) | Append a frame image buffer to the inner frame queue. |
  | [`stopFrameDecoding`](primary-video.html#stopframedecoding) | Stop thread used for frame decoding. |

### Parameter

  | Method               | Description |
  |----------------------|-------------|
  | [`getFrameDecodingParameters`](primary-video.html#getframedecodingparameters) | Initialize frame decoding parameter. |

### Status retrieval

  | Method               | Description |
  |----------------------|-------------|
  | [`getLengthOfFrameQueue`](primary-video.html#getlengthofframequeue) | Get length of current inner frame queue. |
