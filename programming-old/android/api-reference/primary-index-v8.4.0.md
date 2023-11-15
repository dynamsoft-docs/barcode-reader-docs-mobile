---
layout: default-layout
title: BarcodeReader Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader methods of Dynamsoft Barcode Reader for Android SDK.
keywords: methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: BarcodeReader Class
permalink: /programming/android/api-reference/primary-index-v8.4.0.html
---

# BarcodeReader Class

## Initialize

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](primary-initialize-and-destroy.html#barcodereader) | Initialization of `BarcodeReader` object.|

## Decode

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeFile`](primary-decode.html#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](primary-decode.html#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`decodeBuffer`](primary-decode.html#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeBase64String`](primary-decode.html#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](primary-decode.html#decodeBufferedImage) | Decodes barcode from a buffered image (bitmap). |

## Camera Enhancer
  
   | Method               | Description |
   |----------------------|-------------|
   | [`StartCameraEnhancer`](primary-camera.html#start-stop-pause-resume-camera-enhancer) | Start using Dynamsoft Camera Enhancer |
   | [`StopCameraEnhancer`](primary-camera.html#start-stop-pause-resume-camera-enhancer) | Stop using Dynamsoft Camera Enhancer |
   | [`PauseCameraEnhancer`](primary-camera.html#start-stop-pause-resume-camera-enhancer) | Pause the process of Dynamsoft Camera Enhancer |
   | [`ResumeCameraEnhancer`](primary-camera.html#start-stop-pause-resume-camera-enhancer) | Pause the process of Dynamsoft Camera Enhancer |
   | [`SetCameraEnhancerParam`](primary-camera.html#setcameraenhancerparam) | Set the parameters for Dynamsoft Camera Enhancer in Barcode reader |

## License

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](primary-license.html#initlicense) | Read product key and activate the SDK. |
  | [`initLicenseFromServer`](primary-license.html#initlicensefromserver) | Initialize license and connect to the specified server for online verification. |
  | [`initLicenseFromLicenseContent`](primary-license.html#initlicensefromlicensecontent) | Initialize license from the license content on client machine for offline verification. |
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
   | [`initFrameDecodingParameters`](primary-video.html#initframedecodingparameters) | Initialize frame decoding parameter. |

### Callback

   | Method               | Description |
   |----------------------|-------------|
   | [`setErrorCallback`](primary-video.html#seterrorcallback) | Set callback interface to process errors generated during frame decoding. |
   | [`setTextResultCallback`](primary-video.html#settextresultcallback) | Set callback interface to process text results generated during frame decoding. |
   | [`setIntermediateResultCallback`](primary-video.html#setintermediateresultcallback) | Set callback interface to process intermediate results generated during frame decoding. |

### Status retrieval

   | Method               | Description |
   |----------------------|-------------|
   | [`getLengthOfFrameQueue`](primary-video.html#getlengthofframequeue) | Get length of current inner frame queue. |
