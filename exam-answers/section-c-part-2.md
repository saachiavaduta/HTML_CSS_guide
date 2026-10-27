# Section C: Long-Answer and Practical Questions (Part 2: Q71-Q95)

---

## Q71. Demonstrating `block`, `inline`, and `inline-block`

**Answer:**

```html
<div class="demo block">Block</div>
<span class="demo inline">Inline</span>
<span class="demo inline-block">Inline-block</span>
```

```css
.demo { background-color: lightblue; border: 1px solid navy; margin: 6px; }
.block { display: block; width: 200px; height: 60px; }
.inline { display: inline; width: 200px; height: 60px; }        /* width/height ignored */
.inline-block { display: inline-block; width: 200px; height: 60px; }
```

**Explanation:** The block box fills its line, while the inline box ignores its width and height. The inline-block box sits beside other content and still accepts width and height.

---

## Q72. Background, text color, font size, line height, and letter spacing

**Answer:**

```html
<h1>Styled Heading</h1>
<p>First paragraph with custom styling.</p>
<p>Second paragraph with custom styling.</p>
<p>Third paragraph with custom styling.</p>
```

```css
body {
  background-color: #fdf6e3;
  color: #333;
}
p {
  font-size: 18px;
  line-height: 1.7;
  letter-spacing: 1px;
}
```

**Explanation:** `background-color` sets the page background, `color` sets the text color, `font-size` sets the text size, `line-height` sets vertical spacing, and `letter-spacing` sets the space between letters.

---

## Q73. `visibility: hidden` versus `display: none`

**Answer:**

```html
<div class="box first">Box 1 (hidden by visibility)</div>
<div class="box second">Box 2 (hidden by display)</div>
<div class="box third">Box 3 (visible)</div>
```

```css
.box { width: 200px; padding: 20px; margin: 10px; background-color: lightcoral; }
.first { visibility: hidden; }
.second { display: none; }
```

**How the layout changes:** Box 1 becomes invisible but still takes up its space, so Box 3 stays lower than Box 2's old position. Box 2 is removed completely, so Box 3 moves up to fill the gap.

---

## Q74. `align-items` values with flex items of different heights

**Answer:**

```html
<div class="row align-flex-start"><div class="item h1">A</div><div class="item h2">B</div><div class="item h3">C</div></div>
<div class="row align-center"><div class="item h1">A</div><div class="item h2">B</div><div class="item h3">C</div></div>
<div class="row align-flex-end"><div class="item h1">A</div><div class="item h2">B</div><div class="item h3">C</div></div>
<div class="row align-stretch"><div class="item">A</div><div class="item">B</div><div class="item">C</div></div>
```

```css
.row { display: flex; gap: 10px; height: 160px; background: #eef; margin-bottom: 12px; }
.item { width: 80px; background: steelblue; color: white; }
.h1 { height: 40px; }
.h2 { height: 80px; }
.h3 { height: 120px; }

.align-flex-start { align-items: flex-start; }
.align-center { align-items: center; }
.align-flex-end { align-items: flex-end; }
.align-stretch { align-items: stretch; }
.align-stretch .item { height: auto; }
```

**Explanation:** `align-items` controls the cross axis. `flex-start` aligns items at the top, `center` centers them, `flex-end` aligns them at the bottom, and `stretch` makes items fill the container height when they have no fixed height.

---

## Q75. Element, class, and ID selectors on three cards

**Answer:**

```html
<h2>Cards</h2>
<div class="card" id="card-one">
  <h3>Card One</h3>
  <p>Styled by the ID.</p>
</div>
<div class="card">
  <h3>Card Two</h3>
  <p>Styled by the class.</p>
</div>
<div class="card">
  <h3>Card Three</h3>
  <p>Styled by the class.</p>
</div>
```

```css
div { padding: 16px; margin: 10px; }        /* element selector */
.card { border: 1px solid #555; }           /* class selector */
.card p { font-size: 16px; color: #222; }
#card-one { background-color: #ffe0b2; }    /* ID selector */
#card-one h3 { font-size: 24px; color: darkred; }
.card:nth-child(2) { background-color: #c8e6c9; }
```

**Explanation:** The element selector covers all cards, the class covers the shared styling, and the ID changes only the first card. Specificity means the ID rule wins for that card.

---

## Q76. `min-width`, `max-width`, `min-height`, and `max-height`

**Answer:**

```html
<div class="content-box">
  This box has minimum and maximum dimensions. Add more text to see the maximum height limit take effect and the content scroll or overflow.
</div>
```

```css
.content-box {
  width: 50%;
  min-width: 250px;
  max-width: 500px;
  min-height: 100px;
  max-height: 200px;
  border: 2px solid navy;
  padding: 12px;
  overflow: auto;
}
```

**Explanation:** `min-width` and `min-height` set the smallest size the box can reach, while `max-width` and `max-height` set the largest. Resize the window to see the width change between these limits. `overflow: auto` adds a scrollbar if the text exceeds the maximum height.

---

## Q77. Heading and three cards with a 700px breakpoint

**Answer:**

```html
<section>
  <h2>Our Services</h2>
  <div class="service-row">
    <div class="service-card">Web Design</div>
    <div class="service-card">App Development</div>
    <div class="service-card">Hosting</div>
  </div>
</section>
```

```css
.service-row { display: flex; gap: 16px; }
.service-card { flex: 1; padding: 16px; border: 1px solid #999; border-radius: 8px; }

@media (max-width: 700px) {
  .service-row { flex-direction: column; }
}
```

**Explanation:** The row layout applies to larger screens, and the 700px media query stacks the cards at smaller widths.

---

## Q78. Different `flex-basis` values

**Answer:**

```html
<div class="basis-row">
  <div class="b-item one">Item 1</div>
  <div class="b-item two">Item 2</div>
  <div class="b-item three">Item 3</div>
</div>
```

```css
.basis-row { display: flex; gap: 10px; width: 700px; }
.b-item { padding: 12px; border: 1px solid #333; background: #f5f5f5; }
.one   { flex-basis: 100px; }
.two   { flex-basis: 200px; }
.three { flex-basis: 300px; }
```

**Explanation:** `flex-basis` sets each item's starting main size before free space is shared out. Items with larger basis values start wider. Their final sizes also depend on `flex-grow` and `flex-shrink`.

---

## Q79. Child absolutely positioned in a relative parent's top-right corner

**Answer:**

```html
<div class="parent">
  <p>Parent container</p>
  <div class="child">Top-right</div>
</div>
```

```css
.parent {
  position: relative;
  width: 400px;
  height: 250px;
  border: 2px solid navy;
}
.child {
  position: absolute;
  top: 10px;
  right: 10px;
  padding: 8px;
  background-color: gold;
}
```

**Explanation:** The parent becomes the containing block for the absolutely positioned child. `top` and `right` place the child in the corner of the parent, not the page.

---

## Q80. Min and max dimensions with visible borders

**Answer:**

```html
<div class="size-demo">
  Short text.
</div>
<div class="size-demo wide">
  This box has longer text so you can observe how max-width and max-height limit the size of the box as the content grows.
</div>
```

```css
.size-demo {
  min-width: 200px;
  max-width: 350px;
  min-height: 80px;
  max-height: 150px;
  padding: 10px;
  border: 2px dashed teal;
  margin-bottom: 16px;
  overflow: auto;
}
.wide { background-color: #e0f7fa; }
```

**Explanation:** The first box stays at its minimum size because its content is short. The second box grows until it reaches its maximum width and height, after which the content scrolls.

---

## Q81. Element, class, and ID selectors for headings and paragraphs

**Answer:**

```html
<h1>Main Heading</h1>
<p class="intro">First paragraph of text.</p>
<h2 id="special">Special Heading</h2>
<p class="intro">Second paragraph of text.</p>
<button>Read more</button>
```

```css
h1, h2 { color: #222; }               /* element selector for all headings */
.intro { font-size: 18px; line-height: 1.5; }  /* class for both paragraphs */
#special { background-color: #fff176; } /* ID selector for one heading */
```

**Explanation:** The element selector applies to all headings, the class applies to both paragraphs, and the ID changes only one heading's background.

---

## Q82. Cards with border, radius, padding, background, and shadow

**Answer:**

```html
<div class="cards">
  <div class="card">Card 1</div>
  <div class="card">Card 2</div>
  <div class="card">Card 3</div>
</div>
```

```css
.cards { display: flex; gap: 20px; }
.card {
  flex: 1;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 12px;
  background-color: #ffffff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}
```

**Explanation:** `box-shadow` takes horizontal offset, vertical offset, blur radius, and color, which here produces a soft shadow beneath each card.

---

## Q83. `px`, `em`, `rem`, and `vh` units

**Answer:**

```html
<h1 class="title">Units Demo</h1>
<p class="text">This paragraph uses relative units.</p>
<div class="hero">Container using vh</div>
```

```css
html { font-size: 16px; }

.title { font-size: 2rem; }          /* 2 x root font size = 32px */
.text {
  font-size: 1.1em;                  /* relative to parent font size */
  padding: 1em;
  border: 2px solid #444;            /* px for a fixed border */
}
.hero {
  height: 50vh;                      /* half the viewport height */
  background-color: #b2ebf2;
}
```

**Explanation:** `px` is a fixed size, `em` depends on the parent's font size, `rem` depends on the root font size, and `vh` depends on the viewport height. Resizing the browser changes only the `vh` box.

---

## Q84. Link hover and focus outline for input fields

**Answer:**

```html
<h1>Interactive Page</h1>
<p>Visit <a href="#">the documentation</a> for more.</p>
<p>Visit <a href="#">the tutorial</a> for practice.</p>
<p>Visit <a href="#">the forum</a> for help.</p>

<label for="search">Search:</label>
<input type="text" id="search" name="search">
```

```css
a:hover {
  color: purple;
  text-decoration: underline;
}
input:focus {
  outline: 3px solid orange;
  outline-offset: 2px;
}
```

**Explanation:** `:hover` changes links while the pointer is over them, and `:focus` shows an outline when the input is selected with the keyboard or mouse.

---

## Q85. Descendant and child selectors

**Answer:**

```html
<div class="parent">
  <p>Direct child paragraph.</p>
  <section>
    <p>Nested paragraph inside a section.</p>
  </section>
</div>
```

```css
.parent p { color: navy; }      /* all paragraphs inside .parent */
.parent > p { font-weight: bold; } /* only direct child paragraphs */
```

**Explanation:** The descendant selector matches both paragraphs, so both turn navy. The child selector matches only the first paragraph, so only it becomes bold.

---

## Q86. Flex `justify-content` values

**Answer:**

```html
<div class="jc flex-start"><div class="box">1</div><div class="box">2</div><div class="box">3</div></div>
<div class="jc center"><div class="box">1</div><div class="box">2</div><div class="box">3</div></div>
<div class="jc flex-end"><div class="box">1</div><div class="box">2</div><div class="box">3</div></div>
<div class="jc space-between"><div class="box">1</div><div class="box">2</div><div class="box">3</div></div>
<div class="jc space-around"><div class="box">1</div><div class="box">2</div><div class="box">3</div></div>
<div class="jc space-evenly"><div class="box">1</div><div class="box">2</div><div class="box">3</div></div>
```

```css
.jc { display: flex; background: #eceff1; padding: 8px; margin-bottom: 10px; }
.box { width: 60px; height: 40px; background: #42a5f5; color: white; text-align: center; line-height: 40px; }
.flex-start { justify-content: flex-start; }
.center { justify-content: center; }
.flex-end { justify-content: flex-end; }
.space-between { justify-content: space-between; }
.space-around { justify-content: space-around; }
.space-evenly { justify-content: space-evenly; }
```

**Explanation:** `flex-start` packs items at the start, `center` centers them, and `flex-end` packs them at the end. `space-between` places the first and last items at the edges, `space-around` gives each item equal space on both sides, and `space-evenly` makes every gap the same size.

---

## Q87. `overflow: hidden`, `auto`, and `scroll`

**Answer:**

```html
<h2>Overflow Demo</h2>
<p>Each box below has the same fixed size but contains the same long paragraph.</p>

<div class="ov hidden"><p>Long text that goes beyond the box height. Long text that goes beyond the box height. Long text that goes beyond the box height.</p></div>
<div class="ov auto"><p>Long text that goes beyond the box height. Long text that goes beyond the box height. Long text that goes beyond the box height.</p></div>
<div class="ov scroll"><p>Long text that goes beyond the box height. Long text that goes beyond the box height. Long text that goes beyond the box height.</p></div>
```

```css
.ov { width: 250px; height: 100px; border: 2px solid #333; margin-bottom: 12px; }
.hidden { overflow: hidden; }   /* extra content is clipped, no scrollbar */
.auto { overflow: auto; }       /* scrollbar appears only when needed */
.scroll { overflow: scroll; }   /* scrollbars always shown */
```

**Explanation:** `hidden` cuts off the extra text, `auto` adds a scrollbar only when content overflows, and `scroll` always shows scrollbars.

---

## Q88. Feedback form with radio buttons, checkboxes, dropdown, and textarea

**Answer:**

```html
<form action="/survey" method="post">
  <fieldset>
    <legend>Overall Rating</legend>
    <input type="radio" id="r1" name="rating" value="5"><label for="r1">Excellent</label>
    <input type="radio" id="r2" name="rating" value="4"><label for="r2">Good</label>
    <input type="radio" id="r3" name="rating" value="3"><label for="r3">Average</label>
  </fieldset>

  <fieldset>
    <legend>Interests</legend>
    <input type="checkbox" id="i1" name="interest" value="coding"><label for="i1">Coding</label>
    <input type="checkbox" id="i2" name="interest" value="design"><label for="i2">Design</label>
    <input type="checkbox" id="i3" name="interest" value="music"><label for="i3">Music</label>
  </fieldset>

  <label for="course">Course:</label>
  <select id="course" name="course">
    <option>BCA</option>
    <option>BSc IT</option>
    <option>B.Tech CSE</option>
  </select>

  <label for="comments">Comments:</label>
  <textarea id="comments" name="comments" rows="4"></textarea>

  <button type="submit">Submit</button>
</form>
```

**Explanation:** Radio buttons that share a `name` allow only one choice. Checkboxes allow several choices. `<fieldset>` and `<legend>` group related controls.

---

## Q89. Three cards styled with selectors and the box model

**Answer:**

```html
<div class="card-wrap">
  <div class="card card-1">Card 1</div>
  <div class="card card-2">Card 2</div>
  <div class="card card-3">Card 3</div>
</div>
```

```css
.card { box-sizing: border-box; background: #fafafa; }
.card-1 { width: 220px; height: 120px; margin: 10px; padding: 10px; border: 1px solid #333; }
.card-2 { width: 260px; height: 140px; margin: 20px; padding: 20px; border: 3px solid #666; }
.card-3 { width: 300px; height: 160px; margin: 0 30px; padding: 30px; border: 5px dashed #999; }
.card-wrap { display: flex; align-items: flex-start; }
```

**Explanation:** Each card has its own margin, padding, border, and size, so the box model controls the total space each card takes. `box-sizing: border-box` keeps the set width including padding and border.

---

## Q90. Responsive page with a 700px breakpoint

**Answer:**

```html
<section class="responsive">
  <h1>Our Features</h1>
  <p>Explore what this platform offers.</p>
  <div class="feature-row">
    <div class="feature">Speed</div>
    <div class="feature">Security</div>
    <div class="feature">Support</div>
  </div>
</section>
```

```css
.feature-row { display: flex; gap: 16px; }
.feature { flex: 1; padding: 16px; border: 1px solid #bbb; border-radius: 8px; }

@media (max-width: 700px) {
  .feature-row { flex-direction: column; }
}
```

**Explanation:** Flexbox places the cards in a row on desktops, and the media query arranges them vertically at 700px or below.

---

## Q91. Personal portfolio webpage

**Answer:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Portfolio</title>
  <style>
    body {
      background-color: #f4f6f8;
      font-family: Arial, sans-serif;
      color: #222;
      margin: 0;
      padding: 20px;
      line-height: 1.6;
    }
    h1 { color: #0d47a1; }
    img { width: 180px; border-radius: 50%; }
    hr { margin: 24px 0; }
    a { color: #1565c0; }
  </style>
</head>
<body>
  <header>
    <h1>Riya Sharma</h1>
    <img src="profile.jpg" alt="Profile photo of Riya Sharma">
  </header>

  <section>
    <p>I am a computer science student who enjoys building responsive websites and learning new technologies.</p>
  </section>

  <hr>

  <section>
    <h2>Skills</h2>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
      <li>Git</li>
    </ul>
  </section>

  <section>
    <h2>Career Goals</h2>
    <ol>
      <li>Complete an internship in front-end development</li>
      <li>Build a full-stack project</li>
      <li>Work as a professional web developer</li>
    </ol>
  </section>

  <p>
    Find me on <a href="https://github.com">GitHub</a> or
    <a href="https://www.linkedin.com">LinkedIn</a>.
  </p>
</body>
</html>
```

**Explanation:** The page uses a heading, an image with alt text, an unordered list of skills, an ordered list of goals, two hyperlinks, and a horizontal rule. CSS sets the background, font family, text color, and spacing.

---

## Q92. Student registration form

**Answer:**

```html
<form action="/student-register" method="post">
  <label for="fullname">Full Name:</label>
  <input type="text" id="fullname" name="fullname" required>

  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required>

  <label for="password">Password:</label>
  <input type="password" id="password" name="password">

  <label for="dob">Date of Birth:</label>
  <input type="date" id="dob" name="dob">

  <label for="phone">Phone Number:</label>
  <input type="tel" id="phone" name="phone">

  <label for="dept">Department:</label>
  <select id="dept" name="dept">
    <option value="">Select a department</option>
    <option value="cs">Computer Science</option>
    <option value="it">Information Technology</option>
    <option value="ec">Electronics</option>
    <option value="me">Mechanical</option>
  </select>

  <p>Course type:</p>
  <input type="radio" id="ug" name="course" value="ug"><label for="ug">Undergraduate</label>
  <input type="radio" id="pg" name="course" value="pg"><label for="pg">Postgraduate</label>

  <p>Extracurricular interests:</p>
  <input type="checkbox" id="sports" name="interest" value="sports"><label for="sports">Sports</label>
  <input type="checkbox" id="music" name="interest" value="music"><label for="music">Music</label>
  <input type="checkbox" id="coding" name="interest" value="coding"><label for="coding">Coding Club</label>

  <button type="submit">Submit</button>
</form>
```

**Explanation:** Name and email are mandatory. Each label is linked to its control through `for` and `id`, and the dropdown, radio buttons, and checkboxes cover the required choices.

---

## Q93. Styling with CSS selectors

**Answer:**

```html
<h1>Selectors Demo</h1>
<h2>Subheading</h2>
<p class="large" id="highlight">Paragraph with an ID and a class.</p>
<p class="large">Paragraph with only a class.</p>
<p>Plain paragraph.</p>
<p>Another plain paragraph.</p>
<button>One</button>
<button>Two</button>
<button>Three</button>
```

```css
* { font-family: Verdana, sans-serif; }    /* universal selector */
h1, h2 { color: darkgreen; }              /* element selector */
.large { font-size: 18px; line-height: 1.5; }  /* class selector */
#highlight { background-color: yellow; }  /* ID selector */
```

**Explanation:** The universal selector applies the font to every element, the element selector colors all headings, the class sets the size and line height, and the ID gives one paragraph its yellow background.

---

## Q94. Four product cards in a wrapping flex row

**Answer:**

```html
<section class="products">
  <div class="product-card">
    <img src="p1.jpg" alt="Wireless headphones">
    <h3>Wireless Headphones</h3>
    <p>Comfortable over-ear design with long battery life.</p>
    <p class="price">Rs. 2,499</p>
    <button>Add to Cart</button>
  </div>
  <div class="product-card">
    <img src="p2.jpg" alt="Smart watch">
    <h3>Smart Watch</h3>
    <p>Tracks fitness and notifications.</p>
    <p class="price">Rs. 3,999</p>
    <button>Add to Cart</button>
  </div>
  <div class="product-card">
    <img src="p3.jpg" alt="Bluetooth speaker">
    <h3>Bluetooth Speaker</h3>
    <p>Portable speaker with clear sound.</p>
    <p class="price">Rs. 1,799</p>
    <button>Add to Cart</button>
  </div>
  <div class="product-card">
    <img src="p4.jpg" alt="Laptop bag">
    <h3>Laptop Bag</h3>
    <p>Padded bag for laptops up to 15 inches.</p>
    <p class="price">Rs. 899</p>
    <button>Add to Cart</button>
  </div>
</section>
```

```css
.products {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 20px;
}
.product-card {
  width: 22%;
  padding: 16px;
  border: 1px solid #ccc;
  border-radius: 10px;
  background-color: #ffffff;
}
.product-card img { width: 100%; border-radius: 8px; }
```

**Explanation:** `flex-wrap: wrap` moves cards to a new row when the width is insufficient, `justify-content: space-between` spaces them evenly, and each card has padding, a border, rounded corners, and a background color.

---

## Q95. Box model demonstration with three boxes

**Answer:**

```html
<div class="boxes">
  <div class="box box-1">Box 1: width, margin, padding, and border applied.</div>
  <div class="box box-2">Box 2: different width, height, margin, padding, and border.</div>
  <div class="box box-3">Box 3: largest margin and padding.</div>
</div>
```

```css
.boxes { display: flex; align-items: flex-start; gap: 24px; }
.box { box-sizing: content-box; }
.box-1 { width: 150px; height: 80px; margin: 10px; padding: 8px; border: 1px solid #333; background-color: #ffcdd2; }
.box-2 { width: 180px; height: 100px; margin: 20px; padding: 12px; border: 3px solid #1565c0; background-color: #c8e6c9; }
.box-3 { width: 210px; height: 120px; margin: 30px; padding: 20px; border: 5px dashed #6a1b9a; background-color: #fff9c4; }
```

**How margin, padding, and borders affect space:** Padding increases the space inside the box and is painted with the background. The border adds thickness around the padding. Margin adds space outside the border, so it separates the box from its neighbors without changing its own background. With `content-box`, the total width equals the width plus padding plus border plus margin.
