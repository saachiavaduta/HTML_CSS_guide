# 7. Responsive Design, Units, Transitions, Transforms, and Animation

**Notes to read:** `CSS/25.CSS_Units`, `CSS/26.CSS_Media_queries`, `CSS/28.CSS_2D_Transforms`, `CSS/30.CSS_Transition`, `CSS/29.CSS_3D_Transition`, `CSS/31.CSS_Animation`

## Media queries

A media query applies CSS only when a condition is true, usually the viewport width.

```css
@media (max-width: 700px) {
  .cards { flex-direction: column; }
}
```

- `max-width` applies at or below the width (Q22, Q55, Q69).
- `min-width` applies at or above the width. Mobile-first designs use it.
- Q31 asks for the purpose: adapt the layout to different screens.

### Breakpoints used in the answers

| Breakpoint | Typical use | Questions |
|-----------|-------------|-----------|
| 600px | Phone layout, stack nav and cards | Q22, Q69, Q96, Q117, Q120 |
| 650px | Contact form stacking | Q114 |
| 700px | Card rows stacking | Q55, Q77, Q90, Q99, Q106, Q119 |
| 900px | Tablet layout, wrap or stack | Q117, Q120 |

Breakpoints are chosen where the layout starts to break, not for any particular device.

## Units

| Unit | Meaning | Example | Questions |
|------|---------|---------|-----------|
| `px` | Fixed pixels | `border: 2px` | Q83 |
| `%` | Percentage of the parent | `width: 60%` | Q102 |
| `em` | Multiple of the parent's font size | `padding: 1em` | Q83 |
| `rem` | Multiple of the root (`html`) font size | `font-size: 2rem` | Q83, Q102 |
| `vw` | 1% of the viewport width | `width: 50vw` | Q102 |
| `vh` | 1% of the viewport height | `height: 50vh` | Q26, Q83 |

Key idea: `em` changes with the parent, `rem` with the root, `vh` and `vw` with the window. `px` never changes.

Q83 sets `html { font-size: 16px; }`, so `2rem` = 32px.

## Transitions

A transition animates a change between two values over time.

```css
button {
  background-color: #1e88e5;
  transition: background-color 0.3s ease;
}
button:hover { background-color: orange; }
```

- The property names the value to animate (Q40, Q56).
- `transition-duration` sets the time (Q17, Q63). `0s` disables the transition.
- `ease` is the timing curve. Other options include `linear`, `ease-in`, `ease-out`, and `ease-in-out`.
- `transition-delay` sets a wait before the change starts. Its default is `0s`.
- The shorthand order is `transition: property duration timing-function delay`, for example `transition: width 0.5s ease 0.2s`.
- List several properties with commas, as in Q108.

A transition needs a change of state, such as `:hover` or `:focus`, to start. Only animatable properties can transition.

## Transforms

`transform` moves, rotates, scales, or skews an element **visually**. It does not change layout (Q47, Q40).

| Function | Effect | Question |
|----------|--------|----------|
| `scale(1.2)` | Enlarges by 20% | Q63 |
| `rotate(10deg)` | Rotates | Q108 |
| `translateX(20px)` | Moves right | Q108 |
| `scale(1.05) rotate(-5deg)` | Combined | Q108 |

`rotate()` turns around the element's centre by default; `transform-origin` moves the pivot. `translate(x, y)` takes an optional `y`, and `scale(x, y)` defaults `y` to `x`.

Pair `transform` with `transition` so the movement animates (Q40, Q98, Q113).

## 3D transforms

The 3D functions add a depth axis (`CSS/29.CSS_3D_Transition`). Depth only shows when a `perspective` is set.

```css
.stage { perspective: 500px; }   /* on the parent */
.box   { transform: rotateY(45deg); }
```

- `perspective` sets the distance from the viewer to the z=0 plane. Smaller values (500px) give a stronger effect, and larger values (2000px) a subtler one.
- `translate3d(x, y, z)` moves along all three axes. A positive `z` moves towards the viewer.
- `scale3d(x, y, z)` uses unitless factors.
- `rotateX()`, `rotateY()` and `rotateZ()` rotate around one axis. `rotateZ()` matches the 2D `rotate()`.
- `rotate3d(x, y, z, angle)` rotates around a custom axis.
- `transform-style: preserve-3d` on the parent keeps child elements positioned in 3D.

No question in this paper uses 3D transforms.

## Animations

A `@keyframes` rule defines steps, and `animation-*` properties play them (`CSS/31.CSS_Animation`).

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}
.box { animation: fadeIn 0.5s ease 0.2s 1 normal forwards; }
```

| Property | Controls | Values |
|----------|----------|--------|
| `@keyframes` | The steps | `from`/`to` or percentages such as `50%` |
| `animation-name` | Which keyframes to use | A name, `none`, or a comma-separated list |
| `animation-duration` | Length of one cycle | `1s` or `1000ms`. `0s` disables it |
| `animation-delay` | Wait before starting | Negative values start part-way through the cycle |
| `animation-iteration-count` | Number of cycles | A number or `infinite` |
| `animation-direction` | Playback direction | `normal`, `reverse`, `alternate`, `alternate-reverse` |
| `animation-timing-function` | Speed curve | `ease`, `linear`, `ease-in`, `ease-out`, `ease-in-out`, `cubic-bezier()`, `steps()` |
| `animation-fill-mode` | Styles before and after | `none`, `forwards`, `backwards`, `both` |

- Shorthand order: `animation: name duration timing-function delay iteration-count direction fill-mode`.
- An animation runs automatically. A transition needs a state change such as `:hover`. Q17 separates the two: `animation-delay` belongs to keyframe animations, not transitions.
- Only animatable properties such as `opacity`, `transform` and `background-color` can animate.
- `animation-play-state` exists in the note but is not used in its examples.

No question in this paper uses `@keyframes`.

## Hover effects in practice

Common pattern:

```css
.card { transition: transform 0.3s ease, box-shadow 0.3s ease; }
.card:hover { transform: scale(1.05); box-shadow: 0 12px 24px rgba(0,0,0,0.3); }
```

Q98 uses the `transform` part of this pattern on a gallery image. Q113 uses both properties on a profile card.

## Combining the topics

Most long answers (Q96–Q120) use the same recipe:

1. A semantic structure: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`.
2. Flexbox for the layout (file 06).
3. Box-model spacing with `padding`, `margin`, `gap`, and `border`.
4. A `:hover` or `:focus` state with a `transition`.
5. Media queries at 600px, 700px, or 900px to stack the layout.

Q120 applies all five in one complete page.

## Exam tip

When a question asks for responsive design, show at least one media query and state the breakpoint. Mention that `max-width` applies at and below the value.
