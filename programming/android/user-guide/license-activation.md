---
layout: default-layout
title: License Activation - Dynamsoft Barcode Reader Android Edition
description: Initialize the license of Dynamsoft Barcode Reader Android edition.
keywords: license initialization, licensing
needAutoGenerateSidebar: true
---

# License Initialization

## Get a trial license

You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs&package=mobile){:target="_blank"} link.

You can contact our support team via the [Contacting Us](https://www.dynamsoft.com/contact/){:target="_blank"} link when:

- You want request for an Offline trial license.
- Your license generation failed.

## Get a Full License

<a href="https://www.dynamsoft.com/company/contact" target="_blank">Contact us</a> to purchase a full license.

## Set the License In the Code

### For BarcodeScanner

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
```
1. 
```kotlin
val config = BarcodeScannerConfig().apply {
   license = "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9"
}
```

### For Foundational Barcode Reader

The following shows how to set the license in the code.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
import com.dynamsoft.license.LicenseManager;
public class MainActivity extends AppCompatActivity {
   @Override
   protected void onCreate(Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
          setContentView(R.layout.activity_main);
          if (savedInstanceState == null) {
             LicenseManager.initLicense("YOUR-LICENSE-KEY", this, (isSuccess, error) -> {
                if (!isSuccess) {
                   error.printStackTrace();
                }
             });
          }
   }
}
```
2. 
```kotlin
import com.dynamsoft.license.LicenseManager;
class MainActivityKt : AppCompatActivity() {
   override fun onCreate(savedInstanceState: Bundle?) {
          super.onCreate(savedInstanceState)
          setContentView(R.layout.activity_main_kt)
          if (savedInstanceState == null) {
             LicenseManager.initLicense("YOUR-LICENSE-KEY", this) { isSuccess: Boolean, error: Exception ->
                if (!isSuccess) {
                   error.printStackTrace()
                }
             }
          }
   }
}
```
