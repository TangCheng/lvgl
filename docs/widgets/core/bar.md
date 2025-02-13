```eval_rst
.. include:: /header.rst 
:github_url: |github_link_base|/widgets/bar.md
```
# Bar (lv_bar)

## Overview

The bar object has a background and an indicator on it. The width of the indicator is set according to the current value of the bar. 

Vertical bars can be created if the width of the object is smaller than its height.

Not only the end, but the start value of the bar can be set which changes the start position of the indicator.


## Parts and Styles
- `LV_PART_MAIN` The background of the bar and it uses the typical background style properties. Adding padding makes the indicator smaller or larger. The `anim_time` style property sets the animation time if the values set with `LV_ANIM_ON`.
- `LV_PART_INDICATOR` The indicator and it also also uses all the typical background properties.
 
## Usage

### Value and range
A new value can be set by `lv_bar_set_value(bar, new_value, LV_ANIM_ON/OFF)`.
The value is interpreted in a range (minimum and maximum values) which can be modified with `lv_bar_set_range(bar, min, max)`.
The default range is 1..100.

The new value in `lv_bar_set_value` can be set with or without an animation depending on the last parameter (`LV_ANIM_ON/OFF`).

### Modes
The bar can be one the following modes:
- `LV_BAR_MODE_NORMAL` A normal bar as described above
- `LV_BAR_SYMMETRICAL` Draw the indicator form the zero value to current value. Requires negaitve minimum range and positive maximum range.
- `LV_BAR_RANGE` Allows setting the setar value too by `lv_bar_set_start_value(bar, new_value, LV_ANIM_ON/OFF)`. The start value has to be always smaller than the end value.

## Events
- `LV_EVENT_DRAW_PART_BEGIN` and `LV_EVENT_DRAW_PART_END` are sent for both main and indicator parts to allow hooking the drawing. 
The for more detail on the main part see the [Base object](/widgets/obj#events)'s documentation.
For the indicator the following fields are used: `clip_area`, `draw_area`, `rect_dsc`, `part`. 

Learn more about [Events](/overview/event).

## Keys
No *Keys* are processed by the object type.

Learn more about [Keys](/overview/indev).

## Example

```eval_rst

.. include:: ../../../examples/widgets/bar/index.rst

```

## API

```eval_rst

.. doxygenfile:: lv_bar.h
  :project: lvgl

```
