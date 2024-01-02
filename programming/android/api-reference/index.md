---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for Android Language.
keywords: CBarcodeReader, api reference, Android
permalink: /programming/android/api-reference/index.html
---

# API Reference - Android

## Primary Class

- [`CaptureVisionRouter`]({{ site.dcv_android_api }}capture-vision-router/capture-vision-router.html)

## Input

- [`DirectoryFetcher`]({{ site.dcv_android_api }}utility/directory-fetcher.html)
- [`FileFetcher`]({{ site.dcv_android_api }}utility/file-fetcher.html)
- [`ImageSourceAdapter`]({{ site.dcv_android_api }}core/basic-structures/image-source-adapter.html)

## Final Results

- [`BarcodeResultItem`]({{ site.dbr_android_api }}barcode-result-item.html)
- [`CapturedResultReceiver`]({{ site.dcv_android_api }}core/basic-structures/captured-result-receiver.html)
- [`CapturedResult`]({{ site.dcv_android_api }}core/basic-structures/captured-result.html)
- [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html)
- [`DecodedBarcodesResult`]({{ site.dbr_android_api }}decoded-barcodes-result.html)
- [`OriginalImageResultItem`]({{ site.dcv_android_api }}core/basic-structures/original-image-result-item.html)

## Final Results Filters

- [`CapturedResultFilter`]({{ site.dcv_android_api }}core/basic-structures/captured-result-filter.html)
- [`MultiFrameResultCrossFilter`]({{ site.dcv_android_api }}utility/multi-frame-result-cross-filter.html)

## Detailed Barcode Results

- [`AztecDetails`]({{ site.dbr_android_api }}auxiliary-AztecDetails.html)
- [`BarcodeDetails`]({{ site.dbr_android_api }}barcode-details.html)
- [`DataMatrixDetails`]({{ site.dbr_android_api }}auxiliary-DataMatrixDetails.html)
- [`OneDCodeDetails`]({{ site.dbr_android_api }}auxiliary-OneDCodeDetails.html)
- [`PDF417Details`]({{ site.dbr_android_api }}auxiliary-PDF417Details.html)
- [`QRCodeDetails`]({{ site.dbr_android_api }}auxiliary-QRCodeDetails.html)

## Intermediate Results

- [`IntermediateResultManager`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-manager.html)
- [`IntermediateResultReceiver`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-receiver.html)
- [`ObservationParameters`]({{ site.dcv_android_api }}core/intermediate-results/observation-parameters.html)
- [`IntermediateResultExtraInfo`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-extra-info.html)
- [`BinaryImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/binary-image-unit.html)
- [`ColourImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/colour-image-unit.html)
- [`ContoursUnit`]({{ site.dcv_android_api }}core/intermediate-results/contours-unit.html)
- [`EnhancedGrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
- [`GrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/grayscale-image-unit.html)
- [`IntermediateResult`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result.html)
- [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html)
- [`LineSegmentsUnit`]({{ site.dcv_android_api }}core/intermediate-results/line-segments-unit.html)
- [`PredetectedRegionElement`]({{ site.dcv_android_api }}core/intermediate-results/predetected-region-element.html)
- [`PredetectedRegionsUnit`]({{ site.dcv_android_api }}core/intermediate-results/predetected-regions-unit.html)
- [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html)
- [`ScaledDownColourImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/scaled-down-colour-image-unit.html)
- [`TextRemovedBinaryImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/text-removed-binary-image-unit.html)
- [`TextZonesUnit`]({{ site.dcv_android_api }}core/intermediate-results/text-zones-unit.html)
- [`TextureDetectionResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/texture-detection-result-unit.html)
- [`TextureRemovedBinaryImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
- [`TextureRemovedGrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
- [`TransformedGrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/transformed-grayscale-image-unit.html)
- [`ScaledUpBarcodeImageUnit`]({{ site.dbr_android_api }}scaled-up-barcode-image-unit.html)
- [`CandidateBarcodeZonesUnit`]({{ site.dbr_android_api }}candidate-barcode-zones-unit.html)
- [`ComplementedBarcodeImageUnit`]({{ site.dbr_android_api }}complemented-barcode-image-unit.html)
- [`DeformationResistedBarcodeImageUnit`]({{ site.dbr_android_api }}deformation-resisted-barcode-image-unit.html)
- [`LocalizedBarcodesUnit`]({{ site.dbr_android_api }}localized-barcodes-unit.html)
- [`LocalizedBarcodeElement`]({{ site.dbr_android_api }}localized-barcode-element.html)
- [`DecodedBarcodesUnit`]({{ site.dbr_android_api }}decoded-barcodes-unit.html)
- [`DecodedBarcodeElement`]({{ site.dbr_android_api }}decoded-barcode-element.html)
- [`ExtendedBarcodeResult`]({{ site.dbr_android_api }}auxiliary-ExtendedResult.html)

## Settings

- [`SimplifiedCaptureVisionSettings`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)
- [`SimplifiedBarcodeReaderSettings`]({{ site.dbr_android_api }}simplified-barcode-reader-settings.html)

## State Listener

- [`CaptureStateListener`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/capture-state-listener.html)
- [`ImageSourceStateListener`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/image-source-state-listener.html)

## License

- [`LicenseManager`]({{ site.dcv_android_api }}license/license-manager.html)

## Basic Structure

- [`Contour`]({{ site.dcv_android_api }}core/basic-structures/contour.html)
- [`Corner`]({{ site.dcv_android_api }}core/basic-structures/corner.html)
- [`Edge`]({{ site.dcv_android_api }}core/basic-structures/edge.html)
- [`FileImageTag`]({{ site.dcv_android_api }}core/basic-structures/file-image-tag.html)
- [`ImageData`]({{ site.dcv_android_api }}core/basic-structures/image-data.html)
- [`ImageTag`]({{ site.dcv_android_api }}core/basic-structures/image-tag.html)
- [`LineSegment`]({{ site.dcv_android_api }}core/basic-structures/line-segment.html)
- [`Quadrilateral`]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html)
- [`Rect`]({{ site.dcv_android_api }}core/basic-structures/rect.html)
- [`VideoFrameTag`]({{ site.dcv_android_api }}core/basic-structures/video-frame-tag.html)

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
- [`PresetTemplate`]({{ site.dcv_enumerations }}capture-vision-router/preset-template.html?lang=android)
- [`QRCodeErrorCorrectionLevel`]({{ site.dcv_enumerations }}barcode-reader/qr-code-error-correction-level.html?lang=android)
- [`RasterDataSource`]({{ site.dcv_enumerations }}core/raster-data-source.html?lang=android)
- [`RegionObjectElementType`]({{ site.dcv_enumerations }}core/region-object-element-type.html?lang=android)
- [`SectionType`]({{ site.dcv_enumerations }}core/section-type.html?lang=android)
- [`TransformMatrixType`]({{ site.dcv_enumerations }}core/transform-matrix-type.html?lang=android)
- [`VideoFrameQuality`]({{ site.dcv_enumerations }}core/video-frame-quality.html?lang=android)
