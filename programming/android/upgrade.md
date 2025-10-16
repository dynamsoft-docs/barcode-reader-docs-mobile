---
layout: default-layout
title: How to update - Dynamsoft Barcode Reader for Android
description: Follow the upgrade instructions to learn to upgrade Barcode Reader SDK Android edition from 10 to 11.
keywords: updates guide, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
pageStartVer: 10.0
---

# How to Upgrade

## From Version 10.x to 11.x

### Update the Libraries

#### Option 1: Add the Library via Maven

1. Open the file `[App Project Root Path]\settings.gradle` and add the Maven repository:

   <div class="sample-code-prefix"></div>
   >- groovy
   >- kts
   >
   >1. 
   ```groovy
   dependencyResolutionManagement {
      repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
      repositories {
             google()
             mavenCentral()
             maven {
                url "https://download2.dynamsoft.com/maven/aar"
             }
      }
   }
   ```
   2. 
   ```kotlin
   dependencyResolutionManagement {
      repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
      repositories {
             google()
             mavenCentral()
             maven {
                url = uri("https://download2.dynamsoft.com/maven/aar")
             }
      }
   }
   ```

2. Open the file `[App Project Root Path]\app\build.gradle` and add the dependencies:

   <div class="sample-code-prefix"></div>
   >- groovy
   >- kts
   >
   >1. 
   ```groovy
   dependencies {
      implementation 'com.dynamsoft:barcodereaderbundle:{version-number}'
   }
   ```
   2. 
   ```kotlin
   dependencies {
      implementation("com.dynamsoft:barcodereaderbundle:{version-number}")
   }
   ```

   <div class="blockquote-note"></div>
   > Please view [user guide](user-guide.md#option-1-add-the-library-via-maven) for the correct version number.

3. Click **Sync Now**. After the synchronization is complete, the SDK is added to the project.

#### Option 2: Add the Libraries via Local .aar Files

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Dynamsoft Website</a>. After unzipping, several **aar** files can be found in the **Dynamsoft\Libs** directory:

   - 📄 **DynamsoftBarcodeReaderBundle.aar**
   - 📄 **DynamsoftCaptureVisionBundle.aar**

2. Copy the above **.aar** files to the target directory such as *[App Project Root Path]\app\libs*

3. Open the file `[App Project Root Path]\app\build.gradle` and add the reference in the dependencies:

   <div class="sample-code-prefix"></div>
   >- groovy
   >- kts
   >
   >1. 
   ```groovy
   dependencies {
      implementation fileTree(dir: 'libs', include: ['*.aar'])
      def camerax_version = '1.4.2'
      implementation "androidx.camera:camera-core:$camerax_version"
      implementation "androidx.camera:camera-camera2:$camerax_version"
      implementation "androidx.camera:camera-lifecycle:$camerax_version"
      implementation "androidx.camera:camera-view:$camerax_version"
   }
   ```
   2. 
   ```kotlin
   val camerax_version = "1.4.2"
   dependencies {
      implementation(fileTree(mapOf("dir" to "libs", "include" to listOf("*.aar"))))
      implementation("androidx.camera:camera-core:$camerax_version")
      implementation("androidx.camera:camera-camera2:$camerax_version")
      implementation("androidx.camera:camera-lifecycle:$camerax_version")
      implementation("androidx.camera:camera-view:$camerax_version")
   }
   ```

   <div class="blockquote-note"></div>
   > The camera features require the camerax dependencies.

4. Click **Sync Now**. After the synchronization is complete, the SDK is added to the project.

### Update the Template File

You can use the template converter to upgrade your template. View the [online template converter](https://www.dynamsoft.com/tools/template-upgrade/)

## From version 9.x or earlier

Dynamsoft Barcode Reader SDK has been refactored to integrate with DynamsoftCaptureVision (DCV) architecture since version 10. To upgrade from version 9.x or earlier to 11.x, we recommend you to follow the [User Guide](user-guide.md) and re-write your codes. This section highlights only the key changes and necessary actions for upgrading the SDK.
