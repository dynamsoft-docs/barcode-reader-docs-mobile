---
layout: default-layout
title: Why does it sometimes Freeze when I Enter the Scan Page? 
keywords: Dynamsoft Barcode Reader, FAQ, Mobile, tech basic, Android, freeze, page
description: Why does it sometimes Freeze when I Enter the Scan Page?
needAutoGenerateSidebar: true
noTitleIndex: true
---

# Why does it sometimes Freeze when I Enter the Scan Page?

[<< Back to FAQ index](index.html)

Before a barcode reader instance can be created, a one-time connection for license validation needs to occur when the app initializes (or whenever the license is set before the barcode reader instance creation). Sometimes, this license validation could take a second to complete.

A potential "freeze" of the page can occur if `BarcodeReader.initLicense()` is called multiple times in a single process. Please make sure that `initLicense` is called only once in your code.

To help troubleshoot whether the method is being called multiple times, we recommend stepping through the code using a debugger.