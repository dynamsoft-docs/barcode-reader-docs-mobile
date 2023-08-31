---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for Android Language.
keywords: CBarcodeReader, api reference, Android
permalink: /programming/android/api-reference/index.html
---

# API Reference - Android

## Primary Class

- [`DSCaptureVisionRouter`]({{ site.dcv_android_api }}capture-vision-router/capture-vision-router.html)

## Input

- [`DSDirectoryFetcher`]({{ site.dcv_android_api }}utility/directory-fetcher.html)
- [`DSFileFetcher`]({{ site.dcv_android_api }}utility/file-fetcher.html)
- [`DSImageSourceAdapter`]({{ site.dcv_android_api }}core/basic-structures/image-source-adapter.html)
- [`DSProactiveImageSourceAdapter`]({{ site.dcv_android_api }}utility/proactive-image-source-adapter.html)

## Final Results

- [`DSBarcodeResultItem`]({{ site.dbr_android_api }}barcode-result-item.html)
- [`DSCapturedResultReceiver`]({{ site.dcv_android_api }}core/basic-structures/captured-result-receiver.html)
- [`DSCapturedResult`]({{ site.dcv_android_api }}core/basic-structures/captured-result.html)
- [`DSCapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html)
- [`DSDecodedBarcodesResult`]({{ site.dbr_android_api }}decoded-barcodes-result.html)
- [`DSOriginalImageResultItem`]({{ site.dcv_android_api }}core/basic-structures/original-image-result-item.html)

## Final Results Filters

- [`DSCapturedResultFilter`]({{ site.dcv_android_api }}core/basic-structures/captured-result-filter.html)
- [`DSMultiFrameResultCrossFilter`]({{ site.dcv_android_api }}utility/multi-frame-result-cross-filter.html)

## Detailed Barcode Results

- [`DSAztecDetails`]({{ site.dbr_android_api }}aztec-details.html)
- [`DSBarcodeDetails`]({{ site.dbr_android_api }}barcode-details.html)
- [`DSDataMatrixDetails`]({{ site.dbr_android_api }}datamatrix-details.html)
- [`DSOneDCodeDetails`]({{ site.dbr_android_api }}oned-code-details.html)
- [`DSPDF417Details`]({{ site.dbr_android_api }}pdf417-details.html)
- [`DSQRCodeDetails`]({{ site.dbr_android_api }}qr-code-details.html)

## Intermediate Results

- [`DSIntermediateResultManager`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-manager.html)
- [`DSIntermediateResultReceiver`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-receiver.html)
- [`DSObservationParameters`]({{ site.dcv_android_api }}core/intermediate-results/observed-parameters.html)
- [`IntermediateResultExtraInfo`]({{ site.dcv_android_api }}core/structs/intermediate-result-extra-info.html)
- [`DSBinaryImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/binary-image-unit.html)
- [`DSColourImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/colour-image-unit.html)
- [`DSContoursUnit`]({{ site.dcv_android_api }}core/intermediate-results/contours-unit.html)
- [`DSEnhancedGrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
- [`DSGrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/grayscale-image-unit.html)
- [`DSIntermediateResult`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result.html)
- [`DSIntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html)
- [`DSLineSegmentsUnit`]({{ site.dcv_android_api }}core/intermediate-results/line-segments-unit.html)
- [`DSPredetectedRegionElement`]({{ site.dcv_android_api }}core/intermediate-results/predetected-region-element.html)
- [`DSPredetectedRegionsUnit`]({{ site.dcv_android_api }}core/intermediate-results/predetected-regions-unit.html)
- [`DSRegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html)
- [`DSScaledDownColourImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/scaled-down-colour-image-unit.html)
- [`DSTextRemovedBinaryImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/text-removed-binary-image-unit.html)
- [`DSTextZonesUnit`]({{ site.dcv_android_api }}core/intermediate-results/text-zones-unit.html)
- [`DSTextureDetectionResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/texture-detection-result-unit.html)
- [`DSTextureRemovedBinaryImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
- [`DSTextureRemovedGrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
- [`DSTransformedGrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/transformed-grayscale-image-unit.html)
- [`DSScaledUpBarcodeImageUnit`]({{ site.dbr_android_api }}scaled-up-barcode-image-unit.html)
- [`DSCandidateBarcodeZonesUnit`]({{ site.dbr_android_api }}candidate-barcode-zones-unit.html)
- [`DSComplementedBarcodeImageUnit`]({{ site.dbr_android_api }}complemented-barcode-image-unit.html)
- [`DSDeformationResistedBarcodeImageUnit`]({{ site.dbr_android_api }}deformation-resisted-barcode-image-unit.html)
- [`DSLocalizedBarcodesUnit`]({{ site.dbr_android_api }}localized-barcodes-unit.html)
- [`DSLocalizedBarcodeElement`]({{ site.dbr_android_api }}localized-barcode-element.html)
- [`DSDecodedBarcodesUnit`]({{ site.dbr_android_api }}decoded-barcodes-unit.html)
- [`DSDecodedBarcodeElement`]({{ site.dbr_android_api }}decoded-barcode-element.html)
- [`DSExtendedBarcodeResult`]({{ site.dbr_android_api }}extended-barcode-result.html)

## Settings

- [`DSSimplifiedCaptureVisionSettings`]({{ site.dcv_android_api }}capture-vision-router/structs/simplified-capture-vision-settings.html)
- [`DSSimplifiedBarcodeReaderSettings`]({{ site.dbr_android_api }}simplified-barcode-reader-settings.html)
- [`DSPresetTemplate`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/preset-template.html)

## State Listener

- [`DSCaptureStateListener`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/capture-state-listener.html)
- [`DSImageSourceStateListener`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/image-source-state-listener.html)

## License

- [`DSLicenseManager`]({{ site.dcv_android_api }}license/license-manager.html)

## Basic Structure

- [`DSContour`]({{ site.dcv_android_api }}core/basic-structures/contour.html)
- [`DSCorner`]({{ site.dcv_android_api }}core/basic-structures/corner.html)
- [`DSEdge`]({{ site.dcv_android_api }}core/basic-structures/edge.html)
- [`DSFileImageTag`]({{ site.dcv_android_api }}core/basic-structures/file-image-tag.html)
- [`DSImageData`]({{ site.dcv_android_api }}core/basic-structures/image-data.html)
- [`DSImageTag`]({{ site.dcv_android_api }}core/basic-structures/image-tag.html)
- [`DSLineSegment`]({{ site.dcv_android_api }}core/basic-structures/line-segment.html)
- [`DSPDFReadingParameter`]({{ site.dcv_android_api }}core/basic-structures/pdf-reading-parameter.html)
- [`DSPoint`]({{ site.dcv_android_api }}core/basic-structures/point.html)
- [`DSQuadrilateral`]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html)
- [`DSRect`]({{ site.dcv_android_api }}core/basic-structures/rect.html)
- [`DSVideoFrameTag`]({{ site.dcv_android_api }}core/basic-structures/video-frame-tag.html)

## Enumerations

- [`BarcodeFormat`]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?lang=android)
- [`BufferOverflowProtectionMode`]({{ site.dcv_enumerations }}core/buffer-overflow-protection-mode.html?lang=android)
- [`CapturedResultItemType`]({{ site.dcv_enumerations }}core/captured-result-item-type.html?lang=android)
- [`CaptureState`]({{ site.dcv_enumerations }}capture-vision-router/capture-state.html?lang=android)
- [`CornerType`]({{ site.dcv_enumerations }}core/corner-type.html?lang=android)
- [`DeblurMode`]({{ site.dcv_enumerations }}barcode-reader/deblur-mode.html?lang=android)
- [`ErrorCode`]({{ site.dcv_enumerations }}core/error-code.html?lang=android)
- [`ExtendedBarcodeResultType`]({{ site.dcv_enumerations }}barcode-reader/extended-barcode-result-type.html?lang=android)
- [`GrayscaleEnhancementMode`]({{ site.dcv_enumerations }}core/grayscale-enhancement-mode.html?lang=android)
- [`GrayscaleTransformationMode`]({{ site.dcv_enumerations }}core/grayscale-transformation-mode.html?lang=android)
- [`ImageCaptureDistanceMode`]({{ site.dcv_enumerations }}core/image-capture-distance-mode.html?lang=android)
- [`ImagePixelFormat`]({{ site.dcv_enumerations }}core/image-pixel-format.html?lang=android)
- [`ImageSourceState`]({{ site.dcv_enumerations }}core/image-source-state.html?lang=android)
- [`ImageTagType`]({{ site.dcv_enumerations }}core/image-tag-type.html?lang=android)
- [`IntermediateResultUnitType`]({{ site.dcv_enumerations }}core/intermediate-result-unit-type.html?lang=android)
- [`LocalizationMode`]({{ site.dcv_enumerations }}barcode-reader/localization-mode.html?lang=android)
- [`PDFReadingMode`]({{ site.dcv_enumerations }}core/pdf-reading-mode.html?lang=android)
- [`QRCodeErrorCorrectionLevel`]({{ site.dcv_enumerations }}barcode-reader/qr-code-error-correction-level.html?lang=android)
- [`RasterDataSource`]({{ site.dcv_enumerations }}core/raster-data-source.html?lang=android)
- [`RegionObjectElementType`]({{ site.dcv_enumerations }}core/region-object-element-type.html?lang=android)
- [`SectionType`]({{ site.dcv_enumerations }}core/section-type.html?lang=android)
- [`TransformMatrixType`]({{ site.dcv_enumerations }}core/transform-matrix-type.html?lang=android)
- [`VideoFrameQuality`]({{ site.dcv_enumerations }}core/video-frame-quality.html?lang=android)
