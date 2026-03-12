---
layout: default-layout
title: Deep Learning Models - Dynamsoft Barcode Reader iOS
description: Learn how deep learning models improve barcode localization and decoding in Dynamsoft Barcode Reader iOS.
keywords: models, deep learning, iOS, objective-c, swift
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Deep Learning Models in Barcode Scanning

Deep learning models are used by the SDK to improve barcode detection and decoding robustness, especially in challenging conditions such as blur, low contrast, distortion, glare, and complex backgrounds.

In most cases, these models are loaded and used automatically. You usually only need to understand their role and package impact, then decide whether to keep or remove specific model files based on your barcode scope.

## Where Models Are Used in the Pipeline

In a simplified view, barcode processing can be divided into two major stages:

1. Localization stage
     - Find potential barcode regions in the image.
2. Decoding stage
     - Decode the detected regions into barcode text and format.

Different model groups optimize different stages.

## Available Models

### Localization Models

Localization models mainly affect the region detection stage.

Benefits:

1. Improve barcode localization success rate.
2. Filter out false-positive regions before decoding.
3. Reduce wasted decode attempts on invalid regions.

- DataMatrixQRCodeLocalization.data
- OneDLocalization.data
- PDF417Localization.data

Typical use case:

- Images where barcodes are small, partially occluded, or surrounded by heavy background textures.

### Decoders

Decoder models mainly affect the decode stage for specific symbologies.

Benefits:

1. Improve decode success rate on difficult samples.
2. Improve decode efficiency when symbols are damaged or low quality.
3. Provide stronger format-specific decoding capability.

- Code128Decoder.data
- Code39ITFDecoder.data
- EAN13Decoder.data

Typical use case:

- Retail, logistics, and warehouse scenarios where 1D barcodes may be compressed, printed with noise, or captured at non-ideal angles.

### Deblur Models

Deblur models are used before or during decoding to recover details from blurred barcode regions.

Benefits:

1. Improve success rate for motion blur and out-of-focus images.
2. Especially useful for image-based decoding workflows.

Trade-off:

- Usually slower than non-deblur paths, so they are more suitable when read-rate is prioritized over speed.

- OneDDeblur.data
- PDF417Deblur.data
- DataMatrixQRCodeDeblur.data

Typical use case:

- Document scan, album/image import, and any workflow where users decode still images with unstable quality.

## Model Selection Recommendations

If your app has a clear barcode scope, you can keep only the related models.

- QR Code + DataMatrix only:
    - Keep `DataMatrixQRCodeLocalization.data` and `DataMatrixQRCodeDeblur.data`.
    - Consider removing OneD/PDF417-related models.
- 1D-focused business workflows:
    - Keep `OneDLocalization.data`, `Code128Decoder.data`, `Code39ITFDecoder.data`, `EAN13Decoder.data`, and `OneDDeblur.data`.
- PDF417-heavy workflows (e.g. IDs and transport docs):
    - Keep `PDF417Localization.data` and `PDF417Deblur.data`.

If you are unsure, keep all default models first, then trim by test results.

## Package Details and How to Shrink APP Size

Model files are packaged in `DynamsoftBarcodeReaderBundle.aar`. Please [contact us](https://www.dynamsoft.com/company/customer-service/#contact){:target="_blank"} if you want to shrink app size.

## Best Practices

1. Start with all default models enabled.
2. Confirm your target barcode formats and real-world scan scenarios.
3. Remove unrelated models gradually.
4. Validate both speed and read rate after each shrink step.
5. Keep a fallback build profile with all models for troubleshooting.

## Next Steps

- [Barcode Formats](barcode-format.md)
- [Parameters, Settings & Templates](parameters-and-templates.md)
- [Understand Scan Results](understand-barcode-scan-results.md)
