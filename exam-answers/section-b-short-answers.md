# Section B: Short-Answer Questions

---

## Q27. Define semantic HTML and give one example

**Answer:** Semantic HTML uses elements whose names describe the purpose of the content, not just its appearance. For example, `<nav>` marks a block of navigation links.

**Explanation:** Semantic markup helps screen readers, search engines, and developers understand the page structure. A `<div>` carries no meaning, while `<header>`, `<main>`, and `<footer>` do.

---

## Q28. Difference between margin and padding

**Answer:** Margin is the space outside an element's border and separates it from other elements. Padding is the space inside the border and separates the content from the border.

**Explanation:** Padding is drawn with the element's background, while margin is transparent. Adjacent vertical margins can collapse into one, but padding never collapses.

---

## Q29. One difference between an element and an attribute

**Answer:** An element is the complete construct made of a start tag, content, and an end tag, such as `<p>...</p>`. An attribute is a name-value pair placed inside the start tag, such as `class="intro"`.

**Explanation:** Elements form the structure of the page, while attributes give extra information about a specific element.

---

## Q30. Purpose of the `alt` attribute

**Answer:** The `alt` attribute gives a text description of an image. It is displayed if the image fails to load and is read aloud by screen readers.

**Explanation:** Good alt text improves accessibility and helps search engines understand the image. Decorative images can use an empty value, `alt=""`.

---

## Q31. Purpose of a CSS media query

**Answer:** A media query applies CSS rules only when the device or viewport meets a condition, such as a minimum or maximum width. It is the main tool for building responsive layouts.

**Explanation:** For example, `@media (max-width: 700px)` can stack cards vertically on small screens.

---

## Q32. Difference between `static`, `relative`, and `absolute`

**Answer:**
- `position: static` is the default. The element stays in normal document flow, and `top`, `left`, and similar offsets have no effect.
- `position: relative` keeps the element in normal flow and space, then shifts it by its offset values.
- `position: absolute` removes the element from normal flow and positions it relative to the nearest positioned ancestor. If none exists, it uses the page.

**Explanation:** Relative elements still reserve their original space in the layout. Absolute elements do not, so other content can flow underneath them.

---

## Q33. The CSS box model and its four parts

**Answer:** The CSS box model describes every element as a rectangular box made of four parts, from inside out:
1. Content
2. Padding
3. Border
4. Margin

**Explanation:** The total space an element occupies equals its width or height plus padding, border, and margin, unless `box-sizing: border-box` is applied.

---

## Q34. Descendant combinator and child combinator

**Answer:** The descendant combinator (a space) selects an element at any depth inside another element. The child combinator (`>`) selects only direct children.

```css
div p { color: blue; }    /* every p inside a div, at any depth */
div > p { color: green; } /* only p elements that are direct children of a div */
```

```html
<div>
  <p>Direct child, both rules apply</p>
  <section><p>Nested, only the descendant rule applies</p></section>
</div>
```

**Explanation:** The child combinator is stricter, so it matches fewer elements.

---

## Q35. Difference between `id` and `class`

**Answer:** An `id` must be unique within a page and identifies one element, selected with `#`. A `class` can be shared by many elements and is selected with `.`.

**Explanation:** Use IDs for unique landmarks or JavaScript targets, and use classes for reusable styling.

---

## Q36. Purpose of the `<nav>` element

**Answer:** The `<nav>` element groups the major navigation links of a page or a major section of it.

**Explanation:** It tells assistive technology that these links are navigational, so users can jump to them quickly.

---

## Q37. Difference between `display: none` and `visibility: hidden`

**Answer:** `display: none` removes the element from the layout completely, so it takes up no space. `visibility: hidden` hides the element but keeps its space in the layout.

**Explanation:** Hidden elements with `visibility: hidden` cannot be clicked, but they still affect how surrounding elements are positioned.

---

## Q38. Adjacent sibling (`+`) and general sibling (`~`) combinators

**Answer:** The adjacent sibling combinator `h2 + p` selects only the paragraph that immediately follows an `h2` with the same parent. The general sibling combinator `h2 ~ p` selects every paragraph that follows the `h2` and shares its parent.

```css
h2 + p { color: navy; }  /* only the first p after each h2 */
h2 ~ p { color: gray; }  /* all following p siblings of each h2 */
```

**Explanation:** Both require the elements to share a parent. The general sibling form is broader.

---

## Q39. What is a CSS pseudo-class? Give two examples

**Answer:** A pseudo-class selects an element based on its state or position, rather than on its name or attributes. Examples are `:hover`, which applies when the pointer is over an element, and `:focus`, which applies when an element has focus.

**Explanation:** Other examples include `:first-child`, `:last-child`, and `:nth-child()`.

---

## Q40. Difference between `transform` and `transition`

**Answer:** `transform` changes an element's appearance, such as scaling, rotating, or moving it, without affecting the layout. `transition` controls how a change to a CSS property animates over time, such as the duration and easing.

**Explanation:** The two are often used together. For example, `transform` can define the end state and `transition` can animate the move to it.

---

## Q41. Purpose of the `action` attribute in a form

**Answer:** The `action` attribute specifies the URL to which the form data is sent when the form is submitted.

**Explanation:** The `method` attribute, such as `get` or `post`, determines how the data is sent.

---

## Q42. Purpose of the `<label>` element in a form

**Answer:** The `<label>` element gives a visible caption to a form control. It is linked to the control through the `for` attribute matching the input's `id`, or by wrapping the input.

**Explanation:** Clicking a linked label focuses its input, and screen readers announce the label when the input is selected.

---

## Q43. Difference between `flex-grow` and `flex-shrink`

**Answer:** `flex-grow` determines how much a flex item expands to fill extra space in its container. `flex-shrink` determines how much it contracts when the container is too small for its items.

**Explanation:** Both are unitless ratios compared with the other items in the same flex container.

---

## Q44. Difference between `flex-direction: row` and `flex-direction: column`

**Answer:** `row` places flex items horizontally from left to right, so the main axis is horizontal. `column` stacks them vertically from top to bottom, so the main axis is vertical.

**Explanation:** Changing the direction also changes what `justify-content` and `align-items` control.

---

## Q45. Purpose of the `flex-wrap` property

**Answer:** `flex-wrap` controls whether flex items stay on one line or wrap onto new lines when there is not enough space. The default is `nowrap`.

**Explanation:** `flex-wrap: wrap` is useful for card layouts that should flow onto a second row on narrow screens.

---

## Q46. Purpose of the `placeholder` attribute

**Answer:** The `placeholder` attribute shows a hint inside an empty input field. The hint disappears as soon as the user starts typing.

**Explanation:** A placeholder does not replace a `<label>`, because it disappears and is not reliably read by all assistive technology.

---

## Q47. Purpose of the `transform` property

**Answer:** The `transform` property moves, rotates, scales, or skews an element visually. It does not change how the surrounding elements are laid out.

**Explanation:** Common functions include `translate()`, `rotate()`, and `scale()`.
