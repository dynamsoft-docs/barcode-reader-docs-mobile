---
layout: default-layout
title: HelloWorld Sample - Dynamsoft Barcode Reader for iOS
description: This is the HelloWorld Sample page of Dynamsoft Barcode Reader for iOS SDK.
keywords: iOS, samples, HelloWorld
needAutoGenerateSidebar: true
breadcrumbText: HelloWorld
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/samples/helloworld.html
---

# Decode from Video Sample - Use DynamsoftCameraEnhancer as Image Source

This sample illustrates how to recognize barcode from the video streaming. In this sample, you can read how to use DynamsoftCameraEnhancer to capture the video streaming.

View the samples

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/HelloWorldObjC/" target="_blank">Objective-C HelloWorld</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Swift/HelloWorldSwift/" target="_blank">Swift HelloWorld</a>

## How to Switch between One-off Scan & Continuous Scan

The default scan mode of the helloWorld sample is one-off scan. Here shows the sample code for you to switch the scan mode to continuous scan.

1. Add a result view to display the barcode result(s).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, strong) UITextView *resultView;
- (void)viewDidLoad {
   ...
   [self addResultView];
}
- (void)addResultView{
   CGFloat viewHeight = 300;
   _resultView = [[UITextView alloc] initWithFrame:CGRectMake(0, UIScreen.mainScreen.bounds.size.height - viewHeight, self.view.frame.size.width, self.view.frame.size.height)];
   _resultView.layer.borderColor = UIColor.whiteColor.CGColor;
   _resultView.layer.borderWidth = 1.0;
   _resultView.layer.cornerRadius = 12.0;
   _resultView.layer.backgroundColor = UIColor.clearColor.CGColor;
   _resultView.layoutManager.allowsNonContiguousLayout = false;
   _resultView.editable = false;
   _resultView.selectable = false;
   _resultView.textColor = UIColor.whiteColor;
   _resultView.textAlignment = NSTextAlignmentCenter;
   _resultView.hidden = false;
   [self.view addSubview:_resultView];
}
```
2. 
```swift
class ViewController: UIViewController, DBRTextResultListener {
   var resultView:UITextView!
   ...
   // Add code to config the result view.
   func addResultView(){
          let viewHeight:CGFloat = 300
          resultView = UITextView(frame: CGRect(x: 0, y: mainHeight  - SafeAreaBottomHeight - viewHeight , width: self.view.frame.width, height: viewHeight ))
          resultView.layer.borderColor = UIColor.white.cgColor
          resultView.layer.borderWidth = 1.0
          resultView.layer.cornerRadius = 12.0
          resultView.layer.backgroundColor = UIColor.clear.cgColor
          resultView.layoutManager.allowsNonContiguousLayout = false
          resultView.isEditable = false
          resultView.isSelectable = false
          resultView.font = UIFont.systemFont(ofSize: 16, weight: .medium)
          resultView.textColor = UIColor.white
          resultView.textAlignment = .center
          resultView.isHidden = true
          self.view.addSubview(resultView)
   }
}
```

2. Modify the `onDecodedBarcodeReceived` method. Replace the content of `onDecodedBarcodeReceived` with the following code:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)onDecodedBarcodesReceived:(DSDecodedBarcodesResult *)result {
   if (result.items.count > 0) {
          NSString *message = @"";
          for (DSBarcodeResultItem *item in result.items) {
             message = [NSString stringByAppendingString:@"\nFormat: %@\nText: %@\n", item.formatString, item.text];
          }
          dispatch_async(dispatch_get_main_queue(), ^{
             self.resultView.hidden = false;
             self.resultView.text = message;
          });
   }else{
          return;
   }
}
```
2. 
```swift
class ViewController: UIViewController, DBRTextResultListener {
   ...
   func onDecodedBarcodesReceived(_ result: DecodedBarcodesResult) {
      if let items = result.items, items.count > 0 {
         DispatchQueue.main.async {
            self.cvr.stopCapturing()
         }
         var message = ""
         for item in items {
            message = message + String(format:"\nFormat: %@\nText: %@\n", item.formatString, item.text)
         }
         DispatchQueue.main.async{
            self.resultView.isHidden = false
            self.resultView.text = message
         }
      }
   }
}
```

Method `textResultCallback` is where you receive the barcode results when using video barcode decoding. It is triggered each time when an image is processed.

For more details about how to get started with Dynamsoft Barcode Reader, please view the [user guide]({{ site.oc }}user-guide.html).
