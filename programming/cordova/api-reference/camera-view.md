---
layout: default-layout
title: DCVCameraView Class of Dynamsoft Capture Vision Cordova Edition
description: Documentation page of API reference of Dynamsoft Capture Vision DCVCameraView class.
keywords: Camera view, API Reference, Cordova
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: DCVCameraView
---

# Class DCVCameraView

`DCVCameraView` is the class that used to display the view of camera and related UI elements.

```js
class DCVCameraView
```

| Property | Description |
| -------- | ----------- |
| [`bindToHtmlElement`](#bindtohtmlelement) | Bind DCVCameraView to a HTML element. |
| [`setOverlayVisible`](#setoverlayvisible) | A property that indicates whether the `overlays` are visible. |
| [`setTorchButton`](#settorchbutton) | A property that determines whether a torch button will be displayed on the `DCVCameraView` and how the torch button will be displayed. |

## bindToHtmlElement

Bind `DCVCameraView` to a HTML element.

```js
bindToHtmlElement(element:HTMLElement): void;
```

**Parameters**

`element`: A HTML `<div>` for displaying `DCVCameraView`.

**Code Snippet**

Create an HTML element first.

```html
<div id="camera_view" style="width: 100vw; height: 100vh; z-index: -1;">
    <div id="show_result" style="position: fixed; width: 100vw; bottom: 10vh;  text-align:center; color: white; "></div>
</div>
```

Get and bind the HTML element to DCVCameraView

```js
// Get the HTML element.
const cameraViewElement = document.getElementById("camera_view")
// Create an instance of the camera view.
var cameraView = new Dynamsoft.DCVCameraView()
// Bind the camera view instance with the HTML element.
cameraView.bindCameraViewToElement(cameraViewElement)
```

## setOverlayVisible

Set whether to display highlight overlays on the detected significant areas (like barcode areas).

```js
setOverlayVisible(vis:boolean): void;
```

**Parameters**

`vis`: A boolean value that indicates whether the overlays are visible.

**Code Snippet**

```js
cameraView.setOverlayVisible(true)
```

## setTorchButton

Set whether a torch button will be displayed on the `DCVCameraView` and how the torch button will be displayed.

```js
setTorchButton(btn:TorchButton): void;
```

**Parameters**

`btn`: A TorchButton object that contains torch button properties.

**Code Snippet**

You can simply display a torch button on the top-left corner of the view.

```js
cameraView.setTorchButton({
    visible:true
})
```

You can change the size and the position of the torch button.

```js
cameraView.setTorchButton({
    location: {
        x: 100,
        y: 100,
        width: 100,
        height: 100
    },
    visible:true
})
```

You can also change the image of the torch button.

```js
cameraView.setTorchButton({
    location: {
        x: 100,
        y: 100,
        width: 100,
        height: 100
    },
    visible:true,
    torchOnImage: "Put your file path here. This image will be displayed when the torch is on.",
    torchOffImage: "Put your file path here. This image will be displayed when the torch is off."
})
```
