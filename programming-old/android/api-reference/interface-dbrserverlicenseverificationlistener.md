---
layout: default-layout
title: Interface DBRServerLicenseVerificationListener - Dynamsoft Barcode Reader Android API Reference
description: This is the interface DBRServerLicenseVerificationListener page of Dynamsoft Barcode Reader for Android SDK.
keywords: DBRServerLicenseVerificationListener, interface, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
ignore: true
permalink: /programming/android/api-reference/interface-dbrserverlicenseverificationlistener.html
---

# DBRServerLicenseVerificationListener

`DBRServerLicenseVerificationListener` is the interface to handle license verification callback when using `initLicenseFromServer`.

> Note:  
>  
> - `initLicenseFromServer` and `DBRServerLicenseVerificationListener` are deprecated in 9.0 version.  
> - Please use [`DBRLicenseVerificationListener`](interface-dbrlicenseverificationlistener.html) and [`initLicense`](primary-license.html#initlicense) to initialize and verify the license in 9.x versions.

```java
interface com.dynamsoft.dbr.DBRServerLicenseVerificationListener
```

| Method | Description |
| ------ | ----------- |
| `licenseVerificationCallback` | The callback of license server. |

## licenseVerificationCallback

```java
void licenseVerificationCallback(boolean isSuccess, Exception error);
```

**Parameters**

`isSuccess`: Whether the license verification was successful.  
`error`: The error message from license server.

**Code Snippet**

```java
DBRServerLicenseVerificationListener licenseVerificationListener = new DBRServerLicenseVerificationListener() {
    @Override
    public void licenseVerificationCallback(boolean b, Exception e) {
        // Add your code
    }
};
```
