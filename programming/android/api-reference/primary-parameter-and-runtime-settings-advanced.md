---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - BarcodeReader Parameter and Runtime Settings Advanced Methods
description: This page shows BarcodeReader advanced runtime settings methods of Dynamsoft Barcode Reader for Android SDK.
keywords: initRuntimeSettingsWithFile, initRuntimeSettingsWithString, appendTplFileToRuntimeSettings, appendTplStringToRuntimeSettings, getAllParameterTemplateNames, outputSettingsToFile, outputSettingsToString, parameter and runtime settings advanced methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/android/api-reference/primary-parameter-and-runtime-settings-advanced.html
---

# Parameter and Runtime Settings Advanced Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initRuntimeSettingsWithFile`](#initruntimesettingswithfile)  | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsWithString`](#initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`appendTplFileToRuntimeSettings`](#appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`appendTplStringToRuntimeSettings`](#appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`getAllParameterTemplateNames`](#getallparametertemplatenames) | Gets the parameter templates name array. |
  | [`outputSettingsToFile`](#outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputSettingsToString`](#outputsettingstostring) | Output runtime settings to a string. |
  | [`setModeArgument`](#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`getModeArgument`](#getmodeargument) | Get argument value for the specified mode parameter. |

  ---

## initRuntimeSettingsWithFile

Initialize runtime settings with the settings in a given JSON file.

```java
void initRuntimeSettingsWithFile(String filePath, int enumConflictMode) throws BarcodeReaderException
```

**Parameters**

`filePath`: The path of the settings file.  
`enumConflictMode`: The parameter setting mode, which decides whether to inherit parameters from the previous template setting or to overwrite previous settings and replace with the new template.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- The file is not found.
- There exists parameters that are invalid or out of range.
- The template name is invalid.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.initRuntimeSettingsWithFile("your template file path", EnumConflictMode.CM_OVERWRITE);
```

## initRuntimeSettingsWithString

Initialize runtime settings with the settings in a given JSON string.

```java
void initRuntimeSettingsWithString(String content, int enumConflictMode)throws BarcodeReaderException
```

**Parameters**

`content`: A JSON string that represents the content of the settings.  
`enumConflictMode`: The parameter setting mode, which decides whether to inherit parameters from previous template setting or to overwrite previous settings and replace with the new template.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- The library failed to parse the JSON string.
- There exists parameters that are invalid or out of range.
- The template name is invalid.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.initRuntimeSettingsWithString("{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}", EnumConflictMode.CM_OVERWRITE);
```

## appendTplFileToRuntimeSettings

Append a new template file to the current runtime settings.

```java
void appendTplFileToRuntimeSettings(String filePath, int enumConflictMode) throws BarcodeReaderException
```

**Parameters**

`filePath`: The path of the settings file.  
`enumConflictMode`: The parameter setting mode, which decides whether to inherit parameters from previous template setting or to overwrite previous settings with the new template.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- The file is not found.
- There exists parameters that are invalid or out of range.
- The template name is invalid.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.appendTplFileToRuntimeSettings("your template file path", EnumConflictMode.CM_IGNORE);
```

## appendTplStringToRuntimeSettings

Append a new template string to the current runtime settings.

```java
void appendTplStringToRuntimeSettings(String content, int enumConflictMode) throws BarcodeReaderException
```

**Parameters**

`content`: A JSON string that represents the content of the settings.  
`enumConflictMode`: The parameter setting mode, which decides whether to inherit parameters from previous template setting or to overwrite previous settings with the new template.  

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- The library failed to parse the JSON string.
- There exists parameters that are invalid or out of range.
- The template name is invalid.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.initRuntimeSettingsWithString("{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}", EnumConflictMode.CM_OVERWRITE);
reader.appendTplStringToRuntimeSettings("{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_OneD\"], \"ExpectedBarcodesCount\":20}}", EnumConflictMode.CM_IGNORE);
```

## getAllParameterTemplateNames

Gets the parameter templates name array.

```java
String [] getAllParameterTemplateNames()
```

**Return Value**

The template name array.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- The library failed to get all template names.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
String[] templateNames = reader.getAllParameterTemplateNames();
```

## outputSettingsToFile

Output runtime settings to a settings file (JSON file).

```java
void outputSettingsToFile(String filePath, String settingsName) throws BarcodeReaderException
```

**Parameters**

`filePath`: The output file path which stores current settings.  
`settingsName`: A unique name for declaring current runtime settings.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- The file path is not found.
- The library failed to output the settings.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.outputSettingsToFile("your saving file path", "currentRuntimeSettings");
```

## outputSettingsToString

Output runtime settings to a string.

```java
String outputSettingsToString(String settingsName) throws BarcodeReaderException
```

**Parameters** 

`settingsName` A unique name for declaring current runtime settings.  

**Return Value**

The output string which stores the contents of current settings.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- The library failed to output the settings.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
String settingStr = reader.outputSettingsToString("currentRuntimeSettings");
```

## setModeArgument

**Mode arguments** are the optional settings of **mode parameters** in **PublicRuntimeSettings**. You can use `setModeArgument` to configure these arguments.

```java
void setModeArgument(String modesName, int index, String argumentName, String argumentValue) throws BarcodeReaderException
```

**Parameters**

`modesName`: The name of the **mode parameter** that you want to make changes.  
`index`: The array index of **mode parameter**.  
`argumentName`: The name of the **mode argument** to set.  
`argumentValue`: The value of the **mode argument** to set.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- The library failed to set the mode argument. It might because you input incorrect `modeName`, `index`, `argumentName` or `argumentValue`.

**Code Snippet**

Suppose that you specified `[BM_LOCAL_BLOCK, BM_THRESHOLD]` for **mode parameter** `binarizationModes` and you want to set the value of **mode argument** `EnableFillBinaryVacancy` of mode `BM_LOCAL_BLOCK` to 1. The following code snippet is how you can make the settings:

```java
// This is the code that you specify the mode parameter binarizationModes.
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.binarizationModes[0] = EnumBinarizationMode.BM_LOCAL_BLOCK;
settings.binarizationModes[1] = EnumBinarizationMode.BM_THRESHOLD;
reader.updateRuntimeSettings(settings);
// This is the code that you set the mode argument.
reader.setModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy", "1");
```

**Remarks**

Check the available modes and arguments below:

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

Get the current setting of the specified **mode argument**.

```java
String getModeArgument(String modesName, int index, String argumentName) throws BarcodeReaderException
```

**Parameters**

`modesName`: The name of the **mode parameter** that you want to make changes.  
`index`: The array index of **mode parameter**.  
`argumentName`: The name of the **mode argument** to set.

**Return Value**

the optional argument for a specified mode in Modes parameters.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- The library failed to get the mode argument. It might because you input incorrect `modeName`, `index` or `argumentName`.

**Code Snippet**

```java
// You set EnableFillBinaryVacancy to 1 with these code.
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.binarizationModes[0] = EnumBinarizationMode.BM_LOCAL_BLOCK;
reader.updateRuntimeSettings(settings);
reader.setModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy", "1");
// The return value you got from getModeArgument is 1
String argumentValue = reader.getModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy");
```

**Remarks**

Check the available modes and arguments below:

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
