---
layout: default-layout
title: Migrate from v9 to v11 - Dynamsoft Barcode Reader for Android
description: Follow this page to learn to upgrade Barcode Reader SDK Android edition from v9 to v11.
keywords: updates guide, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Migrate from v9 to v11

> [!IMPORTANT]
> **We strongly recommend upgrading to v11.x.** All future algorithm improvements, performance optimizations, and new features will be developed exclusively for v11 and later versions.
> **Critical: Version 9.x and earlier are on a legacy architecture.** All new algorithm development, performance improvements, and features are built exclusively on the DynamsoftCaptureVision (DCV) architecture introduced in v10+. 
> 
> **Staying on v9.x or earlier means:**
> - ❌ No access to new barcode recognition algorithms
> - ❌ No future performance optimizations
> - ❌ Missing out on new symbology support
> - ❌ Limited to critical security patches only
>
> **Upgrading to v11 provides:**
> - ✅ Access to all future algorithm enhancements
> - ✅ Continuous performance improvements
> - ✅ New features and capabilities as they're released
> - ✅ Full technical support and active maintenance

Dynamsoft Barcode Reader SDK has been refactored to integrate with DynamsoftCaptureVision (DCV) architecture since version 10. To upgrade from version 9.x or earlier to 11.x, we recommend you to follow the [User Guide](user-guide.md) and re-write your codes. This section highlights only the key changes and necessary actions for upgrading the SDK.

**⚠️ Version 9.x is in maintenance mode only** - no new features or algorithm updates will be backported.

## Update the Libraries

### Option 1: Add the Library via Maven

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

### Option 2: Add the Libraries via Local .aar Files

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

## Update the Template File

You can use the template converter to upgrade your template. View the [online template converter](https://www.dynamsoft.com/tools/template-upgrade/)
