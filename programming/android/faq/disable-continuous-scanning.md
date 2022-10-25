---
layout: default-layout
title: How do I disable the continuous barcode scanning feature and close the scanner view?
keywords: Dynamsoft Barcode Reader, FAQ, Mobile, tech basic, android, continuous scanning, disable
description: How do I disable the continuous barcode scanning feature and close the scanner view?
needAutoGenerateSidebar: false
---

## How do I disable the continuous barcode scanning feature and close the scanner view? 

[<< Back to FAQ index](index.md)

In a video scenario, the SDK scans continuously by default. In order to stop the scanning process, please call [`stopScanning`](../api-reference/primary-video.md#stopscanning) to stop barcode scanning, whether manually on the click of a button or automatically e.g. once a barcode is found.

Please note that `stopScanning` will only stop the barcode reader from picking up any more barcodes, but the *video will still be on*. In order to fully close the video view as well, the [`close`](https://www.dynamsoft.com/camera-enhancer/docs/programming/android/primary-api/camera-enhancer.html?ver=latest#close) method will need to be called on the `dce` object.

The next section will show some quick code snippets to help with this. Please note that these snippets are in Swift only at the moment:

```java
/* Here is a simple code snippet to create a button and have it close the scanner on click */
Button button = (Button) findViewById(R.id.button_send);
button.setOnClickListener(new View.OnClickListener() {
    public void closeTheScanner(View v) {
        mReader.stopScanning();
        mCameraEnhancer.close();

    }
});

/* And now to create a button and have it resume the scanning on click */
Button button = (Button) findViewById(R.id.button_send);
button.setOnClickListener(new View.OnClickListener() {
    public void resumeTheScanner(View v) {
        DCECameraView cameraView = findViewById(R.id.cameraView);

        mCameraEnhancer = new CameraEnhancer(MainActivity.this);
        mCameraEnhancer.setCameraView(cameraView);
        mReader.setCameraEnhancer(mCameraEnhancer);
        mReader.setTextResultListener(new TextResultListener() {
            // Obtain the recognized barcode results and display.
            @Override
            public void textResultCallback(int id, ImageData imageData, TextResult[] textResults) {
                (MainActivity.this).runOnUiThread(new Runnable() {
                    @Override
                    public void run() {
                    showResult(textResults);
                    }
                });
            }
        });
        mReader.startScanning();
    }
});
```

If you encounter any issues with this feature, please contact the Dynamsoft support team for help.