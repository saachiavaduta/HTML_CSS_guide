# 5. Display, Visibility, Positioning, and Stacking

**Notes to read:** `CSS/15.CSS_Display`, `CSS/17.CSS_Positions`, `HTML/08.Inline_And_Block_Elements`, `CSS/23.CSS_Float`

## display

`display` controls how an element participates in layout.

| Value | Behaviour | Width and height | Questions |
|-------|-----------|------------------|-----------|
| `block` | Starts a new line, fills the width | Applied | Q56, Q71, Q110 |
| `inline` | Sits in the text line, takes only its content width | **Ignored** | Q56, Q71, Q110 |
| `inline-block` | Sits in the line, but accepts width and height | Applied | Q56, Q71, Q110, Q118 |
| `flex` | Makes the element a flex container (file 06) | n/a | Q52, Q55 |
| `none` | Removes the element from layout completely | n/a | Q37, Q73 |

**Why inline ignores height:** inline elements are sized by their text. Vertical padding does draw, but it does not push other lines apart (Q56).

**Why inline-block has spaces between items:** the browser places a space character between inline boxes, so `inline-block` items appear to have a gap (Q110). Removing whitespace in the HTML or using flex avoids this.

## visibility versus display

The display note in the repository covers `display: none` but does not compare it with `visibility`, so this table follows standard CSS behaviour. The note also lists `grid` and `contents` as display values.

| | `visibility: hidden` | `display: none` |
|---|---|---|
| Visible | No | No |
| Takes up space | **Yes** | **No** |
| Can be clicked | No | No |

Q73 shows this: the first box keeps its gap, and the box after the `display: none` element moves up.

## position

`position` controls where an element is placed, using `top`, `right`, `bottom`, `left`.

| Value | Behaviour | Question |
|-------|-----------|----------|
| `static` | Default. Normal flow. Offsets are ignored | Q32, Q53 |
| `relative` | Normal flow and space kept, then shifted by offsets | Q32, Q53, Q79 |
| `absolute` | Removed from flow, placed relative to the nearest positioned ancestor | Q32, Q79, Q97, Q116 |
| `fixed` | Stays in place on the screen while scrolling. Removed from flow | Q65 |
| `sticky` | Acts normal until it hits an offset (for example `top: 0`), then stays, within its parent | Q65 |

### The containing block

An absolutely positioned element is placed relative to its nearest ancestor that has `position` other than `static`. This is the **containing block**.

```css
.parent { position: relative; }   /* the reference point */
.child  { position: absolute; top: 10px; right: 10px; }
```

If no ancestor is positioned, the child uses the page (Q32). Q79 and Q97 both depend on this.

### fixed versus sticky

- `fixed` ignores scrolling. A back-to-top button stays in the corner (Q65).
- `sticky` sticks only while its parent section is on screen. A heading stays at the top of its section and then leaves when the section ends (Q65).

## z-index and stacking

When elements overlap, `z-index` decides which is on top.

```css
.card-a { position: absolute; z-index: 1; }
.card-b { position: absolute; z-index: 2; }   /* appears above card-a */
```

- Higher numbers appear in front (Q8, Q116).
- `z-index` only works on positioned elements, and on flex or grid items (Q8).
- Q97 gives the overlay child `z-index: 10` so it stays above the others.

## float

`float` moves an element to the left or right, and text and inline content wrap around it (`CSS/23.CSS_Float`).

```css
.float-img { float: left; width: 150px; margin-right: 10px; }
.clear     { clear: both; }
```

- `float` values: `none` (default), `left`, `right`. A floated element leaves the normal flow.
- `clear` values: `none`, `left`, `right`, `both`. A cleared element moves below the floats on the chosen side(s).
- When every child of a container is floated, the container can collapse to zero height. `overflow: auto` on the container, or a clearfix (`::after` with `clear: both`), fixes this.
- Flexbox and Grid have mostly replaced `float` for page layout. No question in this paper uses `float`.

## Exam tip

For a question about overlapping or placement, state the containing block first. Then give the offset values and the `z-index` if things overlap.
