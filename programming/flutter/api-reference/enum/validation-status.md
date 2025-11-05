---
layout: default-layout
title: EnumValidationStatus - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumValidationStatus of DBR Flutter Edition defines the status of a field's value after the internal validation checks
keywords: captured result, flutter, capture vision, mapping, code parser, validation
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumValidationStatus
---

# EnumValidationStatus

`EnumValidationStatus` is an enumeration that represents whether the associated field's value passed the internal validation checks.

> [!NOTE]
> An example of a failed validation check is if the month of a birth date is April 31 for instance. Since that is anb invalid day, the date of birth field will be marked as invalid. The validation check does not compare the info of a parsed field against a database or anything of the kind in order to verify if the information is correct.


## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumValidationStatus {
    none,
    succeeded,
    failed
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `none` | No validation check has been performed. |
| `succeeded` | The validation of this field was successful. |
| `failed` | The validation of this field was unsuccessful. |
