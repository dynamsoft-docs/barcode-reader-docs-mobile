---
layout: default-layout
title: HelloWorld Sample - Dynamsoft Barcode Reader for Android
description: This is the HelloWorld Sample page of Dynamsoft Barcode Reader for Android SDK.
keywords: android, samples, HelloWorld
needAutoGenerateSidebar: true
breadcrumbText: HelloWorld
permalink: /programming/android/samples/helloworld-v9.6.20.html
---

# HelloWorld Sample

The Android Helloworld sample illustrates how to create the simplest video streaming barcode reading app with Dynamsoft Barcode Reader (DBR) Android SDK.

View the samples

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.20/android/Java/HelloWorld/" target="_blank">Java (Android) HelloWorld (v9.6.20)</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.20/android/Kotlin/HelloWorld/" target="_blank">Kotlin (Android) HelloWorld (v9.6.20)</a>

## How to Switch between One-off Scan & Continuous Scan

The default scan mode of the helloWorld sample is one-off scan. Here shows the sample code for you to switch the scan mode to continuous scan.

1. Add a textView in the layout file for displaying the results.

    ```xml
    <TextView
        android:id="@+id/tv_res"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:layout_marginTop="430dp"
        android:textSize="16sp"
        android:gravity="center"
        android:scrollbars="vertical"
        android:textColor="@color/white"
        android:visibility="visible"/>
    ```

2. Modify the method showResult with the following code:

    ```java
    private void showResult(TextResult[] results) {
        String strRes = "";
        if (results != null && results.length > 0) {
            DCEFeedback.vibrate(this);
            for (int i = 0; i < results.length; i++)
                strRes += results[i].barcodeText + "\n\n";
            TextView textView = findViewById(R.id.tv_res);
            textView.setText(strRes);
        }
    }
    ```

For more details about how to get started with Dynamsoft Barcode Reader, please view the [user guide]({{ site.android }}user-guide.html).
