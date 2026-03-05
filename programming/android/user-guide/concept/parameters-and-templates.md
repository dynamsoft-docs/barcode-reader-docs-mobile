---
layout: default-layout
title: Parameters & Settings - Dynamsoft Barcode Reader Android
description: Learn how to use parameters, settings, and templates in the Dynamsoft Barcode Reader Android SDK.
keywords: user guide, parameters, settings, Android, java, kotlin
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Parameters, Settings & Templates

- `Parameters`: Algorithm `parameters` that determine how images are processed.
- `Settings`: APIs that let you quickly access `parameters`.
- `Templates`: JSON objects that can define all available `parameters`.
- `Preset Templates`: Quick-start templates. Available via `EnumPresetTemplate`.
- `Customized Templates`: Customized templates in a JSON file.

### When to Use Settings

Settings are integrated under `SimplifiedCaptureVisionSettings`, which is a subset of the parameter template. Commonly used parameters are exposed in `SimplifiedCaptureVisionSettings` so you can access them quickly.

Available setting examples:

- Barcode formats
- Expected barcodes count
- ROI
- Timeout
- Image capture interval

Generally, settings are used together with `Preset Templates`.

Common steps:

1. Select a `Preset Template`.
2. Apply minor optimizations with `SimplifiedCaptureVisionSettings`.

### When to Use a Customized Template

If you are not satisfied with the current performance, you can contact us for full customization. You will then receive a customized template.

### Next Steps

- [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_android_api }}capture-vision-router/simplified-capture-vision-settings.html) API references
- How to use customized templates - [initSettingsFromFile]({{ site.dcvb_android_api }}capture-vision-router/settings.html#initsettingsfromfile)
