# 3. CSS Basics and the Box Model

**Notes to read:** `CSS/01.Introduction_to_CSS`, `CSS/05.CSS_Border`, `CSS/06.CSS_Background`, `CSS/07.CSS_Margin_Padding`, `CSS/08.CSS_Width_Height`, `CSS/09.CSS_Box_Model`, `CSS/11.CSS_Text`, `CSS/12.CSS_Fonts`, `CSS/09.CSS_Outline`

## Rule syntax

```css
selector {
  property: value;
}
```

A **rule** is a selector plus declarations. A declaration is a property and a value. Each declaration ends with a semicolon.

## The box model

Every element is a rectangle made of four layers, from inside out:

1. **Content**: the text or image.
2. **Padding**: space between the content and the border. It takes the element's background colour (Q10, Q28).
3. **Border**: the line around the padding.
4. **Margin**: space outside the border. It is transparent and separates the element from its neighbours (Q28, Q33).

```css
.box {
  width: 200px;
  padding: 20px;
  border: 2px solid navy;
  margin: 10px;
}
```

### Shorthand for padding and margin

`margin` and `padding` take 1 to 4 values, read clockwise from the top:

- 1 value: all four sides.
- 2 values: top/bottom, then left/right.
- 3 values: top, left/right, bottom.
- 4 values: top, right, bottom, left.

### Padding versus margin

| | Padding | Margin |
|---|---|---|
| Position | Inside the border | Outside the border |
| Background | Painted | Transparent |
| Collapses between siblings | No | Yes (vertical margins can merge) |

When two vertical margins meet, the larger one wins. A `margin-bottom: 20px` above a `margin-top: 30px` gives 30px of space, not 50px.

### How much space a box takes

With the default `content-box`, the total width is:

`width + left padding + right padding + left border + right border + left margin + right margin`

The total is larger than the `width` you typed. Q95 shows this with visible borders.

### box-sizing

```css
* { box-sizing: border-box; }
```

With `border-box`, the `width` includes padding and border, so the box stays the size you set. Most modern stylesheets use this, and Q120 applies it to every element.

## Borders and rounded corners

```css
.card {
  border: 2px solid #333;
  border-radius: 10px;
}
```

- `border` sets width, style, and colour in one line.
- `border-radius` rounds the corners (Q15). `50%` on a square image makes a circle (Q54, Q91).
- Styles include `solid`, `dashed`, `dotted`, `double`, `groove`, `ridge`, `inset`, `outset`, `none`, and `hidden` (Q118).
- The repository's border note does not cover `border-radius`, so the rounded-corner rules above are standard CSS.

## Backgrounds

- `background-color` sets a flat colour (Q72).
- `background-image: linear-gradient(...)` makes a gradient (Q118).
- `background-image: url(...)` with `background-size: cover` and `background-position: center` fills a box with a photo (Q118). `background-size: contain` fits the whole image inside the box without cropping it.

## Shadows

```css
box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
```

The values are horizontal offset, vertical offset, blur, and colour. `box-shadow` adds shadow around the box (Q23, Q82). `text-shadow` is different and applies only to text.

## Text and fonts

| Property | Effect | Questions |
|----------|--------|-----------|
| `font-family` | Typeface. List fallbacks, such as `Arial, sans-serif` | Q60, Q91 |
| `font-size` | Text size | Q60, Q72 |
| `font-weight` | Thickness, such as `bold` | Q60 |
| `line-height` | Vertical space between lines. Unitless values like `1.6` scale with font size | Q60, Q72 |
| `letter-spacing` | Space between letters | Q72 |
| `text-align` | `left`, `center`, `right`, `justify` | Q60 |
| `text-decoration` | `underline` or `none` (removes link underline) | Q53, Q60, Q84 |
| `color` | Text colour | Q48, Q72 |
| `text-transform` | `uppercase`, `lowercase`, `capitalize` | — |
| `word-spacing` | Space between words | — |

### Font fallbacks and web fonts

- `font-family` takes a comma-separated list. The browser tries each font in order and uses the generic family at the end (`sans-serif`, `serif`) if none is available. Font names with spaces need quotes, as in `'Times New Roman'`.
- `font-style` takes `normal`, `italic`, or `oblique`.
- Google Fonts are free web fonts. They need a `<link>` tag or an `@import` in CSS, plus an internet connection to load.

## Outline versus border

`outline` is drawn outside the border and does not take up space (Q10). It is often used on `:focus` so keyboard users can see where they are (Q84, Q103).

## Width, height, and limits

```css
.content-box {
  width: 50%;
  min-width: 250px;
  max-width: 500px;
  min-height: 100px;
  max-height: 200px;
}
```

- `min-*` sets the smallest size an element can reach.
- `max-*` sets the largest. `max-width` overrides `width` when the element would otherwise be wider, and it does not accept negative values.
- `width` in percent refers to the parent's width (Q76, Q80).
- `width` and `height` apply to block and inline-block elements. Inline elements ignore both.
- A percentage `height` works only when the parent has an explicit height.
- `height: auto` (the default) sizes the element to its content.

## Overflow

When content is bigger than its box, `overflow` decides what happens:

| Value | Behaviour | Question |
|-------|-----------|----------|
| `visible` | Default. Content spills out | Q24 |
| `hidden` | Clipped, no scrollbar | Q87, Q105 |
| `auto` | Scrollbar only when needed | Q87, Q105 |
| `scroll` | Scrollbars always shown | Q87, Q105 |

## Exam tip

When a question asks for the box model, name all four layers in order from inside out, and show padding and margin with different colours or values so the difference is visible.
