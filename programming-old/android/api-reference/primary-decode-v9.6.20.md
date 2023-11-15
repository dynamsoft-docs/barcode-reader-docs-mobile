---
layout: default-layout
title: BarcodeReader Decode Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader Decode methods of Dynamsoft Barcode Reader for Android SDK.
keywords: decodeFile, decodeFileInMemory, decodeBuffer, decodeBase64String, decodeBufferedImage, decode methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
permalink: /programming/android/api-reference/primary-decode-v9.6.20.html
---


# Decode Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeBuffer(ImageData)`](#decodebufferimagedata) | Decode barcodes with an image data object. This method can handle the orientation information and output a result with transformation matrix for transferring coordinates. |
  | [`decodeBuffer`](#decodebuffer) | Decode barcodes with image data including pixel buffer, width, height, stride and pixel format. Generally, this method is used when processing video streaming. |
  | [`decodeFile`](#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory(fileBytes)`](#decodefileinmemoryfilebytes) | Decode barcodes from an image file in memory. |
  | [`decodeFileInMemory(fileStream)`](#decodefileinmemoryfilestream) | Decode barcodes from an image file in memory. |
  | [`decodeBase64String`](#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](#decodebufferedimage) | Decodes barcode from a buffered imag (bitmap). |
  
  ---

## decodeBuffer(ImageData)

Decode barcodes from an `ImageData` object. The `ImageData` object stores the pixel buffer, width, height, stride and pixel format of the image.

```java
TextResult[] decodeBuffer(ImageData imageData) throws BarcodeReaderException
```

**Parameters**

`imageData`: The image data in memory buffer which also contains the pixel format and orientation information.  

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- The library failed to read the image.
- The image data type is not supported.

**Return Value**

The [`TextResult`](auxiliary-TextResult.html) of all successfully decoded barcodes. `TextResult` includes the text, format and other information about the barcodes.

There are several approaches for you to get an ImageData.

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
        ImageData data = new ImageData();
        data.bytes = dceFrame.getImageData();
        data.width = dceFrame.getWidth();
        data.height = dceFrame.getHeight();
        data.stride = dceFrame.getStrides()[0];
        data.format = dceFrame.getPixelFormat(); 
        data.orientation = dceFrame.getOrientation();
    }
});
```

### Get ImageData from Android Camera2

When you are using Android Camera2, you can create `ImageData` from `android.media.ImageReader`.

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
        ImageData data = new ImageData();
        data.bytes = dceFrame.getImageData();
        data.width = strideY;
        data.height = mImage.getHeight();
        data.stride = strideY;
        data.format = 3; 
        data.orientation = 0;
    }
},handler);
```

### Get ImageData from CameraX

When you are using CameraX, you can create `ImageData` from `androidx.camera.core.ImageProxy`.

**Code Snippet**

```java
private final ImageAnalysis.Analyzer mBarcodeAnalyzer = new ImageAnalysis.Analyzer() {
    @Override
    public void analyze(@NonNull ImageProxy imageProxy) {
        try {
            // insert your code here.
            // after done, release the ImageProxy object
            if (isShowingDialog) {
                mImageData = null;
                return;
            }
            byte[] data = new byte[imageProxy.getPlanes()[0].getBuffer().remaining()];
            imageProxy.getPlanes()[0].getBuffer().get(data);
            int nRowStride = imageProxy.getPlanes()[0].getRowStride();
            int nPixelStride = imageProxy.getPlanes()[0].getPixelStride();

            ImageData imageData = new ImageData();
            imageData.bytes = data;
            imageData.width = imageProxy.getWidth();
            imageData.height = imageProxy.getHeight();
            imageData.stride = nRowStride;
            imageData.format = EnumImagePixelFormat.IPF_NV21;
            imageData.orientation = imageProxy.getImageInfo().getRotationDegrees();
        } finally {
            imageProxy.close();
        }
    }
};
```

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
