---
layout: default-layout
title: Capabilities - Dynamsoft Barcode Reader iOS
description: Index of Dynamsoft Barcode Reader iOS capabilities.
keywords: capabilities, feature index, iOS, objective-c, swift
breadcrumbText: Capabilities
noTitleIndex: false
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Capabilities

Find the feature you need quickly by keyword.

<style>
  .capabilities-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 12px;
    margin: 12px 0 24px;
  }

  .capability-link-card {
    display: block;
    background: #f8fafc;
    border: 1px solid #dbe4ee;
    border-radius: 10px;
    padding: 8px 10px;
    box-shadow: 0 1px 2px rgba(15, 23, 42, 0.05);
    color: #0f172a;
    text-decoration: none;
    line-height: 1.35;
    min-height: 40px;
  }

  .capability-link-card:hover {
    background: #ffffff;
    border-color: #bfdbfe;
    box-shadow: 0 4px 10px rgba(15, 23, 42, 0.08);
  }

  @media (max-width: 900px) {
    .capabilities-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

## Input

<div class="capabilities-grid">
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/read-from-camera.html">Read from Camera</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/read-from-an-image.html">Read from Image</a>
</div>

## Working with Results

<div class="capabilities-grid">
  <a class="capability-link-card" href="{{ site.features }}filter-and-sort.html?lang=objc,swift">Parameter Based Result Filter</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/get-original-image.html">Get Original Image</a>
  <a class="capability-link-card" href="{{ site.features }}get-detailed-info.html?lang=objc,swift">Get Detailed Barcode Information</a>
  <a class="capability-link-card" href="{{ site.features }}get-confidence-rotation.html?lang=objc,swift">Get Barcode Confidence and Rotation</a>
  <a class="capability-link-card" href="{{ site.features }}get-barcode-location.html?lang=objc,swift">Get Barcode Location</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/multi-frame-cross-filter.html">Multi-Frame Cross Filter</a>
</div>

## Control the Scanning Process

<div class="capabilities-grid">
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/barcode-formats.html">Configure Barcode Format</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/init-customized-template.html">Initialize Customized Template</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/config-simplified-settings.html">Configure Simplified Settings</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/read-specific-area.html">Read a specific area/region</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/single-multiple.html">Switch Single & Multiple</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/zoom-control.html">Zoom Control</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/feedback.html">Beep & Vibrate</a>
</div>

## Decode Challenging Barcodes

<div class="capabilities-grid">
  <a class="capability-link-card" href="{{ site.features }}read-inverted-barcodes.html?lang=objc,swift">Read inverted barcodes</a>
  <a class="capability-link-card" href="{{ site.features }}read-deformed-barcodes.html?lang=objc,swift">Read deformed barcodes</a>
  <a class="capability-link-card" href="{{ site.features }}read-incomplete-barcodes.html?lang=objc,swift">Read incomplete barcodes</a>
  <a class="capability-link-card" href="{{ site.features }}read-a-large-image.html?lang=objc,swift">Read barcodes from a large image</a>
  <a class="capability-link-card" href="{{ site.features }}read-barcodes-with-small-module-size.html?lang=objc,swift">Read barcodes with small module size</a>
  <a class="capability-link-card" href="{{ site.features }}read-barcodes-with-imbalanced-colour.html?lang=objc,swift">Read images with imbalanced colors</a>
  <a class="capability-link-card" href="{{ site.features }}read-barcodes-with-uneven-lighting.html?lang=objc,swift">Read images with uneven lighting</a>
  <a class="capability-link-card" href="{{ site.features }}read-images-with-texture.html?lang=objc,swift">Read images with texture</a>
  <a class="capability-link-card" href="{{ site.features }}read-images-with-lots-of-text.html?lang=objc,swift">Read images with lots of text</a>
  <a class="capability-link-card" href="{{ site.features }}read-dense-barcodes.html?lang=objc,swift">Read high-density QR Codes</a>
  <a class="capability-link-card" href="{{ site.usecases }}read-dpm-codes.html?lang=objc,swift">Read DPM Codes</a>
  <a class="capability-link-card" href="{{ site.usecases }}read-postal-codes.html?lang=objc,swift">Read Postal Codes</a>
  <a class="capability-link-card" href="{{ site.features }}preprocess-images.html?lang=objc,swift">Preprocess images to read difficult barcodes</a>
  <a class="capability-link-card" href="{{ site.features }}use-region-predetection.html?lang=objc,swift">Pre-detect Region of Interest (ROI)</a>
  <a class="capability-link-card" href="{{ site.features }}use-format-specific-configuration.html?lang=objc,swift">Use format specific configurations</a>
</div>

## Customize the UI

<div class="capabilities-grid">
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/add-functional-buttons.html">Add Functional Buttons</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/add-graphics.html">Add Graphics with DrawingItems</a>
  <a class="capability-link-card" href="{{ site.oc }}user-guide/capabilities/scan-region-style.html">Scan Region Style</a>
</div>
