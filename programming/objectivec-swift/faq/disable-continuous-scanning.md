---
layout: default-layout
title: How do I disable the continuous barcode scanning feature and close the scanner view?
keywords: Dynamsoft Barcode Reader, FAQ, Mobile, tech basic, ios, continuous scanning, disable
description: How do I disable the continuous barcode scanning feature and close the scanner view?
needAutoGenerateSidebar: false
---

## How do I disable the continuous barcode scanning feature and close the scanner view? 

[<< Back to FAQ index](index.md)

In a video scenario, the SDK scans continuously by default. In order to stop the scanning process, please call [`stopScanning`](../api-reference/primary-video.md#stopscanning) to stop barcode scanning, whether manually on the click of a button or automatically e.g. once a barcode is found.

Please note that `stopScanning` will only stop the barcode reader from picking up any more barcodes, but the *video will still be on*. In order to fully close the video view as well, the [`close`](https://www.dynamsoft.com/camera-enhancer/docs/programming/ios/primary-api/camera-enhancer.html?ver=latest#close) method will need to be called on the `dce` object.

The next section will show some quick code snippets to help with this. Please note that these snippets are in Swift only at the moment:

```swift
/* Let's say that you want to close the scanner on the toggle of a button in the HelloWorld sample. */
/* The first step would be to add a button to close the scanner via the storyboard. */
/* After that, a function must be attached to the button, so let's define it here */
@IBAction func closetheScanner(){
    barcodeReader.stopScanning()
    dce.close()
    self.view.subviews.forEach({ $0.removeFromSuperview() }) // this is called to ensure that no still frames are left hanging after the close method is called
}

/* Now to add a button to open the scanner again once it's closed */
@IBAction func resumeTheScanner(){
    self.view.addSubview(dceView) // dceView is defined earlier in the code - please see the HelloWorld sample/code
    configurationDCE() // this function is from our HelloWorld code and contains all the DCE initialization steps
}
```

If you encounter any issues with this feature, please contact the Dynamsoft support team for help.