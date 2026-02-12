---
layout: default-layout
title: Understand Barcode Results - Dynamsoft Barcode Reader for Android
description: Understand the structure of the barcode decoding results of Dynamsoft Barcode Reader Android.
keywords: understand results, Android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Understanding Barcode Results

`DecodedBarcodesResult` is the barcode-type result returned by the Dynamsoft Barcode Reader SDK. It represents all barcode-related information captured from a single image or video frame.

It contains:

- All decoded barcodes.
- Metadata about the original image.
- Error information when a failure occurs.
- A rotation transformation matrix if the original image includes rotation info.

```java
mRouter.addResultReceiver(new CapturedResultReceiver() {
    @Override
    public void onDecodedBarcodesReceived(@NonNull DecodedBarcodesResult result) {
        if (result.getItems().length!=0)
        {
            for(BarcodeResultItem item:result.getItems())
            {
                String barcodeText = barcodeResultItem.getText();
                String barcodeFormatString = barcodeResultItem.getFormatString();
            }
        }
    }
});
```

## How to Use

### Check Error Messages

Error messages are typically caused by:

- The barcode reading task is not working properly.
- The operation timeout.

```java
mRouter.addResultReceiver(new CapturedResultReceiver() {
    @Override
    public void onDecodedBarcodesReceived(@NonNull DecodedBarcodesResult result) {
        if (result.getErrorCode()!= EnumErrorCode.EC_OK)
        {
            // Handle the error.
        }
    }
});
```

> [!Note]
> You might still receive barcode results even when the error message is not empty.

### Access decoded barcodes

Each decoded barcode is a `BarcodeResultItem` from `result.getBarcodes`. The following is an example:

![barcode-result-item](../../assets/barcode-result-item.png)

| BarcodeResultItem |  |
| ----------------- | -- |
| `format` | 67108864 |
| `formatString` | QR_CODE |
| `text` | www.dynamsoft.com |
| `bytes` | [119],[119],[119],[46],[100],[121],...... |
| `location` | Point(196, 1101), Point(518, 1000),...... |
| `confidence` | 86 |
| `angle` | 345 |
| `moduleSize` | 10 |
| `isDPM` | FALSE |
| `isMirrored` | FALSE |
| `details` | rows = 2<br>columns = 2<br>errorCorrectionLevel = L<br>version = 2<br>model = 2<br>mode = 7<br>page = -1<br>totalPage = -1<br>parityData = 0<br>dataMaskPattern = 2<br>codewords = ...... |

### Common fields to use

- `text`: The decoded string. This is the most common field used for downstream processing.
- `formatString`: The barcode symbology (for example, `QR_CODE`, `EAN_13`).
- `bytes`: Raw payload bytes. By default, barcode text is interpreted using ISO-8859-1. Use this when the payload contains binary data or requires custom decoding.
- `location`: Corner points of the barcode in the image, useful for drawing overlays.
- `confidence`: A confidence score. Higher values indicate more reliable decoding.
- `details`: Symbology-specific details (varies by barcode type).

### Access the Original Image

The original image is not returned by default. In `onDecodedBarcodesReceived`, you receive the original image `HashId`. Use it to fetch the image when needed.

**Code Snippet**

```java
mRouter.addResultReceiver(new CapturedResultReceiver() {
    @Override
    public void onDecodedBarcodesReceived(@NonNull DecodedBarcodesResult result) {
        ImageData originalImage = mRouter.getIntermediateResultManager().getOriginalImage(result.getOriginalImageHashId());
    }
});
```

> [!Note]
> Use `originalImage` within the lifecycle of each `onDecodedBarcodesReceived` callback. Otherwise, it may be released or replaced by a newer image.

**Related APIs**

- [`getOriginalImageHashId`]({{ site.dbr_android_api }}decoded-barcodes-result.html)
- [`getIntermediateResultManager`]({{ site.dcvb_android_api }}capture-vision-router/intermediate-result.html#getintermediateresultmanager)
- [`getOriginalImage`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html#getoriginalimage)

## Explore Result Details

This page provides a high-level overview of barcode scan results. For detailed usage and advanced scenarios, see:

- [Get barcode confidence and rotation]({{ site.features }}get-confidence-rotation.html?lang=android)
- [Get barcode location]({{ site.features }}get-barcode-location.html?lang=android)
- [Get detailed barcode information]({{ site.features }}get-detailed-info.html?lang=android)
- [Filter and sort decoding results]({{ site.features }}filter-and-sort.html?lang=android)
