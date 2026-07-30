---
layout: default-layout
title: Parse Drivers' License - Dynamsoft Barcode Reader Android
description: Learn how to parse Drivers' License with Dynamsoft Barcode Reader Android.
keywords: parse, Android, Drivers' License
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Parse Drivers License

## How to Enable Drivers License Parsing

1. Add code parser task.

   ```json
   "CodeParserTaskSettingOptions": [
     {
       "Name": "parse-drivers-license",
       "CodeSpecifications": [
         "AAMVA_DL_ID",
         "AAMVA_DL_ID_WITH_MAG_STRIPE",
         "SOUTH_AFRICA_DL"
       ]
     },
   ]
   ```

2. Add semantic processing options and specify the target ROI to reference.

   ```json
   "SemanticProcessingOptions": [
     {
       "Name": "sp-drivers-license",
       "ReferenceObjectFilter": {
         "ReferenceTargetROIDefNameArray": [
           "roi-drivers-license"
         ]
       },
       "TaskSettingNameArray": [
         "parse-drivers-license"
       ]
     },
   ]
   ```

3. Add the semantic processing option names to your template.

   ```json
   "CaptureVisionTemplates": [
     {
       "Name": "ReadDriversLicense",
       "ImageROIProcessingNameArray": [
         "roi-drivers-license"
       ],
       "SemanticProcessingNameArray": [
         "sp-drivers-license"
       ]
     }
   ]
   ```

## How to Receive Parsed Results

Receive the `ParsedResult` from the [`onParsedResultsReceived`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html) callback of `CapturedResultReceiver`.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
mRouter.addResultReceiver(new CapturedResultReceiver() {
   @Override
   public void onParsedResultsReceived(@NonNull ParsedResult result) {
          // Add your code to use the ParsedResult
   }
});
```
2. 
```kotlin
cvr.addResultReceiver(object: CapturedResultReceiver{
   override fun onParsedResultsReceived(result: ParsedResult) {
          // Add your code to use the ParsedResult
   }
})
```

You can also receive the `ParsedResult` from the [`onCapturedResultReceived`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html) callback if you want to use the barcode result as well.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
mRouter.addResultReceiver(new CapturedResultReceiver() {
   @Override
   public void onCapturedResultReceived(@NonNull CapturedResult result) {
          DecodedBarcodesResult decodedBarcodesResult = result.getDecodedBarcodesResult();
          ParsedResult parsedResult = result.getParsedResult();
   }
});
```
2. 
```kotlin
cvr.addResultReceiver(object: CapturedResultReceiver{
   override fun onCapturedResultReceived(result: CapturedResult) {
          val parsedResult = result.parsedResult
          val decodedBarcodesResult = result.decodedBarcodesResult
   }
})
```

## Common Fields

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value "AAMVA_DL_ID" |
| AAMVAVersionNumber | AAMVA Version Number |
| fullName | Full name of cardholder |
| lastName | Last name of cardholder |
| givenName | Given name of cardholder |
| firstName | First name of cardholder |
| middleName | Middle name of cardholder |
| street_1 | Street portion of the cardholder address |
| street_2 | Second line of street portion of the cardholder address |
| city | City portion of the cardholder address |
| postalCode | Postal code portion of the cardholder address |
| licenseNumber | License/ID Number |
| vehicleClass | Jurisdiction-specific vehicle class / Driver License Classification Code |
| expirationDate | Expiration Date |
| birthDate | Date of Birth |
| sex | Sex |
| issuedDate | Date on which the document was issued |

View more [Drivers License fields]({{ site.code_types }}aamva-dl-id.html).
