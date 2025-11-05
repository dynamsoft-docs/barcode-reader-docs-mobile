---
layout: default-layout
title: EnumMappingStatus - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumMappingStatus of DBR Flutter Edition defines whether the field was mapped from the source data or not
keywords: captured result, flutter, capture vision, mapping, code parser, mapping
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumMappingStatus
---

# EnumMappingStatus

`EnumMappingStatus` is an enumeration that represents whether the associated field was mapped from the source data or not.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumMappingStatus {
    none,
    succeeded,
    failed
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `none` | No mapping has been performed. |
| `succeeded` | Mapping of this field was successful. |
| `failed` | Mapping of this field was unsuccessful. |
