---
layout: default-layout
title: ParsedResultItem Class - Dynamsoft Capture Vision Flutter Edition
description: The ParsedResult class represents the result of a code parsing process. It provides access to the individual parsed items resulting from a document or an encrypted text.
keywords: originalImageHashId, items, errorCode, ParsedResultItem, api reference, barcode result, capture, flutter, code parser
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ParsedResultItem
---

# ParsedResultItem Class

The `ParsedResultItem` class represents the most basic unit of a parsed result. It includes specific details relevant to the parsed data, including the code type, the raw JSON string, and a map of the individual parsed fields.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class ParsedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`parsedFields`](#parsedfields) | *Map\<String, ParsedField\>* | A map of parsed fields extracted from the parsed result. |
| [`jsonString`](#jsonstring) | *String* | The raw JSON string representation of the parsed result. |
| [`codeType`](#codetype) | *String* | The type of the encrypted code associated to the attached parsed result. |

### parsedFields

A map of the parsed fields extracted from the parsed result. Each field can then be accessed by the associated key, allowing the developer to present the parsed info in a user-friendly manner.

```dart
Map<String, ParsedField> parsedFields;
```

### jsonString

The text of the parsed result as a JSON string.

```dart
String jsonString;
```

### codeType

The type of the encrypted code associated to the attached parsed result. The code can be a MRZ document (passport, visa, etc.), a driver license (North America or South Africa), or an Aadhar card. 

```dart
String codeType;
```
