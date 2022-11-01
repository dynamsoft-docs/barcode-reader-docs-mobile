---
layout: default-layout
title: My barcode is not being picked up using the Barcode Scanner X app. Does this mean that your SDK cannot read the image?
keywords: Dynamsoft Barcode Reader, FAQ, Mobile, tech basic, ios, template, driver license, settings
description: My barcode is not being picked up using the Barcode Scanner X app. Does this mean that your SDK cannot read the image?
needAutoGenerateSidebar: false
---

# My barcode is not being picked up using the Barcode Scanner X app. Does this mean that your SDK cannot read the image?

[<< Back to FAQ index](index.md)

When using Barcode Scanner X in *General Scan* mode, it defaults to the *Speed First* template. If the barcode you are trying to read is not getting picked up under those settings, it is best to access the settings and select the *Read Rate First* template under Scan Mode. This template applies more rigorous algorithms to try and recognize the barcode. 

If the barcode is still not being read with that template, then you can also try taking a picture of the barcode using your camera and then loading in that image instead of using the camera via the top-right image icon.

One more thing to try if the barcode is not being picked up at all by the Barcode Scanner X mobile app is to use our main [online demo](https://demo.dynamsoft.com/barcode-reader/). Using this demo, you can take a picture from your phone directly, or upload a photo from your library. On the left-hand side of the page, you will see a slider for selecting which mode the SDK is running with. Please select the *Best Coverage* option to make sure the SDK tries most of the available algorithms.

If the problem is persisting, please get in touch with the Dynamsoft Support team. The team will be able to investigate your barcode image and provide you with a template that is suited for it.