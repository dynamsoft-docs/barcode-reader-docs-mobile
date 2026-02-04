---
layout: default-layout
title: UI Configurations - Dynamsoft Barcode Reader for iOS
description: LLearn how to add basic UI elements on the DCECameraView for iOS edition.
keywords: UI Configurations, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: false
---

# UI Configurations

In this article, you will learn:

- How to highlight the decoded barcodes
- How to add clickable torchlight button

## Introduction

UI configurations APIs are all included in the [CameraView]({{site.dce_ios}}auxiliary-api/dcecameraview.html) class. All the UI configurations are implemented via the CameraView instance. You can use the following steps to get prepared for UI configurations. These steps are also mentioned in the [Getting started](../user-guide.md).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
#import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
```
2. 
```swift
import DynamsoftCameraEnhancer
```

## How to Highlight Decoded Barcodes

Turn on/off the highlight overlay:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Get the layer first.
DSDrawingLayer *layer = [self.cameraView getDrawingLayer:DSDrawingLayerIdDBR];
// Set the visible property to true or false to control the visibility.
layer.visible = false;
```
2. 
```swift
// Get the layer first.
layer = cameraView.getDrawingLayer(DrawingLayerId.DLR.rawValue)
// Set the visible property to true or false to control the visibility.
layer.visible = false
```

Set the style of the highlight overlays with a preset style:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Get the layer first.
DSDrawingLayer *layer = [self.cameraView getDrawingLayer:DSDrawingLayerIdDBR];
// Change the style of the layer.
[layer setDefaultStyle:DSDrawingStyleIdBlueStroke];
```
2. 
```swift
// Get the layer first.
layer = cameraView.getDrawingLayer(DrawingLayerId.DLR.rawValue)
// Change the style of the layer.
layer.setDefaultStyle(DrawingStyleId.blueStroke.rawValue)
```

Set the style of the highlight overlays with a use defined style:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Get the layer first.
DSDrawingLayer *layer = [self.cameraView getDrawingLayer:DSDrawingLayerIdDBR];
// Create a new DrawingStyle via the DrawingStyleManager.
NSInteger userDefinedStyle = [DSDrawingStyleManager createDrawingStyle:UIColor.blueColor strokeWidth:2 fillColor:UIColor.blueColor textColor:UIColor.blueColor font:UIFontTextStyleTitle1];
// Set the newly created DrawingStyle to the layer.
[layer setDefaultStyle:userDefinedStyle];
```
2. 
```swift
// Get the layer first.
layer = cameraView.getDrawingLayer(DrawingLayerId.DLR.rawValue)
// Create a new DrawingStyle via the DrawingStyleManager.
let styleID = DrawingStyleManager.createDrawingStyle(UIColor.red, strokeWidth: 1, fill: UIColor.init(red: 255, green: 0, blue: 0, alpha: 0.1), textColor: UIColor.red, font:UIFont.systemFont(ofSize: 1) )
// Set the newly created DrawingStyle to the layer.
layer.setDefaultStyle(styleID)
```

## How to add a clickable Torchlight Button

In the `cameraView`, there is a built-in clickable torch button that can control the status of the torchlight. By invoking the proper API in the `CameraView` class, you can control the parameters such as position, size, icon, and visibility of the button.

To display the torch button:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// If you don't add any styles for the button, the torch will be displayed on the top left corner of the screen.
[self.cameraView setTorchButtonVisible:true];
```
2. 
```swift
// If you don't add any styles for the button, the torch will be displayed on the top left corner of the screen.
cameraView.torchButtonVisible = true
```

`torchOnImage` and `torchOffImage` can define the icon images that are displayed when the torch is on and off, respectively. If you set the position or images to nil value, they will be set to the default value.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// You can change the position, size, and displayed image of the button.
[self.cameraView setTorchButtonWithFrame:CGRectMake(50, 50, 50, 50) torchOnImage:nil torchOffImage:nil];
```
2. 
```swift
// You can change the position, size, and displayed image of the button.
cameraView.setTorchButton(CGRect(x:50, y:50, width:50, height:50), torchOn:nil, torchOffImage:nil)
```
