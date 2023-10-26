---
layout: default-layout
title: HelloWorld Sample - Dynamsoft Barcode Reader for iOS
description: This is the HelloWorld Sample page of Dynamsoft Barcode Reader for iOS SDK.
keywords: iOS, samples, HelloWorld
needAutoGenerateSidebar: true
breadcrumbText: HelloWorld
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/samples/helloworld-v9.6.30.html
---

# HelloWorld Sample

The iOS Helloworld sample illustrates how to create the simplest video streaming barcode reading app with Dynamsoft Barcode Reader (DBR) iOS SDK.

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

2. Modify `textResultCallback`. Replace the content of `textResultCallback` with the following code:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)textResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iTextResult *> *)results{
   if (results) {
          NSString *msgText = @"";
          for (NSInteger i = 0; i< [results count]; i++) {
             msgText = [msgText stringByAppendingString:[NSString stringWithFormat:@"\nFormat: %@\nText: %@\n", results[i].barcodeFormatString, results[i].barcodeText]];
          }
          dispatch_async(dispatch_get_main_queue(), ^{
             self.resultView.hidden = false;
             self.resultView.text = msgText;
          });
   }else{
          return;
   }
}
```
2. 
```swift
class ViewController: UIViewController, DBRTextResultListener {
   var resultView:UITextView!
   ...
   // Add code to config the result view.
   func textResultCallback(_ frameId: Int, imageData: iImageData, results: [iTextResult]?) {
          if (results != nil){
             var viewText:String = "\("Total Result(s):") \(results?.count ?? 0)"
             for res in results! {
                viewText = viewText + "\n\("Format:") \(res.barcodeFormatString!) \n\("Text:") \(res.barcodeText ?? "None")\n"
             }
             DispatchQueue.main.async{
                self.resultView.isHidden = false
                self.resultView.text = viewText
             }
          }else{
             return
          }
   }
}
```

Method `textResultCallback` is where you receive the barcode results when using video barcode decoding. It is triggered each time when an image is processed.

For more details about how to get started with Dynamsoft Barcode Reader, please view the [user guide]({{ site.oc }}user-guide.html).
