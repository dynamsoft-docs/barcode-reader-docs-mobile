---
layout: default-layout
title: How to Solve the "Undefined symbols for architecture armv7" Error Building on iOS?
keywords: Dynamsoft Barcode Reader, FAQ, Mobile, tech basic, ios, armv7, undefined symbols
description: How to Solve the "Undefined symbols for architecture armv7" Error Building on iOS?
needAutoGenerateSidebar: true
permalink: /programming/android/faq/armv7-architecture-error-v9.6.30.html
---

# How to Solve the "Undefined symbols for architecture armv7" Error Building on iOS?

[<< Back to FAQ index](index.html)

DBR iOS is compatible with the arm64 and x86_64 architectures only. If you attempt to build an app that is targetting the armv7 architecture, you will be met with an error from the Barcode Reader framework saying

> Undefined symbols for architecture armv7

Please note that this will mostly occur with older versions of Xcode or iOS that are still compatible with the older iOS device models that used the armv7 architecture. For most devices that are able to run iOS 11 and higher, the architecture will be arm64.

By default, when you set the *Architectures* in *Build Settings* to the "$(ARCHS_STANDARD) - Standard Architectures (arm64)", the armv7 architecture should automaticallt not be included. To ensure that your app ignores the armv7 architecture, you can add it to the *Excluded Architectures* field of the *Build Settings*.