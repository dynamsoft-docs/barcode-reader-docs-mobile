---
layout: default-layout
title: Camera View Class - Dynamsoft Capture Vision React Native Edition
description: This page is the API reference of Camera View class
keywords: Camera view, API reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Camera View class
---

# DCVCameraView Class

The UI component of Dynamsoft Capture Vision. It provides the following functions:

- Implement basic camera control like open, close, etc.
- Define the scan area where barcode reading is performed.
- Display the video preview, overlay, scan region etc.

| Property | Description |
| ------- | ----------- |
| [`scanRegion`](#scanregion) | The property for users to specify the region of interest. |
| [`scanRegionVisible`](#scanregionvisible) | A property that determines whether the [`scanRegion`](#scanregion) is visible. |
| [`overlayVisible`](#overlayvisible) | A property that indicates whether the `overlays` are visible. |
| [`torchState`](#torchstate) | The property that indicates the state of the torch light. |
| [`torchButton`](#torchbutton) | The property that defines how the torch button will be displayed. |
| [`cameraPosition`](#cameraposition) | The property for selecting front-facing or back-facing camera. |

## scanRegion

The property for users to specify the region of interest.

```js
scanRegion: Region;
```

**Code Snippet**

```jsx
render() {
    let region = {
        regionTop: 0,
        regionLeft: 10,
        regionBottom: 55,
        regionRight: 80,
        regionMeasuredByPercentage: true
    }
    return (
        <DCVCameraView
            style={{
                flex: 1
            }}
            ref = {(ref)=>{this.scanner = ref}}
            overlayVisible={true}
            scanRegionVisible={true}
            scanRegion={region}
        >
        </DCVCameraView>
    );
}
```

## scanRegionVisible

A property that defines whether the [`scanRegion`](#scanregion) is visible.

```js
scanRegionVisible: boolean;
```

**Code Snippet**

View code snippet in the [`scanRegion`](#scanregion) section.

## overlayVisible

A property that indicates whether the `overlays` are visible.

```js
overlayVisible: boolean;
```

**Code Snippet**

View code snippet in the [`scanRegion`](#scanregion) section.

## torchState

The property that indicates whether the torch (flash) is toggled on or off. It can be set via string or one of the [EnumTorchState](enum-torch-state.md) options.

```js
torchState: string | EnumTorchState;
```

**Code Snippet**

```js
// The following data can be assigned to the torchState
torchState={EnumTorchState.OFF}
torchState={EnumTorchState.ON}
torchState={0}
torchState={1}
torchState={"off"}
torchState={"on"}
```

## torchButton

The property that defines how the torch button will be displayed. The torch button can be displayed on the UI to control the state of torch light. View [interface TorchButton](interface-torch-button.md) to see all available properties for torch button configuration.

```js
torchButton: TorchButton;
```

**Code Snippet**

```js
let rect = {
    x:100,
    y:100,
    width:100,
    height:100
}
...
torchButton={
    {
        location: rect,
        visible: true,
        //When the flashlight is on, the button will appear as this image.
        torchOnImageBase64: "Put Your Base64 String Here",
        //When the flashlight is off, the button will appear as this image.
        torchOffImageBase64: "Put Your Base64 String Here"
    }
}
```

## cameraPosition

The property for selecting front-facing or back-facing camera. It can be set via one of the [EnumCameraPosition](enum-camera-position.md) options.

```js
cameraPosition: EnumCameraPosition;
```

**Code Snippet**

```js
// The following data can be assigned to the torchState
cameraPosition={EnumCameraPosition.CP_BACK}
cameraPosition={EnumCameraPosition.CP_FRONT}
```
