---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Barcode Reader Android Edition
description: The DecodedBarcodesResult class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, DecodedBarcodesResult, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodesResult
permalink: /programming/android/api-reference/decoded-barcodes-result.html
---

# DecodedBarcodesResult Class

The `DecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

```cpp
class DecodedBarcodesResult
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`GetOriginalImageHashId`](#getoriginalimagehashid) | Gets the hash ID of the source image. |
| [`GetOriginalImageTag`](#getoriginalimagetag) | Gets the tag of the source image. |
| [`GetItemsCount`](#getitemscount) | Gets the number of barcode result items in the barcode reading result. |
| [`GetItem`](#getitem) | Gets the barcode result item at the specified index. |
| [`HasItem`](#hasitem) | Check if the barcode result item is present in the array.|
| [`RemoveItem`](#removeitem) | Remove a specific barcode result item from the result array.|
| [`GetRotationTransformMatrix`](#getrotationtransformmatrix) | Get the rotation transformation matrix of the original image relative to the rotated image.|
| [`GetErrorCode`](#geterrorcode) | Gets the error code of the barcode reading result, if an error occurred. |
| [`GetErrorString`](#geterrorstring) | Gets the error message of the barcode reading result, if an error occurred. |

### GetOriginalImageHashId

Gets the hash ID of the source image.

```cpp
virtual const char* GetOriginalImageHashId() const = 0;
```

**Return value**

Returns a pointer to a null-terminated string containing the hash ID of the source image.

### GetOriginalImageTag

Gets the tag of the source image.

```cpp
virtual const CImageTag* GetOriginalImageTag() const = 0;
```

**Return value**

Returns a pointer to a CImageTag object representing the tag of the source image.

**See Also**

[CImageTag]({{ site.dcv_android_api }}core/basic-structures/image-tag.html)

### GetItemsCount

Gets the number of decoded barcode items in the barcode reading result.

```cpp
virtual int GetItemsCount() const = 0;
```

**Return value**

Returns the number of decoded barcode items in the barcode reading result.

### GetItem

Gets the decoded barcode result item at the specified index.

```cpp
virtual const CBarcodeResultItem* GetItem(int index) const = 0;
```

**Parameters**

`[in] index` The zero-based index of the barcode result item to retrieve.

**Return value**

Returns a pointer to the CBarcodeResultItem object at the specified index.

**See Also**

[CBarcodeResultItem]({{ site.android_api }}barcode-result-item.html)

### HasItem

Check if the barcode result item is present in the array.

```cpp
bool HasItem(const CBarcodeResultItem* item) const
```

**Parameters**

`[in] item` The specific item to check.

**Return value**

Returns a bool value indicating whether the item is present in the array or not.

**See Also**

[CBarcodeResultItem]({{ site.android_api }}barcode-result-item.html)

### RemoveItem

Remove a specific barcode result item from the result array.

```cpp
int RemoveItem(const CBarcodeResultItem* item)
```

**Parameters**

`[in] item` The specific item to remove.

**Return value**

Return value indicating whether the deletion was successful or not.

**See Also**

[CBarcodeResultItem]({{ site.android_api }}barcode-result-item.html)

### GetRotationTransformMatrix

Get the rotation transformation matrix of the original image relative to the rotated image.

```cpp
void GetRotationTransformMatrix(double matrix[9]) const;
```

**Parameters**

`[out] matrix` A double array which represents the rotation transform matrix.

### GetErrorCode

Gets the error code of the barcode reading result, if an error occurred.

```cpp
virtual int GetErrorCode() const = 0;
```

**Return value**

Returns the error code of the barcode reading result, or 0 if no error occurred.

**See Also**

[Enumeration ErrorCode]({{ site.dcv_enumerations }}core/error-code.html?lang=android)

### GetErrorString

Gets the error message of the barcode reading result, if an error occurred.

```cpp
virtual const char* GetErrorString() const = 0;
```

**Return value**

Returns a pointer to a null-terminated string containing the error message of the barcode reading result, or a pointer to an empty string if no error occurred.
