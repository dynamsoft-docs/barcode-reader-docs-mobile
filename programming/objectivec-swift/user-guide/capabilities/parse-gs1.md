---
layout: default-layout
title: Parse GS1 AI - Dynamsoft Barcode Reader iOS
description: Learn how to parse GS1 AI with Dynamsoft Barcode Reader iOS.
keywords: parse, iOS, GS1 AI
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Parse GS1 AI

## How to Enable GS1 AI Parsing

1. Add code parser task.

   ```json
   "CodeParserTaskSettingOptions": [
     {
       "Name": "parse_gs1",
       "CodeSpecifications": [
         "GS1_AI"
       ]
     }
   ]
   ```

2. Add semantic processing options and specify the target ROI to reference.

   ```json
   "SemanticProcessingOptions": [
     {
       "Name": "sp_gs1",
       "ReferenceObjectFilter": {
         "ReferenceTargetROIDefNameArray": [
           "roi_read_gs1"
         ]
       },
       "TaskSettingNameArray": [
         "parse_gs1"
       ]
     }
   ]
   ```

3. Add the semantic processing option names to your template.

   ```json
   "CaptureVisionTemplates": [
     {
       "Name": "ReadGS1AI",
       "ImageROIProcessingNameArray": [
         "roi_read_gs1"
       ],
       "SemanticProcessingNameArray": [
         "sp_gs1"
       ]
     }
   ]
   ```

## How to Receive Parsed Results

When semantic processing is enabled, parsed data is delivered through the same capture-result flow as other outputs. Use the result receiving patterns described in [Receive Results](receive-results.md) and then read the parsed output together with the barcode result returned for the current capture session.

## Common Fields

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value `GS1_AI` |
| 01 | Identification of a trade item (GTIN) |
| 10 | Batch or lot number |
| 11 | Production date |
| 12 | Due date for amount on payment slip |
| 13 | Packaging date |
| 15 | Best before date |
| 16 | Sell by date |
| 17 | Expiration date |
| 20 | Internal product variant |
| 21 | Serial number |
| 22 | Consumer product variant |
| 30 | Variable count of items |
| 310n | Net weight, kilograms |
| 37 | Count of trade items or trade item pieces contained in a logistic unit |
| 390n | Amount payable or coupon value - Single monetary area |
| 391n | Amount payable and ISO currency code |
| 392n | Amount payable for a variable measure trade item - Single monetary area |
| 393n | Amount payable for a variable measure trade item and ISO currency code |
| 394n | Percentage discount of a coupon |
| 395n | Amount payable per unit of measure single monetary area |
| 400 | Customer’s purchase order number |
| 401 | Global Identification Number for Consignment (GINC) |
| 402 | Global Shipment Identification Number (GSIN) |
| 410 | Ship to - Deliver to Global Location Number (GLN) |

View more [GS1 AI fields]({{ site.code_types }}gs1-ai.html).