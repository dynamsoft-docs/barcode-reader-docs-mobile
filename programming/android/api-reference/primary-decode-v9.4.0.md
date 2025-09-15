---
layout: default-layout
title: BarcodeReader Decode Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader Decode methods of Dynamsoft Barcode Reader for Android SDK.
keywords: decodeFile, decodeFileInMemory, decodeBuffer, decodeBase64String, decodeBufferedImage, decode methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: false
permalink: /programming/android/api-reference/primary-decode-v9.4.0.html
---


# Decode Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeBuffer`](#decodebuffer) | Decode barcodes with image data including pixel buffer, width, height, stride and pixel format. Generally, this method is used when processing video streaming. |
  | [`decodeFile`](#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory(fileBytes)`](#decodefileinmemoryfilebytes) | Decode barcodes from an image file in memory. |
  | [`decodeFileInMemory(fileStream)`](#decodefileinmemoryfilestream) | Decode barcodes from an image file in memory. |
  | [`decodeBase64String`](#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](#decodebufferedimage) | Decodes barcode from a buffered imag (bitmap). |
  
  ---

## decodeBuffer

Decode barcodes with image data including pixel buffer, width, height, stride and pixel format.

```java
TextResult[] decodeBuffer(byte[] buffer, int width, int height, int stride, int enumImagePixelFormat) throws BarcodeReaderException
```

**Parameters**

`buffer`: The array of bytes that stores the pixel buffer of the image.  
`Width`: The width of the image in pixels.  
`Height`: The height of the image in pixels.  
`Stride`: The stride is measured by the `byte` length of each line in the `buffer`.  
`format`: The image pixel format used in the image byte array.  

**Return Value**

The [`TextResult`](auxiliary-TextResult.html) of all successfully decoded barcodes. `TextResult` includes the text, format and other information about the barcodes.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- The library failed to read the image.
- The image data type is not supported.

There are several approaches for you to get a buffered image.

### Get ImageData from DCEFrame

You can import CameraEnhancer to acquire buffered video frames from `frameOutputCallback` or `videoBuffer` of DCE.

**Code Snippet**

```java
/*You can get frames from frame output call back if you import dynamsoft camera enhancer package.*/
/*You can get all the required parameters of decodeBuffer from DCEFrame.*/
import com.dynamsoft.dce.CameraEnhancer;

BarcodeReader reader = new BarcodeReader();
mCameraEnhancer.addListener(new DCEFrameListener() {
  @Override
  public void frameOutputCallback(DCEFrame dceFrame, long l) {
    try {
      TextResult[] results = reader.decodeBuffer(dceFrame.getImageData(),dceFrame.getWidth(),dceFrame.getHeight(),dceFrame.getStrides()[0],dceFrame.getPixelFormat());
    } catch (BarcodeReaderException e) {
      e.printStackTrace();
    }
  }
});
```

### Get ImageData from Android Camera2

When you are using Android Camera2, you can get video frames from ImageReader.

**Code Snippet**

```java
previewReader.setOnImageAvailableListener(new ImageReader.OnImageAvailableListener() {
  @Override
  public void onImageAvailable(ImageReader reader) {
    Image mImage = reader.acquireLatestImage();
    ByteBuffer bufferY = mImage.getPlanes()[0].getBuffer();
    int strideY = mImage.getPlanes()[0].getRowStride() / mImage.getPlanes()[0].getPixelStride();
    ByteBuffer bufferU = mImage.getPlanes()[1].getBuffer();
    int strideU = mImage.getPlanes()[1].getRowStride() / mImage.getPlanes()[1].getPixelStride();
    ByteBuffer bufferV = mImage.getPlanes()[2].getBuffer();
    int strideV = mImage.getPlanes()[2].getRowStride() / mImage.getPlanes()[2].getPixelStride();
    int padingY = mImage.getPlanes()[0].getRowStride() - mImage.getWidth();
    int padingU = mImage.getPlanes()[1].getRowStride() - mImage.getWidth();
    byte[] newData = new byte[bufferY.limit()];
    newData = new byte[bufferY.limit() + bufferU.limit() + 1 + padingY + padingU];
    bufferV.get(newData, bufferY.limit() + padingY, 1);
    bufferU.get(newData, bufferY.limit() + padingY + 1, bufferU.limit());
    bufferY.get(newData, 0, bufferY.limit());
    int[] strides = new int[]{strideY, strideU, strideV};
    try {
      TextResult[] results = reader.decodeBuffer(newData, strideY, mImage.getHeight(), strideY, 3);
    } catch (BarcodeReaderException e) {
      e.printStackTrace();
    }
  }
},handler);
```

## decodeFile

Decode barcodes from a specified image file.

```java
TextResult[] decodeFile(String fileFullPath) throws BarcodeReaderException
```

**Parameters**

`fileFullPath`: A string defining the file path. It supports BMP, TIFF, JPG and PNG.

> Note: PDF is not supported by mobile editions. Please use server/desktop editions instead.

**Return Value**

The [`TextResult`](auxiliary-TextResult.html) of all successfully decoded barcodes. `TextResult` includes the text, format and other information about the barcodes.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- The file is not found.
- The library failed to read the image.
- The image data type is not supported.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
/*Read external storage permission is required when decoding from a file*/
TextResult[] result = reader.decodeFile(Environment.getExternalStorageDirectory().toString()+"your file path");
```

## decodeFileInMemory(fileBytes)

Decode barcodes from an image file in memory.

```java
TextResult[] decodeFileInMemory(byte[] fileBytes) throws BarcodeReaderException
```

**Parameters**

`fileBytes`: The image file bytes in memory.  

**Return Value**

The [`TextResult`](auxiliary-TextResult.html) of all successfully decoded barcodes. `TextResult` includes the text, format and other information about the barcodes.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- The library failed to read the image.
- The image data type is not supported.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding
get bufferBytes from other component*/
TextResult[] result = reader.decodeFileInMemory(bufferBytes);
```

## decodeFileInMemory(fileStream)

Decode barcodes from an image file in memory.

```java
TextResult [] decodeFileInMemory(InputStream fileStream) throws BarcodeReaderException, IOException
```

**Parameters**

`fileStream`: The image file bytes in memory.  

**Return Value**

The [`TextResult`](auxiliary-TextResult.html) of all successfully decoded barcodes. `TextResult` includes the text, format and other information about the barcodes.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- The library failed to read the image.
- The image data type is not supported.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding
get bufferBytes from other component*/
TextResult[] result = reader.decodeFileInMemory(fileStream);
```

## decodeBase64String

Decode barcode from an image file encoded as a base64 string.

```java
TextResult[] decodeBase64String(String base64) throws BarcodeReaderException
```

**Parameters**

`base64`: A base64 encoded string that represents an image.  

**Return Value**

The [`TextResult`](auxiliary-TextResult.html) of all successfully decoded barcodes. `TextResult` includes the text, format and other information about the barcodes.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- The library failed to read the image.
- The image data type is not supported.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
TextResult[] result = reader.decodeBase64String("file in base64 string");
```

## decodeBufferedImage

Decodes barcode from a buffered image (bitmap).

```java
TextResult[] decodeBufferedImage(Bitmap image) throws BarcodeReaderException
```

**Parameters**

`image`: The image to be decoded.

**Return Value**

The [`TextResult`](auxiliary-TextResult.html) of all successfully decoded barcodes. `TextResult` includes the text, format and other information about the barcodes.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- The library failed to read the image.
- The image data type is not supported.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
/*get BufferedImage input from other component*/
TextResult[] result = reader.decodeBufferedImage(input);
```

## initIntermediateResult

Inits an intermediateResult struct with default values.

```java
IntermediateResult initIntermediateResults(int resultType) throws BarcodeReaderException
```

**Parameters**

`resultType`: An int value that indicates the intermediate result type. The int value should be available in ([EnumIntermediateResultType]({{ site.mobile_enum }}intermediate-result-type.html?lang=android)).

**Return Value**

An [`IntermediateResult`](auxiliary-IntermediateResult.html) struct with default values.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- Your license key doesn't include the intermediate result item.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
IntermediateResult imResult = reader.initIntermediateResult(EnumIntermediateResultType.IRT_ORIGINAL_IMAGE);
```

## decodeIntermediateResults

Decodes barcode from intermediate results.

```java
TextResult[] decodeIntermediateResults(IntermediateResult[] results) throws BarcodeReaderException
```

**Parameters**

`results`: An array of intermediate result.  

**Return Value**

The [`TextResult`](auxiliary-TextResult.html) of all successfully decoded barcodes. `TextResult` includes the text, format and other information about the barcodes.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.intermediateResultTypes = EnumIntermediateResultType.IRT_ORIGINAL_IMAGE;
reader.updateRuntimeSettings(settings);
reader.decodeFile("your file path");
IntermediateResult[] irtResult = reader.getIntermediateResults();
TextResult[] result = reader.decodeIntermediateResults(irtResult);
```
