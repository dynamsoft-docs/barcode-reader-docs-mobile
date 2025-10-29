---
layout: default-layout
title: ParsedField Class - Dynamsoft Capture Vision Flutter Edition
description: The ParsedField class represents the result of a code parsing process. It provides access to the individual parsed items resulting from a document or an encrypted text.
keywords: originalImageHashId, items, errorCode, ParsedField, api reference, barcode result, capture, flutter, code parser
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ParsedField
---

# ParsedField Class

The `ParsedField` class represents a field from the [`ParsedResultItem`](parsed-result-item.md) output of an encrypted text coming from a document or a data source. It contains the parsed value along with its mapping and validation status.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class ParsedField
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`value`](#value) | *String* | The processed value of the parsed field. |
| [`rawValue`](#value) | *String* | The raw string value of the field as obtained from the source data. |
| [`mappingStatus`](#mappingstatus) | [*EnumMappingStatus*](../enum/mapping-status.md) | A status representing whether the field was mapped from the source data or not. |
| [`validationStatus`](#validationstatus) | [*EnumValidationStatus*](../enum/validation-status.md) | The status of a field's value after the internal validation checks. |

### value

The processed value of the parsed field.

```dart
String value;
```

**Remarks**

The processed value usually comes in handy when dealing with country codes. For example, if the passport is from Canada, the processed string value would be "Canada" while the raw string value is "CAN".

### rawValue

The raw string value of the field as obtained from the source data.

```dart
String rawValue;
```

**Remarks**

The processed value usually comes in handy when dealing with country codes. For example, if the passport is from Canada, the processed string value would be "Canada" while the raw string value is "CAN".

### mappingStatus

A status representing whether the field was mapped from the source data or not, represented as a [`EnumMappingStatus`](../enum/mapping-status.md). If the field was unsuccessful during the mapping process, the mappingStatus would be `EnumMappingStatus.failed`.

```dart
EnumMappingStatus mappingStatus;
```

### validationStatus

The status of a field's value after the internal validation checks, represented as a [`EnumValidationStatus`](../enum/validation-status.md). Once a field is parsed by the Code Parser, it is run through validation checks to make sure that the information is accurate and correct. If a field's value does not pass, the validationStatus would be `EnumValidationStatus.failed`.

```dart
String codeType;
```

**Remarks**

An example of a failed validation check is if the month of a birth date is April 31 for instance. Since that is anb invalid day, the date of birth field will be marked as invalid. The validation check does not compare the info of a parsed field against a database or anything of the kind in order to verify if the information is correct.
