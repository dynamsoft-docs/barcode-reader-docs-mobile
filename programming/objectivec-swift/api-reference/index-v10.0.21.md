---
layout: default-layout
title: Dynamsoft Barcode Reader iOSAPI Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for iOS.
keywords: api reference index
permalink: /programming/objectivec-swift/api-reference/index.html
---

# API Reference - iOS

## Primary Class

- [`DSCaptureVisionRouter`]({{ site.dcv_ios_api }}capture-vision-router/capture-vision-router.html)

## Input

- [`DSDirectoryFetcher`]({{ site.dcv_ios_api }}utility/directory-fetcher.html)
- [`DSFileFetcher`]({{ site.dcv_ios_api }}utility/file-fetcher.html)
- [`DSImageSourceAdapter`]({{ site.dcv_ios_api }}core/basic-structures/image-source-adapter.html)

## Final Results

- [`DSBarcodeResultItem`]({{ site.dbr_ios_api }}barcode-result-item.html)
- [`DSCapturedResultReceiver`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-receiver.html)
- [`DSCapturedResult`]({{ site.dcv_ios_api }}core/basic-structures/captured-result.html)
- [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html)
- [`DSDecodedBarcodesResult`]({{ site.dbr_ios_api }}decoded-barcodes-result.html)
- [`DSOriginalImageResultItem`]({{ site.dcv_ios_api }}core/basic-structures/original-image-result-item.html)

## Final Results Filters

- [`DSCapturedResultFilter`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-filter.html)
- [`DSMultiFrameResultCrossFilter`]({{ site.dcv_ios_api }}utility/multi-frame-result-cross-filter.html)

## Detailed Barcode Results

- [`DSAztecDetails`]({{ site.dbr_ios_api }}auxiliary-iAztecDetails.html)
- [`DSBarcodeDetails`]({{ site.dbr_ios_api }}barcode-details.html)
- [`DSDataMatrixDetails`]({{ site.dbr_ios_api }}auxiliary-iDatamatrixDetails.html)
- [`DSOneDCodeDetails`]({{ site.dbr_ios_api }}auxiliary-iOneDCodeDetails.html)
- [`DSPDF417Details`]({{ site.dbr_ios_api }}auxiliary-iPDF417Details.html)
- [`DSQRCodeDetails`]({{ site.dbr_ios_api }}auxiliary-iQRCodeDetails.html)

## Intermediate Results

- [`DSIntermediateResultManager`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-manager.html)
- [`DSIntermediateResultReceiver`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-receiver.html)
- [`DSObservationParameters`]({{ site.dcv_ios_api }}core/intermediate-results/observation-parameters.html)
- [`IntermediateResultExtraInfo`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-extra-info.html)
- [`DSBinaryImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/binary-image-unit.html)
- [`DSColourImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/colour-image-unit.html)
- [`DSContoursUnit`]({{ site.dcv_ios_api }}core/intermediate-results/contours-unit.html)
- [`DSEnhancedGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
- [`DSGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/grayscale-image-unit.html)
- [`DSIntermediateResult`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result.html)
- [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html)
- [`DSLineSegmentsUnit`]({{ site.dcv_ios_api }}core/intermediate-results/line-segments-unit.html)
- [`DSPredetectedRegionElement`]({{ site.dcv_ios_api }}core/intermediate-results/predetected-region-element.html)
- [`DSPredetectedRegionsUnit`]({{ site.dcv_ios_api }}core/intermediate-results/predetected-regions-unit.html)
- [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html)
- [`DSScaledDownColourImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/scaled-down-colour-image-unit.html)
- [`DSTextRemovedBinaryImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/text-removed-binary-image-unit.html)
- [`DSTextZonesUnit`]({{ site.dcv_ios_api }}core/intermediate-results/text-zones-unit.html)
- [`DSTextureDetectionResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/texture-detection-result-unit.html)
- [`DSTextureRemovedBinaryImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
- [`DSTextureRemovedGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
- [`DSTransformedGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/transformed-grayscale-image-unit.html)
- [`DSScaledUpBarcodeImageUnit`]({{ site.dbr_ios_api }}scaled-up-barcode-image-unit.html)
- [`DSCandidateBarcodeZonesUnit`]({{ site.dbr_ios_api }}candidate-barcode-zones-unit.html)
- [`DSComplementedBarcodeImageUnit`]({{ site.dbr_ios_api }}complemented-barcode-image-unit.html)
- [`DSDeformationResistedBarcodeImageUnit`]({{ site.dbr_ios_api }}deformation-resisted-barcode-image-unit.html)
- [`DSLocalizedBarcodesUnit`]({{ site.dbr_ios_api }}localized-barcodes-unit.html)
- [`DSLocalizedBarcodeElement`]({{ site.dbr_ios_api }}localized-barcode-element.html)
- [`DSDecodedBarcodesUnit`]({{ site.dbr_ios_api }}decoded-barcodes-unit.html)
- [`DSDecodedBarcodeElement`]({{ site.dbr_ios_api }}decoded-barcode-element.html)
- [`DSExtendedBarcodeResult`]({{ site.dbr_ios_api }}auxiliary-iExtendedResult.html)

## Settings

- [`DSSimplifiedCaptureVisionSettings`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)
- [`DSSimplifiedBarcodeReaderSettings`]({{ site.dbr_ios_api }}simplified-barcode-reader-settings.html)

## State Listener

- [`DSCaptureStateListener`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/capture-state-listener.html)
- [`DSImageSourceStateListener`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/image-source-state-listener.html)

## License

- [`DSLicenseManager`]({{ site.dcv_ios_api }}license/license-manager.html)

## Basic Structure

- [`DSContour`]({{ site.dcv_ios_api }}core/basic-structures/contour.html)
- [`DSCorner`]({{ site.dcv_ios_api }}core/basic-structures/corner.html)
- [`DSEdge`]({{ site.dcv_ios_api }}core/basic-structures/edge.html)
- [`DSFileImageTag`]({{ site.dcv_ios_api }}core/basic-structures/file-image-tag.html)
- [`DSImageData`]({{ site.dcv_ios_api }}core/basic-structures/image-data.html)
- [`DSImageTag`]({{ site.dcv_ios_api }}core/basic-structures/image-tag.html)
- [`DSLineSegment`]({{ site.dcv_ios_api }}core/basic-structures/line-segment.html)
- [`DSQuadrilateral`]({{ site.dcv_ios_api }}core/basic-structures/quadrilateral.html)
- [`DSRect`]({{ site.dcv_ios_api }}core/basic-structures/rect.html)
- [`DSVideoFrameTag`]({{ site.dcv_ios_api }}core/basic-structures/video-frame-tag.html)

## Enumerations

- [`BarcodeFormat`]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?lang=objc,swift)
- [`BufferOverflowProtectionMode`]({{ site.dcv_enumerations }}core/buffer-overflow-protection-mode.html?lang=objc,swift)
- [`CapturedResultItemType`]({{ site.dcv_enumerations }}core/captured-result-item-type.html?lang=objc,swift)
- [`CaptureState`]({{ site.dcv_enumerations }}capture-vision-router/capture-state.html?lang=objc,swift)
- [`CornerType`]({{ site.dcv_enumerations }}core/corner-type.html?lang=objc,swift)
- [`DeblurMode`]({{ site.dcv_enumerations }}barcode-reader/deblur-mode.html?lang=objc,swift)
- [`ErrorCode`]({{ site.dcv_enumerations }}core/error-code.html?lang=objc,swift)
- [`ExtendedBarcodeResultType`]({{ site.dcv_enumerations }}barcode-reader/extended-barcode-result-type.html?lang=objc,swift)
- [`GrayscaleEnhancementMode`]({{ site.dcv_enumerations }}core/grayscale-enhancement-mode.html?lang=objc,swift)
- [`GrayscaleTransformationMode`]({{ site.dcv_enumerations }}core/grayscale-transformation-mode.html?lang=objc,swift)
- [`ImageCaptureDistanceMode`]({{ site.dcv_enumerations }}core/image-capture-distance-mode.html?lang=objc,swift)
- [`ImagePixelFormat`]({{ site.dcv_enumerations }}core/image-pixel-format.html?lang=objc,swift)
- [`ImageSourceState`]({{ site.dcv_enumerations }}core/image-source-state.html?lang=objc,swift)
- [`ImageTagType`]({{ site.dcv_enumerations }}core/image-tag-type.html?lang=objc,swift)
- [`IntermediateResultUnitType`]({{ site.dcv_enumerations }}core/intermediate-result-unit-type.html?lang=objc,swift)
- [`LocalizationMode`]({{ site.dcv_enumerations }}barcode-reader/localization-mode.html?lang=objc,swift)
- [`PresetTemplate`]({{ site.dcv_enumerations }}capture-vision-router/preset-template.html?lang=objc,swift)
- [`QRCodeErrorCorrectionLevel`]({{ site.dcv_enumerations }}barcode-reader/qr-code-error-correction-level.html?lang=objc,swift)
- [`RasterDataSource`]({{ site.dcv_enumerations }}core/raster-data-source.html?lang=objc,swift)
- [`RegionObjectElementType`]({{ site.dcv_enumerations }}core/region-object-element-type.html?lang=objc,swift)
- [`SectionType`]({{ site.dcv_enumerations }}core/section-type.html?lang=objc,swift)
- [`TransformMatrixType`]({{ site.dcv_enumerations }}core/transform-matrix-type.html?lang=objc,swift)
- [`VideoFrameQuality`]({{ site.dcv_enumerations }}core/video-frame-quality.html?lang=objc,swift)
