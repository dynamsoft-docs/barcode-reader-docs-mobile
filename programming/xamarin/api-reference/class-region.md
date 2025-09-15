---
layout: default-layout
title: Class Region of Dynamsoft Capture Vision Xamarin Edition
description: The Class of region
keywords: Class Region, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Region
---

# Region

Class `Region`.

```c#
namespace DCVXamarin
{
    public class Region
    {
        // The y coordinate of the Top border of the region.
        public int RegionTop;

        // The y coordinate of the Bottom border of the region.
        public int RegionBottom;

        // The x coordinate of the left border of the region.
        public int RegionLeft;

        // The x coordinate of the right border of the region.
        public int RegionRight;

        // If measured by percentage, the above values will be recognized as percentage (1 to 100).
        // Otherwise, the above values will be recognized as pixel length.
        public int RegionMeasuredByPercentage;
    }
}
```

## Related API(s)

- [`IDCVCameraEnhancer.ScanRegion`](camera-enhancer.md#scanregion)
