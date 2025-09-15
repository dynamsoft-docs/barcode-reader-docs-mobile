---
layout: default-layout
title: DMDLSConnectionParameters Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the DMDLSConnectionParameters Class of Dynamsoft Barcode Reader for Android SDK.
keywords: DMDLSConnectionParameters, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
pageStartVer: 8.0
permalink: /programming/android/api-reference/auxiliary-DMDLSConnectionParameters-v8.1.2.html
---


# DMLTSConnectionParameters

Defines a struct to configure the parameters to connect to License Tracking Server.  

> Note:
>
> - This class is removed in version 9.0.

```java
class com.dynamsoft.dbr.DMLTSConnectionParameters
```

| Attributes | Type | Descriptions |
|----------- | ---- | ----------- |
| [`mainServerURL`](#mainserverurl) | *String* | The URL of the License Tracking Server. |
| [`standbyServerURL`](#standbyserverurl) | *String* | The URL of the standby License Tracking Server. |
| [`handshakeCode`](#handshakecode) | *String* | The handshake code. |
| [`sessionPassword`](#sessionpassword) | *String* | The session password of the handshake code set in License Tracking Server. |
| [`uuidGenerationMethod`](#uuidgenerationmethod) | *int* | Sets the method to generate UUID. |
| [`maxBufferDays`](#maxbufferdays) | *int* | Sets the max days to buffer the license info. |
| [`limitedLicenseModules`](#limitedlicensemodules) | *int[]* | Sets the license modules to use. |
| [`chargeWay`](#chargeway) | *int* | Sets the charge way. |

## mainServerURL

The URL of the Dynamsoft License Server.

```java
String mainServerURL
```

**Value Range**

Any string value

**Default Value**

null

**Remarks**

If you choose "Dynamsoft-hosting", then no need to change the value of MainServerURL and StandbyServerURL. When both are set to null (default value), it will connect to Dynamsoft's License Tracking Server for online verification.

## standbyServerURL

The URL of the standby License Tracking Server.

```java
String standbyServerURL
```

**Value Range**

Any string value

**Default Value**

null

**Remarks**

If you choose "Dynamsoft-hosting", then no need to change the value of MainServerURL and StandbyServerURL. When both are set to null (default value), it will connect to License Tracking Server for online verification.

## handshakeCode

The handshake code.

```java
String handshakeCode
```

**Value Range**

Any string value

**Default Value**

null

## sessionPassword

The session password of the handshake code set in License Tracking Server.

```java
String sessionPassword
```

**Value Range**

Any string value

**Default Value**

null

## uuidGenerationMethod

Sets the method to generate UUID.

```java
int uuidGenerationMethod
```

**Value Range**

Any one of the `EnumDMUUIDGenerationMethod` Enumeration items.

**Default Value**

DM_UUIDGM_RANDOM

## maxBufferDays

Sets the max days to buffer the license info.

```java
int maxBufferDays
```

**Value Range**

[7,0x7fffffff]  

**Default Value**

7

## limitedLicenseModules

Sets the license modules to use.

```java
List<Integer> limitedLicenseModules
```

**Value Range**

A list of the `EnumDMLicenseModule` enumeration items.

**Default Value**

null

## chargeWay

Sets the charge way.

```java
int chargeWay
```

**Value Range**

Any one of the `EnumDMChargeWay` enumeration items.
