---
layout: default-layout
title: How to reduce battery consumption when using the Barcode Reader? 
keywords: Dynamsoft Barcode Reader, FAQ, Mobile, tech basic, Android, battery, consumption
description: How to reduce battery consumption when using the Barcode Reader? 
needAutoGenerateSidebar: false
---

# How to reduce the final size of your android app?

[<< Back to FAQ index](index.md)

It is recommended that you distribute your app using App Bundle in order to reduce the final size of the Android app.

The second step is to to utilize APK splits. To learn more about this, please refer to this [page](https://developer.android.com/studio/build/configure-apk-splits#configure-abi-split).

The third thing to do is to to remove processor architecture support. If you won't be distributing your app via Google Play, please refer to this [page](https://developer.android.com/ndk/guides/abis#gc) on how to proceed with this step.