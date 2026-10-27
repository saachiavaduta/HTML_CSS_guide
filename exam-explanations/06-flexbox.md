# 6. Flexbox and Grid

**Notes to read:** `CSS/32.CSS_Flex`, `CSS/33.CSS_Grid`

## The big idea

Flexbox arranges items in a line, either horizontal or vertical. You make the parent a **flex container** with `display: flex`. Its direct children become **flex items**.

```css
.row {
  display: flex;
  gap: 16px;
}
```

Without any other rule, the items sit in a row, left to right.

## Two axes

- **Main axis** runs in the direction of `flex-direction`.
- **Cross axis** runs perpendicular to it.

| `flex-direction` | Main axis | Cross axis |
|------------------|-----------|------------|
| `row` (default) | Horizontal | Vertical |
| `column` | Vertical | Horizontal |

This matters because `justify-content` always acts on the main axis, and `align-items` always acts on the cross axis (Q1, Q44).

## Container properties

| Property | Controls | Values | Questions |
|----------|----------|--------|-----------|
| `flex-direction` | Main axis direction | `row`, `column` | Q44, Q55, Q96 |
| `flex-wrap` | Whether items wrap onto new lines | `nowrap` (default), `wrap` | Q45, Q52, Q62, Q94 |
| `justify-content` | Spacing along the main axis | `flex-start`, `center`, `flex-end`, `space-between`, `space-around`, `space-evenly` | Q1, Q86, Q104 |
| `align-items` | Alignment on the cross axis | `flex-start`, `center`, `flex-end`, `stretch` | Q74, Q104 |
| `gap` | Space between items | Any length | Q52, Q62, Q104 |

### justify-content values

- `flex-start`: items packed to the start.
- `center`: packed to the middle.
- `flex-end`: packed to the end.
- `space-between`: first and last touch the edges, equal space between.
- `space-around`: equal space around each item, so edge gaps are half of the middle gaps.
- `space-evenly`: every gap is the same, including the edges.

Q86 has a container for each value so you can compare them side by side.

### align-items values

- `flex-start`: tops aligned.
- `center`: vertically centred.
- `flex-end`: bottoms aligned.
- `stretch` (default): items fill the cross size if they have no fixed height (Q74).

Q113 uses `justify-content: center` and `align-items: center` together to centre a card on the page.

## Item properties

These control each item's size.

### flex-basis

The starting size of the item before space is shared out (Q78).

```css
.one { flex-basis: 100px; }
```

### flex-grow

How much of **extra** space an item takes, compared with its siblings (Q18, Q43, Q112).

```css
.a { flex-grow: 1; }
.b { flex-grow: 2; }   /* takes twice the extra space of .a */
```

### flex-shrink

How much an item gives up when the container is **too small** (Q13, Q43, Q67).

```css
.a { flex-shrink: 0; }   /* never shrinks */
.c { flex-shrink: 3; }   /* shrinks most */
```

Shrinking is weighted by the item's basis, so a larger item gives up more space.

### flex

The shorthand `flex: 1` means `flex-grow: 1; flex-shrink: 1; flex-basis: 0%` (the note's `1 1 0%`). It gives equal-width items, which is why many card rows use it (Q55, Q69, Q82).

### Defaults

| Property | Default |
|---|---|
| `flex-direction` | `row` |
| `flex-wrap` | `nowrap` |
| `justify-content` | `flex-start` |
| `align-items` | `stretch` |
| `flex-grow` | `0` |
| `flex-shrink` | `1` |
| `flex-basis` | `auto` |
| `order` | `0` |

## Other properties in the note

- `order`: changes visual order. Lower numbers come first, so `order: -1` moves an item to the front.
- `align-self`: overrides `align-items` for one item. Its default `auto` inherits `align-items`.
- `align-content`: aligns the lines of a wrapped container on the cross axis. It has no visible effect on a single line.
- `flex-flow`: shorthand for `flex-direction` and `flex-wrap`, for example `flex-flow: row wrap`.

## How the three item properties work together (Q112)

1. `flex-basis` sets the starting size.
2. If there is leftover space, `flex-grow` shares it.
3. If there is not enough space, `flex-shrink` removes it.

## Wrapping

With `flex-wrap: wrap`, items move to a new line when they do not fit (Q45, Q52). Combine with `gap` for even spacing. Percentage widths such as `width: 30%` on each card make the wrap predictable.

## CSS Grid

Flexbox works in one dimension. Grid arranges items in rows and columns at the same time (`CSS/33.CSS_Grid`). Make the parent a grid container with `display: grid`, and its children become grid items.

```css
.container {
  display: grid;
  grid-template-columns: 100px 200px 1fr;
  grid-template-rows: 50px 100px;
  gap: 15px 10px;   /* row gap, then column gap */
}
```

- `1fr` takes one share of the space left over after fixed tracks.
- `grid-template-areas` names regions, and an item is placed with `grid-area: header`.
- `grid-template` is the shorthand for rows, columns and areas.
- `gap` sets the spacing. `grid-column-gap` and `grid-row-gap` are deprecated in favour of `column-gap` and `row-gap`.
- `justify-items`, `align-items` and `place-items` align items inside their cells.
- `justify-content`, `align-content` and `place-content` align the whole grid when there is spare space.
- Item placement uses `grid-column`, `grid-row` and `grid-area`, for example `grid-column: 1 / 3`.
- `justify-self`, `align-self` and `place-self` align one item in its cell.
- The note's best practice is `repeat(auto-fit, minmax(100px, 1fr))` for a grid that adapts its column count.

No question in this paper asks for Grid. Use Flexbox for the answers in this paper, and treat Grid as background knowledge from the notes.

## Common mistakes

- Expecting `justify-content` to centre vertically in a row. It centres horizontally, so use `align-items` for vertical centring in a row.
- Forgetting `display: flex` on the parent. Without it, the children are not flex items.
- Confusing `flex-grow` (extra space) with `flex-shrink` (missing space).

## Exam tip

For Flexbox questions, first state the main axis, then name the property that acts on it. The examiner checks whether you know which axis you are working on.
