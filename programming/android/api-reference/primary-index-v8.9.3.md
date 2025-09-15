---
layout: default-layout
title: BarcodeReader Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader methods of Dynamsoft Barcode Reader for Android SDK.
keywords: methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: BarcodeReader Class
pageStartVer: 8.6
permalink: /programming/android/api-reference/primary-index-v8.9.3.html
---

# BarcodeReader Class

## Initialize

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](primary-initialize-and-destroy.html#barcodereader) | Initialization of `BarcodeReader` object.|

## Video Decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`setCameraEnhancer`](primary-video.html#setcameraenhancer) | Bind a Camera Enhancer instance to the Barcode Reader.  |
  | [`startScanning`](primary-video.html#startscanning) | Start the barcode reading thread. |
  | [`stopScanning`](primary-video.html#stopscanning) | Stop the barcode reading thread. |
  | [`setTextResultCallback`](primary-video.html#settextresultcallback) | Set callback interface to process text results generated during frame decoding. |
  | [`setIntermediateResultCallback`](primary-video.html#setintermediateresultcallback) | Set callback interface to process intermediate results generated during frame decoding. |
  | [`enableResultVerification`](primary-video.html#enableresultverification) | Enable **Result Verification** feature to improve the accuracy of barcode results for video streaming barcode decoding. |
  | [`enableDuplicateFilter`](primary-video.html#enableduplicatefilter) | Enable **Duplicate Filter** feature to filter out the duplicate results in the period of 3000ms for video barcode decoding. |

## Image Decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeBuffer`](primary-decode.html#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeFile`](primary-decode.html#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](primary-decode.html#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`decodeBase64String`](primary-decode.html#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](primary-decode.html#decodeBufferedImage) | Decodes barcode from a buffered image (bitmap). |
  | [`initIntermediateResult`](primary-decode.html#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`decodeIntermediateResults`](primary-result.html#decodeintermediateresults) | Decodes barcode from intermediate results. |

## License

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](primary-license.html#initlicense) | Read product key and activate the SDK. |
  | [`initLicenseFromServer`](primary-license.html#initlicensefromserver) | Initialize license and connect to the specified server for online verification. |
  | [`initLicenseFromLicenseContent`](primary-license.html#initlicensefromlicensecontent) | Initialize license from the license content on client machine for offline verification. |
  | [`outputLicenseToString`](primary-license.html#outputlicensetostring) | Output the license content to a string from the license server. |
  | [`initLicenseFromDLS`](primary-license.html#initlicensefromdls) | Initializes the barcode reader license and connects to the specified server for online verification. |
  | `initLicenseFromLTS` | `Deprecated`, please use [`initLicenseFromDLS`](primary-license.html#initlicensefromdls) instead. |

## Parameter and Runtime Settings

### Basic

  | Method               | Description |
  |----------------------|-------------|
  | [`getRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings (with struct)`](primary-parameter-and-runtime-settings-basic.html#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`updateRuntimeSettings (with preset template)`](primary-parameter-and-runtime-settings-basic.html#with-a-preset-template) | Update runtime settings from one of the preset templates. |
  | [`resetRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#resetruntimesettings) | Reset runtime settings to default. |

### Advanced
  
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

## Result

  | Method               | Description |
  |----------------------|-------------|
  | [`initIntermediateResult`](primary-result.html#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`getIntermediateResults`](primary-result.html#getintermediateresults) | Get intermediate results. |
  | [`decodeIntermediateResults`](primary-result.html#decodeintermediateresults) | Decodes barcode from intermediate results. |

## Status Retrieval

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](primary-status-retrieval.html#getversion) | Get version information of SDK.|

## Camera Enhancer
  
   | Method               | Description |
   |----------------------|-------------|
   | [`StartCameraEnhancer`](primary-camera.html#startcameraenhancer) | Deprecated, use [`startScanning`](primary-video.html#startscanning) instead. |
   | [`StopCameraEnhancer`](primary-camera.html#stopcameraenhancer) | Deprecated, use [`stopScanning`](primary-video.html#stopscanning) instead. |
   | [`PauseCameraEnhancer`](primary-camera.html#pausecameraenhancer) | Deprecated, use [`stopScanning`](primary-video.html#stopscanning) instead. |
   | [`ResumeCameraEnhancer`](primary-camera.html#resumecameraenhancer) | Deprecated, use [`startScanning`](primary-video.html#startscanning) instead. |
   | [`SetCameraEnhancerParam`](primary-camera.html#setcameraenhancerparam) | Deprecated, use [`setCameraEnhancer`](primary-video.html#setcameraenhancer) instead. |
