# Section A: Multiple-Choice Questions

| Q | Answer | Q | Answer |
|---|--------|---|--------|
| 1 | B | 14 | B |
| 2 | B | 15 | B |
| 3 | C | 16 | B |
| 4 | C | 17 | B |
| 5 | B | 18 | C |
| 6 | A | 19 | B |
| 7 | B | 20 | C |
| 8 | B | 21 | B |
| 9 | A | 22 | B |
| 10 | B | 23 | B |
| 11 | B | 24 | A |
| 12 | B | 25 | B |
| 13 | B | 26 | C |

---

## Q1. Property for arranging flex items along the main axis
**Answer: B. `justify-content`**

**Explanation:** `justify-content` distributes items along the main axis (horizontal in a row, vertical in a column). `align-items` and `align-content` work on the cross axis, and `flex-wrap` controls line wrapping.

---

## Q2. HTML element for a hyperlink
**Answer: B. `<a>`**

**Explanation:** The anchor element `<a>` creates links, and its `href` attribute holds the destination. `<link>` is used in the head to connect resources such as stylesheets.

---

## Q3. Highest specificity
**Answer: C. `#content`**

**Explanation:** An ID selector scores (1,0,0). A class scores (0,1,0), an element scores (0,0,1), and the universal selector scores nothing.

---

## Q4. Entity for the less-than symbol
**Answer: C. `&lt;`**

**Explanation:** `&lt;` is the named character reference for `<`. Written as HTML text, it displays `<` instead of starting a tag.

---

## Q5. Caption for a fieldset
**Answer: B. `<legend>`**

**Explanation:** `<legend>` is the first child of `<fieldset>` and labels the group. `<caption>` is for tables, and `<label>` is for individual controls.

---

## Q6. Selector for the element with ID `card`
**Answer: A. `#card`**

**Explanation:** The `#` prefix selects by ID. `.card` selects by class, and `card` selects `<card>` elements.

---

## Q7. Input type for multiple independent options
**Answer: B. `type="checkbox"`**

**Explanation:** Checkboxes let users select any number of options. Radio buttons allow only one choice per group.

---

## Q8. Property for stacking order
**Answer: B. `z-index`**

**Explanation:** `z-index` sets the stacking order of positioned elements (and flex/grid items). Higher values appear in front. It has no effect on `position: static` elements.

---

## Q9. Independent, self-contained content element
**Answer: A. `<article>`**

**Explanation:** `<article>` marks content that could stand alone, such as a blog post or news item. `<aside>` is related but secondary content, and `<div>` and `<span>` have no semantic meaning.

---

## Q10. Space inside an element's border
**Answer: B. `padding`**

**Explanation:** Padding sits between the content and the border. Margin is outside the border, `outline` is drawn outside the border without taking space, and `gap` is spacing between flex or grid items.

---

## Q11. Selector for every element
**Answer: B. `*`**

**Explanation:** The universal selector `*` matches all elements. `all` is not a CSS selector, and the other options are invalid.

---

## Q12. Declaration for an HTML5 document
**Answer: B. `<!DOCTYPE html>`**

**Explanation:** This declaration tells the browser to use standards mode. It is not a tag, and it is not case-sensitive.

---

## Q13. Controls how much a flex item shrinks
**Answer: B. `flex-shrink`**

**Explanation:** `flex-shrink` sets the shrink factor when items overflow the container. `flex-grow` handles extra space, `flex-basis` sets the starting size, and `flex-direction` sets the main axis.

---

## Q14. Element to include JavaScript
**Answer: B. `<script>`**

**Explanation:** `<script>` embeds or links JavaScript. Its `src` attribute loads an external file, and `defer` is commonly used to delay execution until the HTML is parsed.

---

## Q15. Property that rounds corners
**Answer: B. `border-radius`**

**Explanation:** `border-radius` rounds all four corners, for example `border-radius: 10px;`. Individual corners can be set with longhand properties such as `border-top-left-radius`.

---

## Q16. Attribute that makes an input mandatory
**Answer: B. `required`**

**Explanation:** `required` stops the form from submitting until the field has a value. It is a boolean attribute, so it is written as `required` with no value needed.

---

## Q17. Controls the duration of a transition
**Answer: B. `transition-duration`**

**Explanation:** `transition-duration` sets how long the transition takes, such as `0.3s`. `animation-delay` belongs to keyframe animations, and `transition-speed` and `transform-duration` do not exist.

---

## Q18. Controls how much a flex item grows
**Answer: C. `flex-grow`**

**Explanation:** `flex-grow` decides how much of the leftover space an item receives relative to its siblings. For example, an item with `flex-grow: 2` takes twice the extra space of one with `flex-grow: 1`.

---

## Q19. Input type for one option from a group
**Answer: B. `type="radio"`**

**Explanation:** Radio buttons that share the same `name` form a group, and only one can be selected at a time. `<select>` is a dropdown element, not an input type.

---

## Q20. Highest specificity
**Answer: C. `#nav li`**

**Explanation:** `#nav li` has one ID and one element, giving (1,0,1). `.nav li` scores (0,1,1), `li.active` scores (0,1,1), and `ul li` scores (0,0,2).

---

## Q21. Pseudo-class for mouse pointer over an element
**Answer: B. `:hover`**

**Explanation:** `:hover` applies while the pointer is over an element. `:focus` applies when the element has keyboard or input focus, and `:checked` applies to checked inputs.

---

## Q22. Media query for widths of 600px or less
**Answer: B. `@media (max-width: 600px)`**

**Explanation:** `max-width` applies at or below the given viewport width. `min-width` applies at or above it. `width` by itself matches only one exact width, so it does not cover a range.

---

## Q23. Property that adds a shadow around an element's box
**Answer: B. `box-shadow`**

**Explanation:** `box-shadow` draws a shadow around the element's border box. `text-shadow` applies to text only, and the other options do not exist.

---

## Q24. Controls content that exceeds the box
**Answer: A. `overflow`**

**Explanation:** `overflow` controls what happens to content that overflows, using values such as `visible`, `hidden`, `scroll`, and `auto`.

---

## Q25. Pseudo-element that inserts content before an element
**Answer: B. `::before`**

**Explanation:** `::before` creates generated content before an element's content, and it requires the `content` property. `:before` is the older single-colon syntax, and `:first-child` is a pseudo-class.

---

## Q26. Unit relative to the viewport height
**Answer: C. `vh`**

**Explanation:** `1vh` equals 1% of the viewport height. `em` and `rem` are font-relative, and `px` is an absolute length.
