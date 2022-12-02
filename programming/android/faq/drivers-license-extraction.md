---
layout: default-layout
title: How is the driver's license sample able to extract the information into readable fields? Is DBR responsible for this function?
keywords: Dynamsoft Barcode Reader, FAQ, Mobile, tech basic, android, driver license, info
description: How is the driver's license sample able to extract the information into readable fields? Is DBR responsible for this function?
needAutoGenerateSidebar: false
---

# How is the driver's license sample able to extract the information into readable fields? Is DBR responsible for this function?

[<< Back to FAQ index](index.md)

In the driver's license [sample](../samples/drivers-license.md), the code responsible for extracting the driver license info can be found in the `DBRDriverLicenseUtil` file under the `com.dynamsoft.readadriverlicese` package if you open the project in Android Studio. The file can also be found at the following path inside the project directory: `src/main/java/com/dynamsoft/readadriverlicense`

At the moment, there is no external framework that is responsible for this function in the sample. However, the team is currently developing an edition of our complimentary product, the *Dynamsoft Code Parser*, that is compatible with the mobile platform.