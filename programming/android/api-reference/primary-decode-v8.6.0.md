---
layout: default-layout
title: BarcodeReader Decode Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader Decode methods of Dynamsoft Barcode Reader for Android SDK.
keywords: decodeFile, decodeFileInMemory, decodeBuffer, decodeBase64String, decodeBufferedImage, decode methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/android/api-reference/primary-decode-v8.6.0.html
---


# Decode Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeFile`](#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`decodeBuffer`](#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeBase64String`](#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](#decodebufferedimage) | Decodes barcode from a buffered imag (bitmap). |
  
  ---

## decodeFile

Decode barcodes from a specified image file.

```java
TextResult[] decodeFile(String fileFullPath, String templateName) throws BarcodeReaderException
```

**Parameters**

`fileFullPath`: A string defining the file path.  
`templateName`: The template name.

**Return Value**

All barcode text results decoded successfully.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
TextResult[] result = reader.decodeFile("your file path", "");
```

## decodeFileInMemory

Decode barcodes from an image file in memory.

### fileBytes

```java
TextResult[] decodeFileInMemory(byte[] fileBytes, String templateName) throws BarcodeReaderException
```

**Parameters**

`fileBytes`: The image file bytes in memory.  
`templateName`: The template name.

**Return Value**

All barcode text results decoded successfully.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding
get bufferBytes from other component*/
TextResult[] result = reader.decodeFileInMemory(bufferBytes, "");
```

### fileStream

```java
TextResult [] decodeFileInMemory(InputStream fileStream, String templateName) throws BarcodeReaderException, IOException
```

**Parameters**

`fileStream`: The image file bytes in memory.  
`templateName`: The template name.

**Return Value**

All barcode text results decoded successfully.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html), IOException

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding
get bufferBytes from other component*/
TextResult[] result = reader.decodeFileInMemory(fis, "");
```

## decodeBuffer

Decode barcodes from the memory buffer containing image pixels in defined format.

```java
TextResult[] decodeBuffer(byte[] buffer, int width, int height, int stride, int enumImagePixelFormat, String templateName) throws BarcodeReaderException
```

**Parameters**

`buffer`: The array of bytes which contain the image data.  
`Width`: The width of the image in pixels.  
`Height`: The height of the image in pixels.  
`Stride`: The stride (or scan width) of the image.  
`format`: The image pixel format used in the image byte array.  
`templateName`: The template name.

**Return Value**

All barcode text results decoded successfully.  

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
byte[] bufferBytes;
int iWidth = 0;
int iHeight = 0;
int iStride = 0;
int format;
GetBufferFromFile("your file path", bufferBytes, iWidth, iHeight, iStride, format);
TextResult[] result = reader.decodeBuffer(bufferBytes, iWidth,  iHeight, iStride, format, "");
```

## decodeBase64String

Decode barcode from an image file encoded as a base64 string.

```java
TextResult[] decodeBase64String(String base64, String templateName) throws BarcodeReaderException
```

**Parameters**

`base64`: A base64 encoded string that represents an image.  
`templateName`: The template name.

**Return Value**

All barcode text results decoded successfully.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
TextResult[] result = reader.decodeBase64String("file in base64 string", "");
```

## decodeBufferedImage

Decodes barcode from a buffered image (bitmap).

```java
TextResult[] decodeBufferedImage(Bitmap image, String templateName) throws IOException, BarcodeReaderException
```

**Parameters**

`image`: The image to be decoded.  
`templateName`: The template name.

**Return Value**

All barcode text results decoded successfully.  

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html), IOException

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
/*get BufferedImage input from other component*/
TextResult[] result = reader.decodeBufferedImage(input, "");
```

## initIntermediateResult

Inits an intermediateResult struct with default values.

```java
IntermediateResult initIntermediateResults(int resultType) throws BarcodeReaderException
```

**Parameters**

`resultType`: The type of the intermediate result to init.

**Return Value**

An intermediateResult struct with default values.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
IntermediateResult imResult = reader.initIntermediateResult(EnumIntermediateResultType.IRT_ORIGINAL_IMAGE);
```

## decodeIntermediateResults

Decodes barcode from intermediate results.

```java
TextResult[] decodeIntermediateResults(IntermediateResult[] results, String templateName) throws BarcodeReaderException
```

**Parameters**

`results`: An array of intermediate result.  
`templateName`: The template name.

**Return Value**

All barcode text results decoded successfully.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.intermediateResultTypes = EnumIntermediateResultType.IRT_ORIGINAL_IMAGE;
reader.updateRuntimeSettings(settings);
reader.decodeFile("your file path", "");
IntermediateResult[] irtResult = reader.getIntermediateResults();
TextResult[] result = reader.decodeIntermediateResults(irtResult, "");
```
