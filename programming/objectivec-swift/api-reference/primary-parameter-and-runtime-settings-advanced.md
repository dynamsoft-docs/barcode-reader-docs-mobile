---
layout: default-layout
title: Parameter and Runtime Settings Advanced Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows advanced Runtime Settings methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: initRuntimeSettingsWithFile, initRuntimeSettingsWithString, appendTplFileToRuntimeSettings, appendTplStringToRuntimeSettings, allParameterTemplateNames, outputSettingsToFile, outputSettingsToString, parameter and runtime settings advanced methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/primary-parameter-and-runtime-settings-advanced.html
---

# Parameter and Runtime Settings Advanced Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initRuntimeSettingsWithFile`](#initruntimesettingswithfile) | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsWithString`](#initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`appendTplFileToRuntimeSettings`](#appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`appendTplStringToRuntimeSettings`](#appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`allParameterTemplateNames`](#allparametertemplatenames) | Gets the parameter templates name array. |
  | [`outputSettingsToFile`](#outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputSettingsToString`](#outputsettingstostring) | Output runtime settings to a string. |
  | [`setModeArgument`](#setmodeargument) | Sets the optional argument for a specified mode in Modes parameters. |
  | [`getModeArgument`](#getmodeargument) | Gets the optional argument for a specified mode in Modes parameters. |

---

## initRuntimeSettingsWithFile

Initialize runtime settings with the parameters obtained from a JSON file.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)initRuntimeSettingsWithFile:(NSString* _Nonnull)fileName
                       conflictMode:(EnumConflictMode)conflictMode
                              error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func initRuntimeSettingsWithFile(_ fileName: String, conflictMode: EnumConflictMode) throws
```

**Parameters**

`[in] fileName`: The settings file path.  
`[in] conflictMode`: The parameter setting mode, which decides whether to inherit parameters from previous template settings or to overwrite previous settings with the new template.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The file is not found.
- There exists parameters that are invalid or out of range.
- The template name is invalid.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader initRuntimeSettingsWithFile:@"your template file path" conflictMode:EnumConflictModeOverwrite error:nil];
```
2. 
```swift
do{
   try barcodeReader.initRuntimeSettingsWithFile("your template file path", conflictMode:EnumConflictMode.overwrite)
}catch{
   // Add your code to deal with exceptions
}
```

## initRuntimeSettingsWithString

Initialize runtime settings with the parameters obtained from a JSON string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)initRuntimeSettingsWithString:(NSString* _Nonnull)content
                         conflictMode:(EnumConflictMode)conflictMode
                                error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func initRuntimeSettingsWithString(_ content: String, conflictMode: EnumConflictMode) throws
```

**Parameters**

`[in] content`: A JSON string that represents the content of the settings.  
`[in] conflictMode`: The parameter setting mode, which decides whether to inherit parameters from previous template setting or to overwrite previous settings with the new template.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to parse the JSON string.
- There exists parameters that are invalid or out of range.
- The template name is invalid.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader initRuntimeSettingsWithString:@"{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}" conflictMode:EnumConflictModeOverwrite error:nil];
```
2. 
```swift
do{
   try barcodeReader.initRuntimeSettingsWithString("{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}", conflictMode:EnumConflictMode.overwrite)
}catch{
   // Add your code to deal with exceptions
}
```

## appendTplFileToRuntimeSettings

Append a new template file to the current runtime settings.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)appendTplFileToRuntimeSettings:(NSString * _Nonnull)fileName
                          conflictMode:(EnumConflictMode)conflictMode
                                 error:(NSError * _Nullable *_Nullable)error;
```
2. 
```swift
func appendTplFileToRuntimeSettings(_ fileName: String, conflictMode: EnumConflictMode) throws
```

**Parameters**

`[in] fileName`: The settings file path.  
`[in] conflictMode`: The parameter setting mode, which decides whether to inherit parameters from previous template settings or to overwrite previous settings with the new template.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The file is not found.
- There exists parameters that are invalid or out of range.
- The template name is invalid.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader appendTplFileToRuntimeSettings:@"your template file path" conflictMode:EnumConflictModeIgnore error:nil];
```
2. 
```swift
do{
   try barcodeReader.appendTplFileToRuntimeSettings("your template file path", conflictMode:EnumConflictMode.ignore, error:&error)
}catch{
   // Add your code to deal with exceptions
}
```

## appendTplStringToRuntimeSettings

Append a new template string to the current runtime settings.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)appendTplStringToRuntimeSettings:(NSString * _Nonnull)content
                            conflictMode:(EnumConflictMode)conflictMode
                                   error:(NSError *_Nullable *_Nullable)error;
```
2. 
```swift
func appendTplStringToRuntimeSettings(_ content: String, conflictMode: EnumConflictMode) throws
```

**Parameters**

`[in] content`: A JSON string that represents the content of the settings.  
`[in] conflictMode`: The parameter setting mode, which decides whether to inherit parameters from previous template setting or to overwrite previous settings with the new template.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to parse the JSON string.
- There exists parameters that are invalid or out of range.
- The template name is invalid.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader initRuntimeSettingsWithString:@"{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}" conflictMode:EnumConflictModeOverwrite error:nil];
[barcodeReader appendTplStringToRuntimeSettings:@"{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_OneD\"], \"ExpectedBarcodesCount\":20}}" conflictMode:EnumConflictModeIgnore error:nil];
```
2. 
```swift
do{
   try barcodeReader.initRuntimeSettingsWithString("{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}", conflictMode:EnumConflictMode.Overwrite)
   try barcodeReader.appendTplStringToRuntimeSettings("{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_OneD\"], \"ExpectedBarcodesCount\":20}}", conflictMode:EnumConflictMode.ignore)
}catch{
   // Add your code to deal with exceptions
}
```

## allParameterTemplateNames

Get count of parameter templates.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSArray<NSString*>* _Nullable)allParameterTemplateNames: (NSError *__autoreleasing  _Nullable * _Nullable)error;
```
2. 
```swift
func allParameterTemplateNames() throws -> [String]
```

**Parameters**

`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to get all template names.

**Return Value**

The template name array.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSArray* allTplNames = [barcodeReader allParameterTemplateNames:nil];
```
2. 
```swift
let allTplNames = do{
   try barcodeReader.allParameterTemplateNames()
}catch{
   // Add your code to deal with exceptions
}
```

## outputSettingsToFile

Outputs runtime settings and save them into a settings file (JSON file).  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)outputSettingsToFile:(NSString *_Nullable)filePath 
                settingsName:(NSString*_Nonnull)settingsName 
                       error:(NSError*_Nullable *_Nullable)error;
```
2. 
```swift
func outputSettingsToFile(_ filePath: String?, settingsName: String) throws
```

**Parameters**

`[in] filePath` The path of the output file which stores current settings.  
`[in] settingsName` A unique name for declaring current runtime settings.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The file path is not found.
- The library failed to output the settings.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
settingsName = [barcodeReader outputSettingsToFile:@"your saving file path" settingsName:@"currentRuntimeSettings" error:nil];
```
2. 
```swift
do{
   let settingsName = try barcodeReader.outputSettingsToFile("your saving file path", settingsName:"currentRuntimeSettings")
}catch{
   // Add your code to deal with exceptions
}
```

## outputSettingsToString

Output runtime settings to a string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSString *_Nullable)outputSettingsToString:(NSString*_Nonnull)settingsName 
                                        error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func outputSettingsToString(_ settingsName: String) throws -> String
```

**Parameters**

`[in] settingsName` A unique name for declaring current runtime settings.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to output the settings.

**Return Value**

The output string which stores the content of current settings.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
settingsName = [barcodeReader outputSettingsToString:@"currentRuntimeSettings" error:nil];
```
2. 
```swift
do{
   let settingsName = try barcodeReader.outputSettingsToString("currentRuntimeSettings")
}catch{
   // Add your code to deal with exceptions
}
```

## setModeArgument

Sets the optional argument for a specified mode in Modes parameters.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)setModeArgument:(NSString* _Nonnull)modeName
                    index:(NSInteger)index 
                    argumentName:(NSString* _Nonnull)argumentName
                    argumentValue:(NSString* _Nonnull)argumentValue
                    error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func setModeArgument(_ modeName: String, index: Int, argumentName: String, argumentValue: String) throws
```

**Parameters**

`[in] modesName` The mode parameter name to set argument.  
`[in] index` The array index of mode parameter to indicate a specific mode.  
`[in] argumentName` The name of the argument to set.  
`[in] argumentValue` The value of the argument to set.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to set the mode argument. It might because you input incorrect `modeName`, `index`, `argumentName` or `argumentValue`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
iPublicRuntimeSettings *settings = [barcodeReader getRuntimeSettings:nil];
settings.binarizationModes = @[@(EnumBinarizationModeLocalBlock)];
[barcodeReader updateRuntimeSettings:settings error:nil];
[barcodeReader setModeArgument:@"BinarizationModes" index:0 argumentName:@"EnableFillBinaryVacancy" argumentValue:"1" error:nil];
```
2. 
```swift
do{
   let settings = try barcodeReader.getRuntimeSettings()
   settings.binarizationModes = [EnumBinarizationMode.localBlock]
   try barcodeReader.updateRuntimeSettings(settings)
   try barcodeReader.setModeArgument("BinarizationModes", index: 0, argumentName: "EnableFillBinaryVacancy", argumentValue: "1")
}catch{
   // Add your code to deal with exceptions
}
```

**Remarks**

Check follow link for available modes and arguments:

- [`BarcodeColourModes`]({{ site.parameters_reference }}barcode-colour-modes.html)
- [`BinarizationModes`]({{ site.parameters_reference }}binarization-modes.html)
- [`ColourClusteringModes`]({{ site.parameters_reference }}colour-clustering-modes.html)
- [`ColourConversionModes`]({{ site.parameters_reference }}colour-conversion-modes.html)
- [`DeformationResistingModes`]({{ site.parameters_reference }}deformation-resisting-modes.html)
- [`ImagePreprocessingModes`]({{ site.parameters_reference }}image-preprocessing-modes.html)
- [`IntermediateResultSavingMode`]({{ site.parameters_reference }}intermediate-result-saving-mode.html)
- [`LocalizationModes`]({{ site.parameters_reference }}localization-modes.html)
- [`RegionPredetectionModes`]({{ site.parameters_reference }}region-predetection-modes.html)
- [`ScaleUpModes`]({{ site.parameters_reference }}scale-up-modes.html)
- [`TextFilterModes`]({{ site.parameters_reference }}text-filter-modes.html)
- [`TextureDetectionModes`]({{ site.parameters_reference }}texture-detection-modes.html)

## getModeArgument

Gets the optional argument for a specified mode in Modes parameters.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSString* _Nonnull)getModeArgument:(NSString* _Nonnull)modeName
                               index:(NSInteger)index
                        argumentName:(NSString* _Nonnull)argumentName
                               error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func getModeArgument(_ modeName: String, index: Int, argumentName: String) throws -> String
```

**Parameters**

`[in] modesName` The mode parameter name to get arguments.  
`[in] index` The array index of mode parameter to indicate a specific mode.  
`[in] argumentName` The name of the argument to get.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to get the mode argument. It might because you input incorrect `modeName`, `index` or `argumentName`.

**Return Value**

the optional argument for a specified mode

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
iPublicRuntimeSettings *settings = [barcodeReader getRuntimeSettings:nil];
settings.binarizationModes = @[@(EnumBinarizationModeLocalBlock)];
[barcodeReader updateRuntimeSettings:settings error:nil];
[barcodeReader setModeArgument:@"BinarizationModes" index:0 argumentName:@"EnableFillBinaryVacancy" argumentValue:"1" error:nil];
argumentValue = [barcodeReader getModeArgument:@"BinarizationModes" index:0 argumentName:@"EnableFillBinaryVacancy" error:&error];
```
2. 
```swift
let settings = do{
   try barcodeReader.getRuntimeSettings()
   settings.binarizationModes = [EnumBinarizationMode.localBlock]
   try barcodeReader.updateRuntimeSettings(settings)
   try barcodeReader.setModeArgument("BinarizationModes", index: 0, argumentName: "EnableFillBinaryVacancy", argumentValue: "1")
   let argumentValue = try barcodeReader.getModeArgument("BinarizationModes", index: 0, argumentName: "EnableFillBinaryVacancy")
}catch{
   // Add your code to deal with exceptions
}
```

**Remarks**

Check follow link for available modes and arguments:

- [`BarcodeColourModes`]({{ site.parameters_reference }}barcode-colour-modes.html)
- [`BinarizationModes`]({{ site.parameters_reference }}binarization-modes.html)
- [`ColourClusteringModes`]({{ site.parameters_reference }}colour-clustering-modes.html)
- [`ColourConversionModes`]({{ site.parameters_reference }}colour-conversion-modes.html)
- [`DeformationResistingModes`]({{ site.parameters_reference }}deformation-resisting-modes.html)
- [`ImagePreprocessingModes`]({{ site.parameters_reference }}image-preprocessing-modes.html)
- [`IntermediateResultSavingMode`]({{ site.parameters_reference }}intermediate-result-saving-mode.html)
- [`LocalizationModes`]({{ site.parameters_reference }}localization-modes.html)
- [`RegionPredetectionModes`]({{ site.parameters_reference }}region-predetection-modes.html)
- [`ScaleUpModes`]({{ site.parameters_reference }}scale-up-modes.html)
- [`TextFilterModes`]({{ site.parameters_reference }}text-filter-modes.html)
- [`TextureDetectionModes`]({{ site.parameters_reference }}texture-detection-modes.html)
