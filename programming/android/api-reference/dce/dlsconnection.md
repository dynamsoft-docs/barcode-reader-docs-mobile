---
layout: default-layout
title: Android DMDLSConnectionParameters Class - Dynamsoft Camera Enhancer
description: This is the documentation - Android DMDLSConnectionParameters Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android DMDLSConnectionParameters Class
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android DMDLSConnectionParameters Class
---

# DMDLSConnectionParameters

`DMDLSConnectionParameters` is the class that defines a struct to configure the parameters to connect to the Dynamsoft License Server.

```java
class com.dynamsoft.dce.DMDLSConnectionParameters
```

| Attribute Name | Type |
| -------------- | ---- |
| [`mainServerURL`](#mainserverurl) | String |
| [`standbyServerURL`](#standbyserverurl) | String |
| [`handshakeCode`](#handshakecode) | String |
| [`organizationID`](#organizationid) | String |
| [`sessionPassword`](#sessionpassword) | String |
| [`uuidGenerationMethod`](#uuidgenerationmethod) | int |
| [`maxBufferDays`](#maxbufferdays) | int |
| [`limitedLicenseModules`](#limitedlicensemodules) | list |
| [`chargeWay`](#chargeway) | int |
| [`products`](#products) | int |

## mainServerURL

The URL of the Dynamsoft License Server.

**Value Range**

Any string value

**Default Value**

null

**Code Snippet**

```java
dceParameters.mainServerURL = "";
```

**Remarks**

If you choose "Dynamsoft-hosting", then no need to change the value of MainServerURL and StandbyServerURL. When both are set to null (default value), it will connect to Dynamsoft License Servers for online verification.

&nbsp;

## standbyServerURL

The URL of the standby Dynamsoft License Server.

**Value Range**

Any string value

**Default Value**

null

**Code Snippet**

```java
dceParameters.standbyServerURL = "";
```
**Remarks**

If you choose "Dynamsoft-hosting", then no need to change the value of MainServerURL and StandbyServerURL. When both are set to null (default value), it will connect to Dynamsoft License Servers for online verification.

&nbsp;


## handshakeCode

The handshake code.

**Value Range**

Any string value

**Default Value**

null

**Code Snippet**


```java
dceParameters.handshakeCode = "";
```

&nbsp;

## organizationID

The organization ID

**Value Range**

Any string value

**Default Value**

null

**Code Snippet**

```java
dceParameters.organizationID = "";
```

&nbsp;

## sessionPassword

The session password of the handshake code set in Dynamsoft License Server.

**Value Range**

Any string value

**Default Value**

null

**Code Snippet**

```java
dceParameters.sessionPassword = "";
```

&nbsp;

## uuidGenerationMethod

Sets the method to generate UUID.

**Value Range**

Any one of the [`EnumDMUUIDGenerationMethod`]({{ site.dce-enums }}enum-1.html?lang=android#enumcameradmuuidcenerationmethod) Enumeration items.

**Default Value**

DM_UUIDGM_RANDOM

**Code Snippet**


```java
dceParameters.uuidGenerationMethod = EnumCameraDMUUIDGenerationMethod.DM_UUIDGM_RANDOM;
```

**See Also**

[`EnumDMUUIDGenerationMethod`]({{ site.dce-enums }}enum-1.html?lang=android#enumcameradmuuidcenerationmethod)

&nbsp;

## maxBufferDays

Sets the max days to buffer the license info.

**Value Range**

[7,0x7fffffff]  

**Default Value**

7

**Code Snippet**

```java
dceParameters.maxBufferDays = 7;
```

&nbsp;

## chargeWay

Sets the charge way.

**Value Range**

Any one of the [`EnumDMChargeWay`]({{ site.dce-enums }}enum-1.html?lang=android#enumdmchargeway) Enumeration items.

**Default Value**

DM_CW_AUTO

**Code Snippet**

```java
dceParameters.chargeWay = EnumDMChargeWay.DM_CW_DEVICE_COUNT;
```

**See Also**

[`EnumDMChargeWay`]({{ site.dce-enums }}enum-1.html?lang=android#enumdmchargeway)

&nbsp;


## products

Set the products. This is a combined value of Product Enumration items.

**Value Range**

Any one of the [`EnumProduct`]({{ site.dce-enums }}enum-1.html?lang=android#enumproduct) Enumeration items.

**Code Snippet**


```java
dceParameters.products = EnumProduct.PROD_DBR;
```

**See Also**

[`EnumProduct`]({{ site.dce-enums }}enum-1.html?lang=android#enumproduct)
