# 4. Selectors, Combinators, Pseudo-Classes, Pseudo-Elements, and Specificity

**Notes to read:** `CSS/02.CSS_Selectors`, `CSS/18.CSS_Combinators`, `CSS/19.CSS_Pseudo_Class`, `CSS/20.CSS_Pseudo_Elements`, `CSS/21.CSS_Attribute_Selector`, `CSS/27.CSS_Specificity`

## Basic selectors

| Selector | Example | Matches | Questions |
|----------|---------|---------|-----------|
| Element | `p` | Every `<p>` | Q75, Q93 |
| Class | `.card` | Any element with `class="card"` (reusable) | Q6, Q75 |
| ID | `#card` | The one element with `id="card"` (unique) | Q6, Q75 |
| Universal | `*` | Every element | Q11, Q93, Q120 |
| Grouping | `h1, h2` | Both headings | Q81, Q93 |
| Attribute | `input[type="text"]` | Inputs whose `type` is `text` | Q103 |

**ID versus class:** an ID must be unique on the page. A class can be shared. Use IDs for single landmarks and classes for styling many items (Q35).

## Attribute selectors

An attribute selector styles elements by an attribute, using square brackets (`CSS/21.CSS_Attribute_Selector`).

| Selector | Matches |
|----------|---------|
| `[title]` | Any element that has a `title` attribute, whatever its value |
| `[type="text"]` | An exact value match |
| `[class~="highlight"]` | A value that contains the word `highlight` in a space-separated list |
| `[href*="example"]` | A value that contains the text `example` anywhere |
| `[src^="images"]` | A value that starts with `images` |
| `[src$=".jpg"]` | A value that ends with `.jpg` |

```css
input[type="text"] { background-color: lightyellow; }
a[target="_blank"] { color: red; }
img[src$=".jpg"]   { opacity: 0.8; }
```

Q103 uses `input[type="text"]` as one of several attribute-based input selectors in the feedback form. An attribute selector scores (0,1,0) in specificity, the same as a class.

## Combinators

A combinator describes a relationship between two selectors.

```css
div p   { }   /* descendant: any p inside a div, at any depth */
div > p { }   /* child: only p directly inside a div */
h2 + p  { }   /* adjacent sibling: only the p right after an h2 */
h2 ~ p  { }   /* general sibling: every p after an h2, same parent */
```

Example:

```html
<div>
  <p>A</p>                       <!-- matches div p and div > p -->
  <section><p>B</p></section>    <!-- matches div p only -->
</div>
```

- Descendant (space) is the broadest (Q34, Q85).
- Child (`>`) is stricter and matches only direct children (Q34, Q85, Q107).
- Adjacent (`+`) matches one element (Q38, Q107).
- General (`~`) matches all following siblings (Q38, Q107).

## Pseudo-classes

A pseudo-class selects an element based on its **state or position**, with a single colon.

| Pseudo-class | Applies when | Question |
|--------------|--------------|----------|
| `:hover` | Pointer is over the element | Q21, Q48, Q63 |
| `:focus` | Element has keyboard or click focus | Q84, Q101 |
| `:checked` | Checkbox or radio is checked | Q21 (named in the explanation) |
| `:first-child`, `:last-child` | First or last child | Q39 |
| `:nth-child(n)` | Specific positions | Q63, Q75 |

Q39 asks for a definition: a pseudo-class is a state or position selector, not a name or attribute selector.

## Pseudo-elements

A pseudo-element targets a **part** of an element, with a double colon.

```css
p::first-letter { font-size: 2em; }   /* the first letter */
p::before { content: "★ "; }          /* generated content before the text */
```

- `::first-letter` styles the first letter (Q64, Q101).
- `::before` and `::after` insert content and require the `content` property (Q25, Q64).

The single-colon `:before` is the older syntax. Use `::` in exams.

## Specificity

When two rules target the same element, specificity decides the winner. Count the selector parts as a score:

| Part | Score |
|------|-------|
| Inline style | Highest (outside this table) |
| ID (`#x`) | (1,0,0) |
| Class, attribute, pseudo-class (`.x`, `[a]`, `:hover`) | (0,1,0) |
| Element, pseudo-element (`p`, `::before`) | (0,0,1) |
| Universal `*` | (0,0,0) |

Compare the three numbers left to right. Higher wins. Equal scores fall back to whichever rule is later in the stylesheet.

Worked examples:

- `#content` = (1,0,0). Highest of the options in Q3.
- `.nav li` = (0,1,1). `#nav li` = (1,0,1). Q20 chooses `#nav li` because one ID beats any number of classes.
- `li.active` = (0,1,1), `ul li` = (0,0,2).

Ties and `!important` (from `CSS/27.CSS_Specificity`):

- If two rules have equal specificity, the one later in the stylesheet wins.
- `!important` beats normal rules, including inline styles. If two `!important` rules conflict, the higher specificity wins.

Q115 shows a clear case. An element with `class="note"` and `id="alert"` gets the ID colour, because `(1,0,0)` beats `(0,1,0)` and `(0,0,1)`.

## Common mistakes

- `card` (no prefix) means the element `<card>`. `.card` is the class and `#card` the ID (Q6).
- `.body` in Q60 is an ordinary class. It is not a special selector, and it is valid because class names can contain letters.
- Avoid IDs for general styling. They make later overrides hard, because the ID score is high.

## Exam tip

For specificity questions, write the three-number score next to each selector before you choose the winner. This turns a guess into a calculation.
