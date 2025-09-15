---
layout: default-layout
title: How to Reduce Battery Consumption?
keywords: Dynamsoft Barcode Reader, FAQ, Mobile, tech basic, ios, battery, consumption
description: How to Reduce Battery Consumption?
needAutoGenerateSidebar: true
---

# How to Reduce Battery Consumption?

[<< Back to FAQ index](index.html)

If you are finding that the battery of your phone is being heavily consumed when using the Barcode Reader, there are a couple of things that you can do to potentially reduce the battery consumption, depending on the usage situation.

For a non-continuous video scanning scenario, make sure to call the [stopScanning](../api-reference/primary-video.html#stopscanning) method when the video scanning is no longer required.

For a continuous video scanning scenario, increase the value of [minImageReadingInterval](../api-reference/primary-video.html#minimagereadinginterval) to reduce the frequency of fetching frames, thus reducing the number of scans per unit time, and thus, less resources needing to be consumed. You can dynamically adjust `minImageReadingInterval` as needed to achieve the performance you are looking for.