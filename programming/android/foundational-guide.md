---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader for Android
description: This is the user guide of Dynamsoft Barcode Reader for Android SDK.
keywords: user guide, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Build Your App with Foundational APIs

## Requirements

- Supported OS: Android 5.0 (API Level 21) or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Android Studio 2022.2.1 or higher.

## Add the Libraries

There are two ways to add the libraries into your project - **Manually** and **Maven**.

### Option 1: Add the Libraries via Maven

1. Open the file `[App Project Root Path]\app\build.gradle` and add the Maven repository:

   ```groovy
   allprojects {
      repositories {
         maven {
               url "https://download2.dynamsoft.com/maven/aar"
         }
      }
   }
   ```

2. Add the references in the dependencies:

   ```groovy
   dependencies {
      implementation 'com.dynamsoft:dynamsoftbarcodereaderbundle:10.4.2003'
   }
   ```

   > Read more about the modules of [dynamsoftbarcodereaderbundle](api-reference/index.html){:target="_blank"}

3. Click **Sync Now**. After the synchronization is complete, the SDK is added to the project.

### Option 2: Add the Libraries via Local .aar Files

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">Dynamsoft Website</a>. After unzipping, seven **aar** files can be found in the **Dynamsoft\Libs** directory:

   - **DynamsoftCaptureVisionRouter.aar**
   - **DynamsoftBarcodeReader.aar**
   - **DynamsoftCore.aar**
   - **DynamsoftImageProcessing.aar**
   - **DynamsoftLicense.aar**
   - **DynamsoftUtility.aar**
   - **DynamsoftCameraEnhancer.aar** (Optional)
      >Note:
      >
      >If you want to use Android Camera SDK or your own sdk to control camera, please ignore **DynamsoftCameraEnhancer.aar** in the following steps.

2. Copy the above seven **aar** files to the target directory such as `[App Project Root Path]\app\libs`

3. Open the file `[App Project Root Path]\app\build.gradle` and add the reference in the dependencies:

   ```groovy
   dependencies {
       implementation fileTree(dir: 'libs', include: ['*.aar'])

        def camerax_version = '1.1.0'
        implementation "androidx.camera:camera-core:$camerax_version"
        implementation "androidx.camera:camera-camera2:$camerax_version"
        implementation "androidx.camera:camera-lifecycle:$camerax_version"
        implementation "androidx.camera:camera-view:$camerax_version"
   }
   ```

   > Note:
   >
   > You need to add the CameraX dependency to use the `DynamsoftCameraEnhancer` library.
   > camerax_version 1.3.0+ is not currently compatible with the DynamsoftCameraEnhancer library.

4. Click **Sync Now**. After the synchronization is complete, the SDK is added to the project.

## Build Your First Application

In this section, we are going to explain how to create a Hello World implementation similar to our simple `DecodeWithCameraEnhancer` app for reading barcodes from camera video input.

>Note:
>
> - Android Studio 2022.3.1 is used here in this guide.
> - You can get similar source code from
>   - <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/DecodeWithCameraEnhancer" target="_blank">DecodeWithCameraEnhancer Sample (Java)</a>
>   - DynamsoftCameraEnhancer library is used for camera capture in this guide below. If you use the Android CameraX SDK for camera capture, check [DecodeWithCameraX sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/DecodeWithCameraX){:target="_blank"} on how to add barcode scanning to your app.

### Create a New Project

1. Open Android Studio, select **File > New > New Project**.

2. Choose the correct template for your project. In this sample, we use **Empty Views Activity**.

3. When prompted, set your app name to 'DecodeWithCameraEnhancer' and set the **Save** location, **Language**, and **Minimum SDK** (we use 21 here).
    > Note:
    >
    > - With **minSdkVersion** set to 21, your app is compatible with more than 99.6% of devices on the Google Play Store (last update: October 2023).

### Include the Libraries

Add the SDK to your new project. Please read [Add the Libraries](#add-the-libraries) section for more details.

### Initialize License

1. Initialize the license in the file `MainActivity.java`.

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
                LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", this, (isSuccess, error) -> {
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
                LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", this) { isSuccess: Boolean, error: Exception ->
                   if (!isSuccess) {
                      error.printStackTrace()
                   }
                }
             }
      }
   }
   ```

   >Note:  
   >  
   >- The license string here grants a time-limited free trial which requires network connection to work.
   >- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=android){:target="_blank"} link.
   >- If you download the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?product=dbr&utm_source=guide&package=android" target="_blank">Installation Package</a>, it comes with a 30-day trial license by default.

### Initialize Camera Module

1. In the Project window, open **app > res > layout > `activity_main.xml`** and create a DCE camera view section under the root node.

   ```xml
    <com.dynamsoft.dce.CameraView
        android:id="@+id/camera_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>
    ```

2. Import the dynamsoft camera module, initialize the camera view and bind to the created Camera Enhancer instance in the file `MainActivity.java`.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1. 
   ```java
   import com.dynamsoft.dce.CameraView;
   import com.dynamsoft.dce.CameraEnhancer;
   import com.dynamsoft.dce.utils.PermissionUtil;
   public class MainActivity extends AppCompatActivity {
      CameraEnhancer mCamera;
      @Override
      protected void onCreate(Bundle savedInstanceState) {
             ...
             // Add camera view for previewing video.
             PermissionUtil.requestCameraPermission(this);
             CameraView cameraView = findViewById(R.id.camera_view);
             mCamera = new CameraEnhancer(cameraView, this);
      }
   }
   ```
   2. 
   ```kotlin
   import com.dynamsoft.dce.CameraView
   import com.dynamsoft.dce.CameraEnhancer
   import com.dynamsoft.dce.utils.PermissionUtil
   class MainActivityKt : AppCompatActivity() {
      private lateinit var mCamera: CameraEnhancer
      override fun onCreate(savedInstanceState: Bundle?) {
             ...
             PermissionUtil.requestCameraPermission(this)
             val cameraView: CameraView = findViewById(R.id.camera_view)
             mCamera = CameraEnhancer(cameraView, this)
      }
   }
   ```

### Initialize Capture Vision Router

1. Import and initialize the `CaptureVisionRouter` and set the previously created `CameraEnhancer` instance as its input.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1. 
   ```java
   import com.dynamsoft.cvr.CaptureVisionRouter;
   import com.dynamsoft.cvr.CaptureVisionRouterException;
   public class MainActivity extends AppCompatActivity {
      ...
      private CaptureVisionRouter mRouter;
      @Override
      protected void onCreate(Bundle savedInstanceState) {
             ...
             mRouter = new CaptureVisionRouter(this);
             try {
                mRouter.setInput(mCamera);
             } catch (CaptureVisionRouterException e) {
                throw new RuntimeException(e);
             }
      }
   }
   ```
   2. 
   ```kotlin
   import com.dynamsoft.cvr.CaptureVisionRouter
   import com.dynamsoft.cvr.CaptureVisionRouterException
   class MainActivityKt : AppCompatActivity() {
      private lateinit var mRouter: CaptureVisionRouter
      override fun onCreate(savedInstanceState: Bundle?) {
             ...
             mRouter = CaptureVisionRouter(this)
             try {
                mRouter.setInput(mCamera)
             } catch (e: CaptureVisionRouterException) {
                throw RuntimeException(e)
             }
      }
   }
   ```

2. Create a `CapturedResultReceiver` and register with the `CaptureVisionRouter` instance to get recognized barcode results.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1. 
   ```java
   import com.dynamsoft.core.basic_structures.CapturedResultReceiver;
   import com.dynamsoft.dbr.DecodedBarcodesResult;
   public class MainActivity extends AppCompatActivity {
      @Override
      protected void onCreate(Bundle savedInstanceState) {
             ...
             mRouter.addResultReceiver(new CapturedResultReceiver() {
                @Override
                public void onDecodedBarcodesReceived(DecodedBarcodesResult result) {
                   runOnUiThread(() -> showResult(result));
                }
             });
      }
   }
   ```
   2. 
   ```kotlin
   import com.dynamsoft.core.basic_structures.CapturedResultReceiver
   import com.dynamsoft.dbr.DecodedBarcodesResult
   class MainActivityKt : AppCompatActivity() {
      override fun onCreate(savedInstanceState: Bundle?) {
             ...
             mRouter.addResultReceiver(object : CapturedResultReceiver {
                override fun onDecodedBarcodesReceived(result: DecodedBarcodesResult) {
                   runOnUiThread { showResult(result) }
                }
             })
      }
   }
   ```

3. Override the `MainActivity.onResume` and `MainActivity.onPause` functions to start/stop video barcode scanning. After scanning starts, the sdk will automatically decode the video frames from the Camera Enhancer, then send the recognized barcode results to the callback.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1. 
   ```java
   import com.dynamsoft.cvr.EnumPresetTemplate;
   import com.dynamsoft.dce.CameraEnhancerException;
   public class MainActivity extends AppCompatActivity {
      ...
      @Override
      public void onResume() {
             // Start video barcode reading
             try {
                mCamera.open();
             } catch (CameraEnhancerException e) {
                e.printStackTrace();
             }
             mRouter.startCapturing(EnumPresetTemplate.PT_READ_BARCODES, new CompletionListener() {
                @Override
                public void onSuccess() {}
                @Override
                public void onFailure(int errorCode, String errorString) {
                   runOnUiThread(() -> showDialog("Error", String.format(Locale.getDefault(), "ErrorCode: %d %nErrorMessage: %s", errorCode, errorString)));
                }
             });
             super.onResume();
      }
      @Override
      public void onPause() {
            // Stop video barcode reading
            try {
               mCamera.close();
            } catch (CameraEnhancerException e) {
               e.printStackTrace();
            }
            mRouter.stopCapturing();
            super.onPause();
      }
   }
   ```
   2. 
   ```kotlin
   import com.dynamsoft.cvr.EnumPresetTemplate
   import com.dynamsoft.dce.CameraEnhancerException
   public class MainActivity extends AppCompatActivity {
      ...
      public override fun onResume() {
             // Start video barcode reading
             try {
                mCamera.open()
             } catch (e: CameraEnhancerException) {
                e.printStackTrace()
             }
             mRouter.startCapturing(EnumPresetTemplate.PT_READ_BARCODES, object : CompletionListener {
                override fun onSuccess() {}
                override fun onFailure(errorCode: Int, errorString: String?) =
                   runOnUiThread { showDialog("Error", "ErrorCode: $errorCode ErrorMessage: $errorString") }
             })
             super.onResume()
      }
      public override fun onPause() {
             // Stop video barcode reading
             try {
                mCamera.close()
             } catch (e: CameraEnhancerException) {
                e.printStackTrace()
             }
             mRouter.stopCapturing()
             super.onPause()
      }
   }
   ```

### Display Barcode Results

Display the barcode result(s) in a dialog box.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
...
import android.app.AlertDialog;
import com.dynamsoft.dbr.BarcodeResultItem;
import com.dynamsoft.dce.Feedback;
public class MainActivity extends AppCompatActivity {
   private AlertDialog mAlertDialog;
   ...
   private void showResult(DecodedBarcodesResult result) {
          StringBuilder strRes = new StringBuilder();
          if (result != null && result.getItems() != null && result.getItems().length > 0) {
             mRouter.stopCapturing();
             for (int i = 0; i < result.getItems().length; i++) {
                BarcodeResultItem item = result.getItems()[i];
                strRes.append(item.getFormatString()).append(":").append(item.getText()).append("\n\n");
             }
             if (mAlertDialog != null && mAlertDialog.isShowing()) {
                return;
             }
             Feedback.vibrate(this);
             showDialog("Results:", strRes.toString());
          }
   }
   private void showDialog(String title, String message) {
          if(mAlertDialog == null) {
             mAlertDialog = new AlertDialog.Builder(this).setCancelable(true).setPositiveButton("OK", null)
                .setOnDismissListener(dialog -> mRouter.startCapturing(EnumPresetTemplate.PT_READ_BARCODES, null))
                .create();
          }
          mAlertDialog.setTitle(title);
          mAlertDialog.setMessage(message);
          mAlertDialog.show();
   }
}
```
2. 
```kotlin
...
import android.app.AlertDialog
import com.dynamsoft.dbr.BarcodeResultItem
import com.dynamsoft.dce.Feedback
class MainActivityKt : AppCompatActivity() {
   private var mAlertDialog: AlertDialog? = null
   ...
   private fun showResult(result: DecodedBarcodesResult?) {
          val strRes = StringBuilder()
          if (result?.items != null && result.items.isNotEmpty()) {
             mRouter.stopCapturing()
             for (i in result.items.indices) {
                val item: BarcodeResultItem = result.items[i]
                strRes.append(item.formatString).append(":").append(item.text)
                   .append("\n\n")
             }
             if (mAlertDialog != null && mAlertDialog!!.isShowing) {
                return
             }
             Feedback.vibrate(this)
             showDialog("Results:", strRes.toString())
          }
   }
   private fun showDialog(title: String, message: String?) {
          if (mAlertDialog == null) {
             mAlertDialog = AlertDialog.Builder(this).setCancelable(true).setPositiveButton("OK", null)
                .setOnDismissListener { mRouter.startCapturing(EnumPresetTemplate.PT_READ_BARCODES, null) }
                .create()
          }
          mAlertDialog!!.setTitle(title)
          mAlertDialog!!.setMessage(message)
          mAlertDialog!!.show()
   }
}
```

### Build and Run the Project

1. Select the device that you want to run your app on from the target device drop-down menu in the toolbar.

2. Click the **Run app** button, then Android Studio installs your app on the connected device and launches it.

You can also download the full source code of all the steps above:

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationAPISamples/DecodeWithCameraEnhancer" target="_blank">DecodeWithCameraEnhancer Sample (Java)</a>

## Next Steps

From this page, you have learned how to create a simple video barcode decoding app. In the next steps, the following pages will help you on adding configurations to enhance your barcode reader.

### Explore Features

If you want to explore the many features of the SDK and learn how to use them to best process the images you read in your application, read the articles in [Explore Features](user-guide/explore-features/index.md).

### Check Use Cases

If you want to check how the SDK works in popular use cases, read the articles in [Use Cases](user-guide/use-cases/index.md).

### Using CameraX with DBR

If you use the Android CameraX SDK, [DecodeWithCameraX sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/DecodeWithCameraX){:target="_blank"} will guide you on how to add barcode scanning to your app.

### Other platforms

- <a target="_blank" href="https://www.dynamsoft.com/barcode-reader/docs/mobile/programming/objectivec-swift/?ver=latest">Getting Started with iOS</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/react-native/?ver=latest">Getting Started with React Native</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/flutter/?ver=latest">Getting Started with Flutter</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/xamarin/?ver=latest">Getting Started with Xamarin.Forms</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/cordova/?ver=latest">Getting Started with Cordova</a>
