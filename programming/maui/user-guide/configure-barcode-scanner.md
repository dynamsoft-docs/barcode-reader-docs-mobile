---
layout: default-layout
title: Configure Barcode Scanner - Dynamsoft Barcode Scanner MAUI Edition
description: Configure the Barcode scan settings via BarcodeScannerConfig class when using Barcode Scanner MAUI Edition
keywords: Configure, config, BarcodeScannerConfig, MAUI
breadcrumbText: Configure Barcode Scanner
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Configure Barcode Scanner

When developing with `BarcodeScanner` component, you can add configurations via the `BarcodeScannerConfig` class. This page will guide you on how to configure the settings.

## Setup a customized template file

A template file is a JSON file that includes a series of algorithm parameter settings. It is always used to customize the performance for different usage scenarios. [Contact us](https://www.dynamsoft.com/company/customer-service/#contact) to get a customized template for your scanner.

1. Put your JSON file in the **Resources\Raw** folder of your project.

2. Specify the template file via `TemplateFile`

```csharp
var config = new BarcodeScannerConfig("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
config.TemplateFile = "CustomizedTemplate.json";
```

> [!NOTE] You can also use a JSON string as the template file.

**Related APIs**

- [`TemplateFile`]({{ site.dbr_maui_api }}barcode-scanner/barcode-scanner-config.html#templatefile)

## Configure the UI Elements

- Close button: Stop Barcode scanning and go back to the previous activity.
- Torch button: A clickable button that can turn on/off the torch.

```csharp
var config = new BarcodeScannerConfig("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
config.IsTorchButtonVisible = true;
config.IsGuideFrameVisible = true;
config.IsCloseButtonVisible = true;
```

**Related APIs**

- [`IsTorchButtonVisible`]({{ site.dbr_maui_api }}barcode-scanner/barcode-scanner-config.html#istorchbuttonvisible)
- [`IsGuideFrameVisible`]({{ site.dbr_maui_api }}barcode-scanner/barcode-scanner-config.html#isguideframevisible)
- [`IsCloseButtonVisible`]({{ site.dbr_maui_api }}barcode-scanner/barcode-scanner-config.html#isclosebuttonvisible)

### Beep

Let the app to trigger a beep sound when Barcode is scanned successfully.

```csharp
var config = new BarcodeScannerConfig("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
config.IsBeepEnabled = true;
```

**Related API**

- [`IsBeepEnabled`]({{ site.maui_api }}barcode-scanner/barcode-scanner-config.html#setbeepenabled)
