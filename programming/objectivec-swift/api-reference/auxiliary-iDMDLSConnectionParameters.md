---
layout: default-layout
title: iDMDLSConnectionParameters Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iDMDLSConnectionParameters Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iDMDLSConnectionParameters, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 8.6
ignore: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iDMDLSConnectionParameters.html
---


# Class iDMDLSConnectionParameters

> Note:
>
> - This class is deprecated in version 9.0.
> - Please use [`initLicense`](primary-license.html#initlicense) to activate the license for v9.0+ versions.

Defines a struct to configure the parameters to connect to the license server.  

```objc
@interface iDMDLSConnectionParameters
```

| Attribute | Type | Descriptions |
|---------- | ---- | ------------ |
| [`mainServerURL`](#mainserverurl) | *NSString\** | The URL of the Dynamsoft License Server. |
| [`standbyServerURL`](#standbyserverurl) | *NSString\** | The URL of the standby Dynamsoft License Server. |
| [`handshakeCode`](#handshakecode) | *NSString\** | The handshake code. |
| [`sessionPassword`](#sessionpassword) | *NSString\** | The session password of the handshake code set in Dynamsoft License Server. |
| [`chargeWay`](#chargeway) | *EnumDMChargeWay* | Sets the charge way. |
| [`UUIDGenerationMethod`](#uuidgenerationmethod) | *EnumDMUUIDGenerationMethod* | Sets the method to generate UUID. |
| [`maxBufferDays`](#maxbufferdays) | *NSInteger* | Sets the max days to buffer the license info. |
| [`limitedLicenseModules`](#limitedlicensemodules) | *NSArray\** | Sets the license modules to use. |
| [`organizationID`](#organizationid) | *NSString\** | The organization ID got from Dynamsoft. |

## mainServerURL

The URL of the Dynamsoft License Server.

```objc
NSString* mainServerURL
```

**Value Range**

Any string value

**Default Value**

nil

**Remarks**

If you choose "Dynamsoft-hosting", then no need to change the value of MainServerURL and StandbyServerURL. When both are set to nil (default value), it will connect to Dynamsoft's Dynamsoft License Servers for online verification.

## standbyServerURL

The URL of the standby Dynamsoft License Server.

```objc
NSString* standbyServerURL
```

**Value Range**

Any string value

**Default Value**

nil

**Remarks**

If you choose "Dynamsoft-hosting", then no need to change the value of MainServerURL and StandbyServerURL. When both are set to nil (default value), it will connect to Dynamsoft's Dynamsoft License Servers for online verification.

## handshakeCode

The handshake code.

```objc
NSString* handshakeCode
```

**Value Range**

Any string value

**Default Value**

nil

## sessionPassword

The session password of the handshake code set in Dynamsoft License Server.

```objc
NSString* sessionPassword
```

**Value Range**

Any string value

**Default Value**

nil

## chargeWay

Sets the charge way.

```objc
EnumDMChargeWay chargeWay
```

**Value Range**

Any one of the `EnumDMChargeWay` enumeration items.

**Default Value**

EnumDMChargeWayAuto

## UUIDGenerationMethod

Sets the method to generate UUID.

```objc
EnumDMUUIDGenerationMethod UUIDGenerationMethod
```

**Value Range**

Any one of the `EnumDMUUIDGenerationMethod` enumeration items.

**Default Value**

EnumDMUUIDGenerationMethodRandom

## maxBufferDays

Sets the max days to buffer the license info.

```objc
NSInteger maxBufferDays
```

**Value Range**

[7,0x7fffffff]

**Default Value**

7

## limitedLicenseModules

Sets the license modules to use.

```objc
NSArray* limitedLicenseModules
```

**Value Range**

Each array item can be any one of the `EnumDMLicenseModule` enumeration items.

**Default Value**

nil

## organizationID

The organization ID got from Dynamsoft.

```objc
NSString* organizationID
```

**Value Range**

Any string value

**Default Value**

""
