---
layout: default-layout
title: On the Barcode Scanner X demo app, there's several modes made for specific use cases, including one for driver licenses. How can I configure my app to do the same?
keywords: Dynamsoft Barcode Reader, FAQ, Mobile, tech basic, android, template, driver license, settings
description: On the Barcode Scanner X demo app, there's several modes made for specific use cases, including one for driver licenses. How can I configure my app to do the same?
needAutoGenerateSidebar: true
---

# On the Barcode Scanner X demo app, there's several modes made for specific use cases, including one for driver licenses. How can I configure my app to do the same?

[<< Back to FAQ index](index.md)


In the Barcode Scanner X app, please go to the use case scenario that you are interested. On the right-bottom, tap on "Export Template". 

Once you get the templates, you can implement them using the [`initRuntimeSettingsWithString`](../api-reference/primary-parameter-and-runtime-settings-advanced.md#initruntimesettingswithstring) or [`initRuntimeSettingsWithFile`](../api-reference/primary-parameter-and-runtime-settings-advanced.md#initruntimesettingswithfile) methods, depending on which input method you prefer.