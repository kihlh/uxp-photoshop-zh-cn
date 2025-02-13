---
id: "solidcolor"
title: "SolidColor"
sidebar_label: "SolidColor"
repo: "uxp-photoshop"
product: "photoshop"
keywords:
  - Creative Cloud
  - API Documentation
  - UXP
  - Plugins
  - JavaScript
  - ExtendScript
  - SDK
  - C++
  - Scripting
---

# Solid Color

Represents a color, and allows for mapping into all available Photoshop color models.

When a property is accessed (either via read or write), the current color model
of the SolidColor objects gets set to the space of the accessor. Photoshop internally
converts the color across these color spaces using the Color Settings set by the user.

For example, to set the foreground color to red:

```javascript
const red = new SolidColor();
red.rgb.red = 255;
red.rgb.green = 0;
red.rgb.blue = 0;

app.foregroundColor = red;
```

To understand how color models change as you interact with a SolidColor object,
please see example below:

```javascript
const c = new SolidColor();
console.log(c.model); // By default, this will be ColorModel.RGB

c.cmyk.cyan = 50; // Photoshop will convert the color to CMYK using Edit > Color Settings data
console.log(c.model); // Now, the model will be ColorModel.CMYK

c.rgb.green = 128; // Model will change back to ColorModel.RGB
```

## Properties

| 名称 | 类型 | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| cmyk | [*CMYKColor*](/ps_reference/colors/cmykcolor/) | R W | 23.0 | The color&#x27;s representation in CMYK color space. |
| gray | [*GrayColor*](/ps_reference/colors/graycolor/) | R W | 23.0 | The color&#x27;s representation in grayscale. |
| hsb | [*HSBColor*](/ps_reference/colors/hsbcolor/) | R W | 23.0 | The color&#x27;s representation in HSB color space. |
| lab | [*LabColor*](/ps_reference/colors/labcolor/) | R W | 23.0 | The color&#x27;s representation in LAB color space. |
| nearestWebColor | [*RGBColor*](/ps_reference/colors/rgbcolor/) | R | 23.0 | The color&#x27;s nearest match within the 216 web-safe colors. |
| rgb | [*RGBColor*](/ps_reference/colors/rgbcolor/) | R W | 23.0 | The color&#x27;s representation in RGB color space. |

## Methods

### isEqual
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.0</span>

*boolean*

True if the SolidColor object is visually equivalent to the specified color.

Both colors are converted to Lab colorspace,
and the sum of their normalized squared Euclidian
distance in each space is averaged across the three
then compared to a small constant (3.5e-6).

Due to differences in coverage by various color spaces and clamping,
a color that is converted from RGB to CMYK and back may not be visually equal.

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `color` | [*SolidColor*](/ps_reference/classes/solidcolor/) |
