---
layout: default-layout
title: Interface Region - Dynamsoft Capture Vision React Native Edition
description: The interface region of Dynamsoft Capture Vision React Native edition.
keywords: Interface Region, API reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Region
---

# Region

Interface `Region`.

```js
export interface Region {
    /**
     * The y coordinate of the Top border of the region.
     */
    regionTop: number;
    /**
     * The y coordinate of the Bottom border of the region.
     */
    regionBottom: number;
    /**
     * The x coordinate of the left border of the region.
     */
    regionLeft: number;
    /**
     * The x coordinate of the right border of the region.
     */
    regionRight: number;
    /**
     * If measured by percentage, the above values will be recognized as percentage (1 to 100).
     * Otherwise, the above values will be recognized as pixel length.
     */
    regionMeasuredByPercentage: number | boolean;
}
```
