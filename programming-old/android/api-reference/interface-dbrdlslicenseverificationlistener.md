---
layout: default-layout
title: Interface DBRDLSLicenseVerificationListener - Dynamsoft Barcode Reader Android API Reference
description: This is the interface DBRDLSLicenseVerificationListener page of Dynamsoft Barcode Reader for Android SDK.
keywords: DBRDLSLicenseVerificationListener, interface, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
pageStartVer: 8.0
permalink: /programming/android/api-reference/interface-dbrdlslicenseverificationlistener.html
---

# DBRDLSLicenseVerificationListener

`DBRDLSLicenseVerificationListener` is the interface to handle license verification callback when using `initLicenseFromDLS`.

> Note:  
>  
> - Interface `DBRDLSLicenseVerificationListener` and `initLicenseFromDLS` are deprecated in 9.0 version.  
> - Please use [`DBRLicenseVerificationListener`](interface-dbrlicenseverificationlistener.html) and [`initLicense`](primary-license.html#initlicense) to initialize and verify the license in 9.x versions.

```java
interface com.dynamsoft.dbr.DBRDLSLicenseVerificationListener
```

| Method | Description |
| ------ | ----------- |
| `DLSLicenseVerificationCallback` | The callback of license server. |

## DLSLicenseVerificationCallback

```java
void DLSLicenseVerificationCallback(boolean isSuccess, Exception error);
```

**Parameters**

`isSuccess`: Whether the license verification was successful.  
`error`: The error message from license server.

**Code Snippet**

```java
DBRDLSLicenseVerificationListener dbrDLSListener = new DBRDLSLicenseVerificationListener() {
    @Override
    public void DLSLicenseVerificationCallback(boolean b, Exception e) {
        // Add your code
    }
};
```
