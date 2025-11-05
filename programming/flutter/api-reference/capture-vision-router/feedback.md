---
layout: default-layout
title: FeedBack Class - Dynamsoft Capture Vision Flutter
description: FeedBack class of DCV Flutter provides API to control the haptic feedback features of a phone.
keywords: haptic, feedback, barcode reader, flutter, capture vision
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# FeedBack

The `FeedBack` class allows you to control the haptic feedback features so that the phone can either beep or vibrate when a result is found.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class FeedBack
```

## Methods

### beep

Plays a beep sound when a captured result is found.

```dart
Future<void> beep()
```

### vibrate

Triggers a vibration when a captured result is found.

```dart
Future<void> vibrate()
```

## Code Snippet

```dart
late final CapturedResultReceiver _receiver = CapturedResultReceiver()
    ..onDecodedBarcodesReceived = (DecodedBarcodesResult result) async {
      if (result.items?.isNotEmpty ?? false) {
        FeedBack.beep();
        FeedBack.vibrate();
        _cvr.stopCapturing();
        var displayString = result.items?.map((item) => "Format: ${item.formatString}\nText: ${item.text}").join('\n\n');
        showTextDialog("Barcodes Count: ${result.items?.length ?? 0}", displayString ?? "", () {
          _cvr.startCapturing(_templateName);
        });
      }
    };
```