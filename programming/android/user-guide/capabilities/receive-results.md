---
layout: default-layout
title: Receive Results - Dynamsoft Barcode Reader Android
description: Learn how to receive captured results when using Dynamsoft Barcode Reader Android edition.
keywords: Receive Results, Android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Receive Results

## Receive Results from CapturedResultReceiver

If you only need barcode results, use `onDecodedBarcodesReceived`.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
mRouter.addResultReceiver(new CapturedResultReceiver() {
    @Override
    public void onDecodedBarcodesReceived(@NonNull DecodedBarcodesResult result) {
        // Add your code to use the DecodedBarcodesResult
    }
});
```
2. 
```kotlin
cvr.addResultReceiver(object: CapturedResultReceiver{
    override fun onDecodedBarcodesReceived(result: DecodedBarcodesResult) {
        // Add your code to use the DecodedBarcodesResult
    }
})
```

Likewise, in scenarios such as driver license parsing, you can get a `ParsedResult` directly from `onParsedResultsReceived`.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
mRouter.addResultReceiver(new CapturedResultReceiver() {
    @Override
    public void onParsedResultsReceived(@NonNull ParsedResult result) {
        // Add your code to use the ParsedResult
    }
});
```
2. 
```kotlin
cvr.addResultReceiver(object: CapturedResultReceiver{
    override fun onParsedResultsReceived(result: ParsedResult) {
        // Add your code to use the ParsedResult
    }
})
```

If you need multiple result types at the same time, `onCapturedResultReceived` is more convenient.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
mRouter.addResultReceiver(new CapturedResultReceiver() {
    @Override
    public void onCapturedResultReceived(@NonNull CapturedResult result) {
        // You can get both ParsedResult and DecodedBarcodesResult
    }
});
```
2. 
```kotlin
cvr.addResultReceiver(object: CapturedResultReceiver{
    override fun onCapturedResultReceived(result: CapturedResult) {
        // You can get both ParsedResult and DecodedBarcodesResult
        val parsedResult = result.parsedResult
        val decodedBarcodesResult = result.decodedBarcodesResult
    }
})
```

## Receive Results from Capture Methods

The result is returned as a `CapturedResult` object when using `capture` methods. You can get the types you want from the `CapturedResult` object.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
CapturedResult capturedResult = mRouter.capture("Your file path",EnumPresetTemplate.PT_READ_BARCODES_READ_RATE_FIRST);
DecodedBarcodesResult decodedBarcodesResult = capturedResult.getDecodedBarcodesResult();
BarcodeResultItem[] barcodeResultItems = decodedBarcodesResult.getItems();
for(BarcodeResultItem barcodeResultItem: barcodeResultItems)
{
   String barcodeText = barcodeResultItem.getText();
   String barcodeFormatString = barcodeResultItem.getFormatString();
}
```
2. 
```kotlin
val capturedResult = mRouter.capture("Your file path", EnumPresetTemplate.PT_READ_BARCODES_READ_RATE_FIRST)
val decodedBarcodesResult = capturedResult.decodedBarcodesResult
val barcodeResultItems = decodedBarcodesResult.items
for (barcodeResultItem in barcodeResultItems) {
   val barcodeText = barcodeResultItem.text
   val barcodeFormatString = barcodeResultItem.formatString
}
```

## Receive Results from IntermediateResultReceiver

To use `IntermediateResultReceiver`, you need to get the `IntermediateResultManager` from `CaptureVisionRouter` first. Then, you can add result receiver to the `IntermediateResultManager` for receiving intermediate results.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
mRouter.getIntermediateResultManager().addResultReceiver(new IntermediateResultReceiver() {
   @Override
   public void onLocalizedBarcodesReceived(@NonNull LocalizedBarcodesUnit unit, IntermediateResultExtraInfo info) {
          if (unit.getCount() != 0)
          {
             for (LocalizedBarcodeElement element: unit.getLocalizedBarcodes())
             {
                 // LocalizedBarcodeElement is the basic element representing a localized barcode
                 // Add your code to use the LocalizedBarcodeElement
             }
          }
   }
});
```
2. 
```kotlin
cvr.intermediateResultManager.addResultReceiver(object: IntermediateResultReceiver
{
   override fun onLocalizedBarcodesReceived(
          unit: LocalizedBarcodesUnit,
          info: IntermediateResultExtraInfo?
   ) {
          for (element: LocalizedBarcodeElement in unit.localizedBarcodes)
          {
                 // LocalizedBarcodeElement is the basic element representing a localized barcode
                 // Add your code to use the LocalizedBarcodeElement
          }
   }
})
```
