---
layout: default-layout
title: Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows all methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
breadcrumbText: Methods
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/primary-index-v8.9.3.html
---

# BarcodeReader Class

## Initialize
  
  | Method               | Description |
  |----------------------|-------------|
  | [`init`](primary-initialize.md#init) | Create an instance of Dynamsoft Barcode Reader. |

## Video Decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`setCameraEnhancer`](primary-video.md#setcameraenhancer) | Bind a Camera Enhancer instance to the Barcode Reader.  |
  | [`startScanning`](primary-video.md#startscanning) | Start the barcode reading thread. |
  | [`stopScanning`](primary-video.md#stopscanning) | Stop the barcode reading thread. |
  | [`setDBRTextResultDelegate`](primary-video.md#setdbrtextresultdelegate) | Set callback function to process text results generated during frame decoding. |
  | [`setDBRIntermediateResultDelegate`](primary-video.md#setdbrintermediateresultdelegate) | Set callback function to process intermediate results generated during frame decoding. |

  | Property | Description |
  |----------|-------------|
  | [`enableResultVerification`](primary-video.md#enableresultverification) | Verify the results before output. |
  | [`enableDuplicateFiter`](primary-video.md#enableduplicatefiter) | Output the duplicated result only once for every 3 seconds. |

## Image Decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeBuffer`](primary-decode.md#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeFileWithName`](primary-decode.md#decodefilewithname) | Decode barcodes from a specified image file. |
  | [`decodeImage`](primary-decode.md#decodeimage) | Decode barcodes from an image file in memory. |
  | [`decodeBase64`](primary-decode.md#decodebase64) | Decode barcodes from a base64 encoded string. |

## License

  | Method               | Description |
  |----------------------|-------------|
  | [`license`](primary-license.md#license) | Stores the license used in DynamsoftBarcodeReader. |
  | [`initWithLicense`](primary-license.md#initwithlicense) | Read product key and activate the SDK. |
  | [`initWithLicenseFromServer`](primary-license.md#initwithlicensefromserver) | Initialize license and connect to the specified server for online verification. |
  | [`outputLicenseToString`](primary-license.md#outputlicensetostring) | Output the license content to a string from the license server. |
  | [`initLicenseFromDLS`](primary-license.md#initlicensefromdls) | Initializes the barcode reader license and connects to the specified server for online verification. |
  | `initLicenseFromLTS` | `Deprecated`, please use [`initLicenseFromDLS`](primary-license.md#initlicensefromdls) instead. |

## Parameter and Runtime Settings

### Basic
  
  | Method               | Description |
  |----------------------|-------------|
  | [`getRuntimeSettings`](primary-parameter-and-runtime-settings-basic.md#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings (with struct)`](primary-parameter-and-runtime-settings-basic.md#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`updateRuntimeSettings (with preset template)`](primary-parameter-and-runtime-settings-basic.md#with-a-preset-template) | Update runtime settings from one of the preset templates. |
  | [`resetRuntimeSettings`](primary-parameter-and-runtime-settings-basic.md#resetruntimesettings) | Reset runtime settings to default. |

### Advanced
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initRuntimeSettingsWithFile`](primary-parameter-and-runtime-settings-advanced.md#initruntimesettingswithfile) | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsWithString`](primary-parameter-and-runtime-settings-advanced.md#initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`appendTplFileToRuntimeSettings`](primary-parameter-and-runtime-settings-advanced.md#appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`appendTplStringToRuntimeSettings`](primary-parameter-and-runtime-settings-advanced.md#appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`allParameterTemplateNames`](primary-parameter-and-runtime-settings-advanced.md#allparametertemplatenames) | Get the count of the parameter templates. |
  | [`outputSettingsToFile`](primary-parameter-and-runtime-settings-advanced.md#outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputSettingsToString`](primary-parameter-and-runtime-settings-advanced.md#outputsettingstostring) | Output runtime settings to a string. |
  | [`setModeArgument`](primary-parameter-and-runtime-settings-advanced.md#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`getModeArgument`](primary-parameter-and-runtime-settings-advanced.md#getmodeargument) | Get argument value for the specified mode parameter. |

## Result

  | Method               | Description |
  |----------------------|-------------|
  | [`createIntermediateResult`](primary-result.md#createintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`getIntermediateResult`](primary-result.md#getintermediateresult) | Get intermediate results. |
  | [`decodeIntermediateResults`](primary-result.md#decodeintermediateresults) | Decodes barcode from intermediate results. |

## Camera Enhancer
  
   | Method               | Description |
   |----------------------|-------------|
   | [`SetCameraEnhancerParam`](primary-camera.md#setcameraenhancerparam) | Deprecated, use [`setCameraEnhancer`](primary-video.md#setcameraenhancer) instead. |
