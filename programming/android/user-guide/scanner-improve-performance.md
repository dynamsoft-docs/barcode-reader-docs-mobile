---
layout: default-layout
title: Improve the Performance of BarcodeScanner - Dynamsoft Barcode Reader for Android
description: Improve the performance of BarcodeScanner on Android platform.
keywords: BarcodeScanner, scanner, Android, template file
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Improve the Performance of BarcodeScanner

Using a template file is the quickest way to improve the performance of BarcodeScanner. A template file is a JSON file (or JSON string) that includes a series of algorithm parameter settings. [Contact us](https://www.dynamsoft.com/company/customer-service/#contact) to get a customized template for your scanner.

1. Add a **Templates** folder to the assets folder of your project at **src\main\assets\Templates**. Put your JSON file in the **Templates** folder. Here we use a **ReadQRCode.json** file as an example.

    <div align="left">
    <p><img src="../../assets/init-settings-from-file-android.png" alt="initSettings" width="50%" /></p>
    </div>

2. Specify the template file via `setTemplateFile`

    <div class="sample-code-prefix"></div>
    >- Java
    >- Kotlin
    >
    >1. 
    ```java
    BarcodeScannerConfig config = new BarcodeScannerConfig();
    config.setTemplateFile("ReadQRCodes.json");
    ```
    2. 
    ```kotlin
    val config = BarcodeScannerConfig().apply {
       templateFile = "ReadQRCodes.json"
    }
    ```

**Related APIs**

- [`setTemplateFile`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#settemplatefile)
