---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader for Android
description: This is the user guide of Dynamsoft Barcode Reader for Android SDK.
keywords: user guide, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/android/user-guide-v9.6.20.html
---


# Getting Started with Android

## Requirements

- Supported OS: <a href="https://developer.android.com/about/versions/lollipop" target="_blank">Android 5.0 (API Level 21)</a> or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Android Studio 3.4+ (Android Studio 4.2+ recommended).

## Add the SDK

The Dynamsoft Barcode Reader (DBR) Android SDK comes with two modules:

- **DynamsoftBarcodeReader.aar**: Main module. Provides APIs to easily scan 1D and 2D barcodes from image files and camera video.

- **DynamsoftCameraEnhancer.aar** (Optional): <a href="/camera-enhancer/docs/mobile/programming/android/?ver=2.3.10" target="_blank"> Dynamsoft Camera Enhancer (DCE) module</a> for getting video frames from mobile cameras. Provides APIs for camera control, camera preview, and other advanced features.
   >Note:
   >
   >**DCE is optional.** If you want to use Android CameraX SDK to control camera, preview video, and read barcodes in the callback function that outputs a video frame, please refer to [DecodeWithCameraX sample]({{ site.android }}samples/no-camera-enhancer.html).

There are two ways to add the SDK into your project - **Manually** and **Maven**.

### Add the Library Manually

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">Dynamsoft Website</a>. After unzipping, two **aar** files can be found in the **DynamsoftBarcodeReader\Libs** directory:

   - **DynamsoftBarcodeReader.aar**
   - **DynamsoftCameraEnhancer.aar** (Optional)
      >Note:
      >
      >If you want to use Android Camera SDK or your own sdk to control camera, please ignore **DynamsoftCameraEnhancer.aar** in the following steps.

2. Copy the above two **aar** files to the target directory such as `[App Project Root Path]\app\libs`

3. Open the file `[App Project Root Path]\app\build.gradle` and add reference in the dependencies:

    ```groovy
    dependencies {
        implementation fileTree(dir: 'libs', include: ['*.aar'])
    }
    ```

4. Click **Sync Now**. After the synchronization completes, the SDK is added to the project.

### Add the Library via Maven

1. Open the file `[App Project Root Path]\app\build.gradle` and add the maven repository:

    ```groovy
    repositories {
         maven {
            url "https://download2.dynamsoft.com/maven/aar"
         }
    }
    ```

2. Add reference in the dependencies:

   ```groovy
   dependencies {
      implementation 'com.dynamsoft:dynamsoftbarcodereader:9.6.20'
      
      // Remove the following line if you want to use Android Camera sdk or your own sdk to control camera.
      implementation 'com.dynamsoft:dynamsoftcameraenhancer:2.3.11'
   }
   ```

3. Click **Sync Now**. After the synchronization completes, the SDK is added to the project.

## Build Your First Application

In this section, let's see how to create a HelloWorld app for reading barcodes from camera video input.

>Note:
>
>- Android Studio 4.2 is used here in this guide.
>- You can get similar source code from
>    - <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.20/android/Java/HelloWorld" target="_blank">HelloWorld Sample (Java)</a>
>    - <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.20/android/Kotlin/HelloWorld" target="_blank">HelloWorld Sample (Kotlin)</a>
>- DCE is used for camera capture in this guide below. If you use the Android CameraX SDK for camera capture, check [DecodeWithCameraX sample]({{ site.android }}samples/no-camera-enhancer.html) on how to add barcode scanning to your app.

### Create a New Project

1. Open Android Studio, select **File > New > New Project**.

2. Choose the correct template for your project. In this sample, we use **Empty Activity**.

3. When prompted, choose your app name 'HelloWorld' and set the **Save** location, **Language**, and **Minimum SDK** (we use 21 here).
    > Note:
    >
    > - With **minSdkVersion** set to 21, your app is compatible with more than 94.1% of devices on the Google Play Store (last update: March 2021).

### Include the Library

Add the SDK to your new project. Please read [Add the SDK](#add-the-sdk) section for more details.

### Initialize License

1. Initialize the license in the file `MainActivity.java`.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1. 
   ```java
   import com.dynamsoft.dbr.BarcodeReader;
   import com.dynamsoft.dbr.DBRLicenseVerificationListener;
   public class MainActivity extends AppCompatActivity {
      @Override
      protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);
            // Initialize license for Dynamsoft Barcode Reader.
            BarcodeReader.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", new DBRLicenseVerificationListener() {
               @Override
               public void DBRLicenseVerificationCallback(boolean isSuccess, Exception error) {
                  if(!isSuccess){
                     error.printStackTrace();
                  }
               }
            });
      }
   }
   ```
   2. 
   ```kotlin
   import com.dynamsoft.dbr.BarcodeReader;
   import com.dynamsoft.dbr.DBRLicenseVerificationListener;
   class MainActivityKt : AppCompatActivity() {
      private lateinit var mReader: BarcodeReader
      private lateinit var mCameraEnhancer: CameraEnhancer
      private var alertDialog: AlertDialog? = null
      override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            setContentView(R.layout.activity_main_kt)
            BarcodeReader.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9") { isSuccessful, e ->
               runOnUiThread {
                  if (!isSuccessful) {
                     e.printStackTrace()
                     showDialog(getString(R.string.error_dialog_title), e.message?:"", null)
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
   <com.dynamsoft.dce.DCECameraView
      android:id="@+id/cameraView"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      tools:layout_editor_absoluteX="25dp"
      tools:layout_editor_absoluteY="0dp" />
    ```

2. Import the dynamsoft camera module, initialize the camera view and bind to the created Camera Enhancer instance in the file `MainActivity.java`.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1. 
   ```java
   import com.dynamsoft.dce.DCECameraView;
   import com.dynamsoft.dce.CameraEnhancer;
   import com.dynamsoft.dce.CameraEnhancerException;
   public class MainActivity extends AppCompatActivity {
      CameraEnhancer mCameraEnhancer;
      @Override
      protected void onCreate(Bundle savedInstanceState) {
            ...
            // Add camera view for previewing video.
            DCECameraView cameraView = findViewById(R.id.cameraView);
            mCameraEnhancer = new CameraEnhancer(MainActivity.this);
            mCameraEnhancer.setCameraView(cameraView);
      }
   }
   ```
   2. 
   ```kotlin
   import com.dynamsoft.dbr.BarcodeReader;
   import com.dynamsoft.dbr.DBRLicenseVerificationListener;
   class MainActivityKt : AppCompatActivity() {
      private lateinit var mCameraEnhancer: CameraEnhancer
      override fun onCreate(savedInstanceState: Bundle?) {
            val cameraView = findViewById<DCECameraView>(R.id.cameraView)
            cameraView.overlayVisible = true
            // Create an instance of Dynamsoft Camera Enhancer for video streaming.
            mCameraEnhancer = CameraEnhancer(this@MainActivityKt)
            mCameraEnhancer.cameraView = cameraView
      }
   }
   ```

### Initialize Barcode Reader

1. Import and initialize the barcode reader, bind to the created Camera Enhancer instance.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1. 
   ```java
   import com.dynamsoft.dbr.BarcodeReaderException;
   public class MainActivity extends AppCompatActivity {
      BarcodeReader mReader;
      @Override
      protected void onCreate(Bundle savedInstanceState) {
            ...
            try {
               mReader = new BarcodeReader();
            } catch (BarcodeReaderException e) {
               e.printStackTrace();
            }
            mReader.setCameraEnhancer(mCameraEnhancer);
      }
   }
   ```
   2. 
   ```kotlin
   import com.dynamsoft.dbr.BarcodeReaderException;
   class MainActivityKt : AppCompatActivity() {
      private lateinit var mCameraEnhancer: CameraEnhancer
      private lateinit var mReader: BarcodeReader
      override fun onCreate(savedInstanceState: Bundle?) {
            try {
               // Create an instance of Dynamsoft Barcode Reader.
               mReader = BarcodeReader()
            } catch (e: BarcodeReaderException) {
               e.printStackTrace()
            }
            mReader.setCameraEnhancer(mCameraEnhancer)
      }
   }
   ```

2. Create a barcode result listener and register with the barcode reader instance to get recognized barcode results.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1. 
   ```java
   import com.dynamsoft.dbr.ImageData;
   import com.dynamsoft.dbr.TextResult;
   import com.dynamsoft.dbr.TextResultListener;
   public class MainActivity extends AppCompatActivity {
      @Override
      protected void onCreate(Bundle savedInstanceState) {
            ...
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
      }
   }
   ```
   2. 
   ```kotlin
   import com.dynamsoft.dbr.BarcodeReaderException;
   class MainActivityKt : AppCompatActivity() {
      private lateinit var mCameraEnhancer: CameraEnhancer
      private lateinit var mReader: BarcodeReader
      override fun onCreate(savedInstanceState: Bundle?) {
            // Addd textResultListener to your project
            mReader.setTextResultListener { id, imageData, textResult ->
               runOnUiThread {
                  showResult(textResult)
               }
            }
      }
   }
   ```

3. Override the `MainActivity.onResume` and `MainActivity.onPause` functions to start/stop video barcode scanning. After scanning starts, the Barcode Reader will automatically invoke the `decodeBuffer` API to process the video frames from the Camera Enhancer, then send the recognized barcode results to the text result callback.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1. 
   ```java
   public class MainActivity extends AppCompatActivity {
      ...
      @Override
      public void onResume() {
            // Start video barcode reading
            mReader.startScanning();
            try {
               mCameraEnhancer.open();
            } catch (CameraEnhancerException e) {
               e.printStackTrace();
            }
            super.onResume();
      }
      @Override
      public void onPause() {
            // Stop video barcode reading
            mReader.stopScanning();
            try {
               mCameraEnhancer.close();
            } catch (CameraEnhancerException e) {
               e.printStackTrace();
            }
            super.onPause();
      }
   }
   ```
   2. 
   ```kotlin
   public class MainActivity extends AppCompatActivity {
      // Add configurations to onResume and onPause
      public override fun onResume() {
            // Start video barcode reading
            try {
               mCameraEnhancer.open()
            } catch (e: CameraEnhancerException) {
               e.printStackTrace()
            }
            mReader.startScanning()
            super.onResume()
      }
      public override fun onPause() {
            // Stop video barcode reading
            try {
               mCameraEnhancer.close()
            } catch (e: CameraEnhancerException) {
               e.printStackTrace()
            }
            mReader.stopScanning()
            super.onPause()
      }
   }
   ```

### Display Barcode Results

1. In the Project window, open **app > res > layout > `activity_main.xml`**, create a text view section under the root node to display the recognized barcode results. The following sample code is a TextView under RelativeLayout

   ```xml
   ...
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

2. Display barcode result in TextView.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1. 
   ```java
   public class MainActivity extends AppCompatActivity {
      ...
      TextView tvRes;
      @Override
      protected void onCreate(Bundle savedInstanceState) {
            ...
            // Add TextView to display recognized barcode results.
            tvRes = findViewById(R.id.tv_res);
      }
      private void showResult(TextResult[] results) {
            if (results != null && results.length > 0) {
               String strRes = "";
               for (int i = 0; i < results.length; i++)
                  strRes += results[i].barcodeText + "\n\n";
                  tvRes.setText(strRes);
            } else {
               tvRes.setText("");
            }
      }
   }
   ```
   2. 
   ```kotlin
   class MainActivityKt : AppCompatActivity() {
      private fun showDialog(
            title: String,
            message: String,
            listener: DialogInterface.OnClickListener?
      ) {
            val dialog = AlertDialog.Builder(this)
            alertDialog = dialog.setTitle(title).setPositiveButton("OK", listener)
               .setMessage(message)
               .setCancelable(false)
               .show()
      }
      private fun showResult(results: Array<TextResult>?){
            var strRes = "";
            if(results != null && results.isNotEmpty()){
               DCEFeedback.vibrate(this)
               mReader.stopScanning()
               for(i in results.indices){
                  strRes += results[i].barcodeText
               }
               if (alertDialog != null && alertDialog!!.isShowing) {
                  return
               }
               showDialog("Result", strRes){ _, _ -> mReader.startScanning()}
            }
      }
   }
   ```

### Build and Run the Project

1. Select the device that you want to run your app on from the target device drop-down menu in the toolbar.

2. Click the **Run app** button, then Android Studio installs your app on your connected device and starts it.

You can download similar source code here:

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.20/android/Java/HelloWorld" target="_blank">HelloWorld Sample (Java)</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.20/android/Kotlin/HelloWorld" target="_blank">HelloWorld Sample (Kotlin)</a>

## Next Steps

From this page, you have learned how to create a simple video barcode decoding app. In the next steps, the following pages will help you on adding configurations to enhance your barcode reader.

### Explore Features

If you want to explore the many features of the SDK and learn how to use them to best process the images you read in your application, read the articles in [Explore Features](user-guide/explore-features/index.html).

### Check Use Cases

If you want to check how the SDK works in popular use cases, read the articles in [Use Cases](user-guide/use-cases/index.html).

### Optimize Performance

If you have successfully integrated the SDK in your application but would like to get the best performance possible, read how to do this in [Optimize Performance](quick-performance-settings.html).

### Using CameraX with DBR

If you use the Android CameraX SDK, [DecodeWithCameraX sample]({{ site.android }}samples/no-camera-enhancer.html) will guide you on how to add barcode scanning to your app.

### Other platforms

- <a target="_blank" href="https://www.dynamsoft.com/barcode-reader/docs/mobile/programming/objectivec-swift/?ver=latest">Getting Started with iOS</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/react-native/?ver=latest">Getting Started with React Native</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/flutter/?ver=latest">Getting Started with Flutter</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/xamarin/?ver=latest">Getting Started with Xamarin.Forms</a>
- <a target="_blank" href="https://www.dynamsoft.com/capture-vision/docs/programming/cordova/?ver=latest">Getting Started with Cordova</a>
