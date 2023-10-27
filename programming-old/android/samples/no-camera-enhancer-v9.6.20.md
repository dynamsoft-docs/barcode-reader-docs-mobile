---
layout: default-layout
title: How to use the Barcode Reader without the Camera Enhancer - Dynamsoft Barcode Reader for Android
description: This is a guide on how to use the Android Barcode Reader with the CameraX component instead of Camera Enhancer.
keywords: iOS, sample, Android, camera
needAutoGenerateSidebar: true
breadcrumbText: No Camera Enhancer
permalink: /programming/android/samples/no-camera-enhancer-v9.6.20.html
---

# DecodeWithCameraX Sample

**DecodeWithCameraX** is a sample that demonstrate how to decode barcodes from video streaming when you are using `CameraX` as the source of video streaming. When using `CameraX` for barcode decoding, the key points are:

- Set up `CameraX` for capturing and displaying the video streaming.
- Receive the `ImageProxy` from `ImageAnalysis.Analyzer` and transfer the `ImageProxy` to `iImageData` so that it can be recognized by `DynamsoftBarcodeReader`.
- Add configurations to interface `ImageSource`. Let the method `getImage` returns the `iImageData` you generated from `ImageProxy`. The barcode reader can continuously obtain the `iImageData` via method `getImage`.

**View the Sample(s)**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.20/android/Java/DecodeWithCameraX/" target="_blank">Java (Android) DecodeWithCameraX Sample (v9.6.20)</a>

## Generate ImageData from ImageAnalysis

`iImageData` is the data type that can be recognized by `DynamsoftBarcodeReader` as an image source for barcode decoding. The following code snippet shows you how to transfer `ImageProxy`, which is produced by `CameraX`, to an `iImageData`.

**Code Snippet**

```java
public class CameraFragment extends Fragment {
    private ImageData mImageData;
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
                mImageData = imageData;
            } finally {
                imageProxy.close();
            }
        }
    };
}
```

## Setup Image Source

There are three key points when decoding barcodes from the video streaming:

- Set up the source of image. The source and be either `ImageSource` or `DynamsoftCameraEnhancer`.
- Set up the `DBRTextResultListener` for receiving the barcode result from the callback.
- Trigger the method `startScanning` when you want to start video streaming barcode decoding.

The following code snippet shows how to use `ImageSource` as the source of video barcode decoding.

```java
public class CameraFragment extends Fragment {
    // The mImageData will be updated each time when you receive new image from ImageAnalysis
    private ImageData mImageData;

    private void initBarcodeReader() {
        try {
            // Create an instance of Dynamsoft Barcode Reader.
            mReader = new BarcodeReader();
        } catch (BarcodeReaderException e) {
            e.printStackTrace();
        }
        // Set the ImageSource so that DBR will read barcode from ImageSource.
        mReader.setImageSource(new ImageSource() {
            @Override
            // Configure the method getImage. The method will be triggered each time when the library finished processing the previous image.
            public ImageData getImage() {
                return mImageData;
            }
        });
        // Set text result listener so that you can receive barcode result from textResultCallback.
        mReader.setTextResultListener(new TextResultListener() {
            @Override
            public void textResultCallback(int i, ImageData imageData, TextResult[] textResults) {
                // Add code to execute when barcode results are received.
            }
        });
    }

    @Override
    public void onResume() {
        super.onResume();
        // Methods startScanning and stopScanning are the switch of barcode decoding thread.
        // Once you have configured the source of image and trigger startScanning, you will be able to receive barcode result from textResultCallback.
        mReader.startScanning();
    }

    @Override
    public void onPause() {
        super.onPause();
        mReader.stopScanning();
    }
}
```

If you still have questions about the usage of `CameraX` when implementing video barcode decoding, you can view the sample for more details.
