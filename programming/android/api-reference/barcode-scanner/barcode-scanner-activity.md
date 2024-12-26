---
layout: default-layout
title: BarcodeScannerActivity Class - Dynamsoft Barcode Scanner Android Edition
description: BarcodeScannerActivity of DynamsoftBarcodeScanner Android is an activity class that implements barcode decoding features.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScannerActivity
---

# Class BarcodeScannerActivity

`BarcodeScannerActivity` is an activity class that implements barcode decoding features.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.aar

*Namespace:* com.dynamsoft.dbrbundle.ui

```java
class BarcodeScannerActivity extends AppCompatActivity
```

## ResultContract

A contract specifying that the activity `BarcodeScannerActivity` can be called with an input of type `BarcodeScannerConfig` and produce an output of type `BarcodeScanResult`.

```java
public static final class ResultContract extends ActivityResultContract<BarcodeScannerConfig, BarcodeScanResult>
```

## How to Use

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
public class MainActivity extends AppCompatActivity {
   private ActivityResultLauncher<BarcodeScannerConfig> launcher;
   @Override
   protected void onCreate(@Nullable Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
          setContentView(R.layout.activity_main);
          TextView textView = findViewById(R.id.tv_result);
          // Set up the license via the BarcodeScannerConfig
          BarcodeScannerConfig config = new BarcodeScannerConfig();
          config.setLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
          // Set up a launcher and register the result callback for BarcodeScannerActivity.
          launcher = registerForActivityResult(new BarcodeScannerActivity.ResultContract(), result -> {
             if (result.getResultStatus() == BarcodeScanResult.EnumResultStatus.RS_FINISHED && result.getBarcodes() != null) {
                    String content = "Result: format: " + result.getBarcodes()[0].getFormatString() + "\n" + "content: " + result.getBarcodes()[0].getText();
                    textView.setText(content);
             } else if (result.getResultStatus() == BarcodeScanResult.EnumResultStatus.RS_CANCELED) {
                    textView.setText("Scan canceled.");
             }
             if (result.getErrorString() != null && !result.getErrorString().isEmpty()) {
                    textView.setText(result.getErrorString());
             }
          });
          // Config a button on the UI. Launch the BarcodeScannerActivity when button clicked.
          findViewById(R.id.btn_navigate).setOnClickListener(v -> launcher.launch(config));
   }
}
```
2. 
```kotlin
class MainActivity : AppCompatActivity() {
   private lateinit var launcher: ActivityResultLauncher<BarcodeScannerConfig>
   override fun onCreate(savedInstanceState: Bundle?) {
          super.onCreate(savedInstanceState)
          setContentView(R.layout.activity_main)
          val textView = findViewById<TextView>(R.id.tv_result)
          // Set up the license via the BarcodeScannerConfig
          val config = BarcodeScannerConfig().apply {
             license = "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9";
          }
          // Set up a launcher and register the result callback for BarcodeScannerActivity.
          launcher = registerForActivityResult(BarcodeScannerActivity.ResultContract()) { result ->
             if (result.resultStatus == BarcodeScanResult.EnumResultStatus.RS_FINISHED && result.barcodes != null) {
                    val content = """
                    Result: format: ${result.barcodes[0].formatString}
                    content: ${result.barcodes[0].text}
                    """.trimIndent()
                    textView.text = content
             } else if (result.resultStatus == BarcodeScanResult.EnumResultStatus.RS_CANCELED) {
                    textView.text = "Scan canceled."
             }
             if (result.errorString != null && result.errorString.isNotEmpty()) {
                    textView.text = result.errorString
             }
          }
          // Config a button on the UI. Launch the BarcodeScannerActivity when button clicked.
          findViewById<View>(R.id.btn_navigate).setOnClickListener {
             launcher.launch(
                    config
             )
          }
   }
}
```
