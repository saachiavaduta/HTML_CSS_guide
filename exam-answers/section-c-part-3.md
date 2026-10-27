# Section C: Long-Answer and Practical Questions (Part 3: Q96-Q120)

---

## Q96. Horizontal navigation bar with a 600px breakpoint

**Answer:**

```html
<header class="navbar">
  <div class="brand">Green Valley College</div>
  <nav>
    <ul class="nav-links">
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Courses</a></li>
      <li><a href="#">Gallery</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</header>
```

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 24px;
  background-color: #1a237e;
}
.brand { color: white; font-size: 20px; font-weight: bold; }
.nav-links { display: flex; gap: 16px; list-style: none; margin: 0; padding: 0; }
.nav-links a { color: white; text-decoration: none; padding: 8px 12px; border-radius: 4px; }
.nav-links a:hover { color: #1a237e; background-color: #ffeb3b; }

@media (max-width: 600px) {
  .navbar { flex-direction: column; }
  .nav-links { flex-direction: column; gap: 8px; margin-top: 8px; }
}
```

**Explanation:** Flexbox places the college name on the left and the links on the right. The hover rule changes the link color and background, and the media query stacks the links vertically at 600px or below.

---

## Q97. Three positioned children in a relative parent

**Answer:**

```html
<div class="big-parent">
  <div class="child child-1">Top-right</div>
  <div class="child child-2">Bottom-left</div>
  <div class="child child-3">Overlay</div>
</div>
```

```css
.big-parent {
  position: relative;
  width: 600px;
  height: 400px;
  border: 2px solid #333;
  background-color: #eceff1;
}
.child { position: absolute; width: 180px; height: 120px; padding: 10px; }
.child-1 { top: 10px; right: 10px; background-color: #aed581; }
.child-2 { bottom: 10px; left: 10px; background-color: #81d4fa; }
.child-3 {
  top: 60px;
  left: 150px;
  background-color: rgba(255, 152, 0, 0.9);
  z-index: 10;
}
```

**Explanation:** The parent is the containing block, so the children position themselves within it. The third child has the highest `z-index`, so it appears above the other two where they overlap.

---

## Q98. Image gallery with captions and hover zoom

**Answer:**

```html
<div class="gallery">
  <figure class="gallery-item"><img src="img1.jpg" alt="Campus entrance"><figcaption>Entrance</figcaption></figure>
  <figure class="gallery-item"><img src="img2.jpg" alt="College library"><figcaption>Library</figcaption></figure>
  <figure class="gallery-item"><img src="img3.jpg" alt="Science lab"><figcaption>Lab</figcaption></figure>
  <figure class="gallery-item"><img src="img4.jpg" alt="Sports ground"><figcaption>Sports</figcaption></figure>
  <figure class="gallery-item"><img src="img5.jpg" alt="Auditorium"><figcaption>Auditorium</figcaption></figure>
  <figure class="gallery-item"><img src="img6.jpg" alt="Cafeteria"><figcaption>Cafeteria</figcaption></figure>
</div>
```

```css
.gallery { display: flex; flex-wrap: wrap; gap: 16px; }
.gallery-item { width: 30%; margin: 0; text-align: center; }
.gallery-item img {
  width: 100%;
  border: 2px solid #455a64;
  border-radius: 10px;
  transition: transform 0.3s ease;
}
.gallery-item img:hover { transform: scale(1.05); }
```

**Explanation:** Each image sits in its own `<figure>` with a caption. Flexbox spaces the items, and the `transition` on `transform` makes the enlargement on hover smooth.

---

## Q99. Responsive feature section

**Answer:**

```html
<section class="feature-section">
  <h2>Why Learn With Us</h2>
  <p>Our courses combine theory with hands-on practice.</p>
  <div class="feature-cards">
    <div class="feature-card f1">Hands-on Labs</div>
    <div class="feature-card f2">Live Projects</div>
    <div class="feature-card f3">Career Guidance</div>
  </div>
</section>
```

```css
.feature-cards { display: flex; gap: 20px; }
.feature-card { flex: 1; padding: 20px; border: 2px solid #3949ab; border-radius: 8px; }
.f1 { background-color: #e8eaf6; }
.f2 { background-color: #e0f2f1; }
.f3 { background-color: #fff3e0; }

@media (max-width: 700px) {
  .feature-cards { flex-direction: column; }
}
```

**Explanation:** The cards sit in one row on larger screens. Each has a different background, padding, and border, and the 700px media query stacks them vertically.

---

## Q100. Student marks table

**Answer:**

```html
<table class="marks">
  <thead>
    <tr>
      <th>Roll Number</th>
      <th>Student Name</th>
      <th>HTML Marks</th>
      <th>CSS Marks</th>
      <th>Total Marks</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>101</td><td>Asha Patel</td><td>45</td><td>42</td><td>87</td></tr>
    <tr><td>102</td><td>Rohan Shah</td><td>38</td><td>40</td><td>78</td></tr>
    <tr><td>103</td><td>Meera Joshi</td><td>48</td><td>46</td><td>94</td></tr>
    <tr><td>104</td><td>Kunal Mehta</td><td>35</td><td>39</td><td>74</td></tr>
    <tr><td>105</td><td>Priya Desai</td><td>44</td><td>43</td><td>87</td></tr>
  </tbody>
</table>
```

```css
.marks { border-collapse: collapse; width: 100%; }
.marks th, .marks td {
  border: 1px solid #555;
  padding: 10px;
  text-align: center;
}
.marks th { background-color: #1e88e5; color: white; }
.marks tbody tr:hover { background-color: #e3f2fd; }
```

**Explanation:** `<thead>` holds the headings, `<tbody>` holds the records, and `<th>` and `<td>` mark header and data cells. `border-collapse` removes double borders, and `:hover` on the row changes its background.

---

## Q101. Pseudo-classes and pseudo-elements

**Answer:**

```html
<h1>Pseudo-Class Demo</h1>
<h2>Second Heading</h2>
<p>First paragraph text.</p>
<p>Second paragraph text.</p>
<a href="#">A link</a>
<button>Click me</button>
<input type="text" placeholder="Type here">
```

```css
button { padding: 10px 20px; background-color: #42a5f5; border: none; color: white; }
button:hover { background-color: #0d47a1; }

input:focus { outline: 3px solid #ff9800; }

p::first-letter { font-size: 2em; color: crimson; font-weight: bold; }

h1::before, h2::before { content: "❖ "; color: teal; }
```

**Explanation:** `:hover` changes the button background, and `:focus` adds a visible outline to the input. `::first-letter` enlarges the first letter of each paragraph, and `::before` adds a symbol before each heading.

---

## Q102. Units and dimensions

**Answer:**

```html
<div class="units-wrap">
  <div class="unit-box box-px">Width in px</div>
  <div class="unit-box box-pct">Width in %</div>
  <div class="unit-box box-vw">Width in vw</div>
  <div class="unit-box box-rem">Width in rem</div>
</div>
```

```css
html { font-size: 16px; }
.units-wrap { display: flex; flex-direction: column; gap: 12px; }
.unit-box { padding: 1em; border: 1px solid #333; background-color: #f1f8e9; }

.box-px  { width: 300px; }
.box-pct { width: 60%; }
.box-vw  { width: 50vw; min-width: 200px; }
.box-rem { width: 20rem; max-width: 100%; }

.box-px  { min-height: 60px; }
.box-rem { max-height: 10rem; }
```

**Explanation:** `px` is fixed, `%` depends on the parent width, `vw` depends on the viewport width, and `rem` depends on the root font size. Resizing the window changes the `%` and `vw` boxes. The `px` and `rem` boxes keep their width, though `max-width: 100%` on the `rem` box stops it from overflowing a narrow window. `em` and `rem` are also used for text and padding.

---

## Q103. College event feedback form with styling

**Answer:**

```html
<form class="feedback-form" action="/event-feedback" method="post">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">

  <label for="email">Email:</label>
  <input type="email" id="email" name="email">

  <label for="event-date">Event Date:</label>
  <input type="date" id="event-date" name="event-date">

  <p>Overall satisfaction:</p>
  <input type="radio" id="sat1" name="satisfaction" value="yes"><label for="sat1">Yes</label>
  <input type="radio" id="sat2" name="satisfaction" value="no"><label for="sat2">No</label>

  <p>Activities attended:</p>
  <input type="checkbox" id="a1" name="activities" value="talk"><label for="a1">Talk</label>
  <input type="checkbox" id="a2" name="activities" value="workshop"><label for="a2">Workshop</label>

  <label for="rating">Rating:</label>
  <select id="rating" name="rating">
    <option>5</option><option>4</option><option>3</option><option>2</option><option>1</option>
  </select>

  <label for="feedback">Feedback:</label>
  <textarea id="feedback" name="feedback" rows="4"></textarea>

  <button type="submit">Submit</button>
</form>
```

```css
.feedback-form {
  max-width: 420px;
  margin: 24px auto;
  padding: 20px;
  background-color: #fafafa;
  border: 1px solid #ccc;
  border-radius: 10px;
}
.feedback-form label { display: block; margin-top: 10px; font-weight: bold; }
.feedback-form input[type="text"],
.feedback-form input[type="email"],
.feedback-form input[type="date"],
.feedback-form select,
.feedback-form textarea {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
  border: 1px solid #999;
  border-radius: 4px;
}
.feedback-form input:focus,
.feedback-form textarea:focus { outline: 2px solid #1e88e5; }
.feedback-form button {
  margin-top: 16px;
  padding: 10px 20px;
  background-color: #1e88e5;
  color: white;
  border: none;
  border-radius: 4px;
  transition: background-color 0.3s;
}
.feedback-form button:hover { background-color: #0d47a1; }
```

**Explanation:** The form container uses padding, border, and `margin: auto` to center it. The inputs share one width, `:focus` outlines the input being edited, and the button's `:hover` and `transition` change its color smoothly.

---

## Q104. Flexbox direction, justification, alignment, and gap

**Answer:**

```html
<h3>Row Direction</h3>
<div class="flex-demo row">
  <div class="fb s1">1</div><div class="fb s2">2</div><div class="fb s3">3</div><div class="fb s4">4</div>
</div>

<h3>Column Direction</h3>
<div class="flex-demo column">
  <div class="fb s1">1</div><div class="fb s2">2</div><div class="fb s3">3</div><div class="fb s4">4</div>
</div>
```

```css
.flex-demo {
  display: flex;
  gap: 12px;
  height: 220px;
  padding: 10px;
  background: #eceff1;
  margin-bottom: 16px;
}
.row { flex-direction: row; justify-content: space-between; align-items: center; }
.column { flex-direction: column; justify-content: flex-start; align-items: flex-start; }

.fb { background: #5c6bc0; color: white; padding: 10px; }
.s1 { width: 60px; height: 40px; }
.s2 { width: 80px; height: 60px; }
.s3 { width: 40px; height: 80px; }
.s4 { width: 100px; height: 50px; }

/* Alternative justify-content values, each applied to a separate container */
.justify-center { justify-content: center; }
.justify-flex-end { justify-content: flex-end; }

/* Alternative align-items values */
.align-flex-start { align-items: flex-start; }
.align-stretch { align-items: stretch; }
```

**Explanation:** `flex-direction` sets the main axis, and `justify-content` and `align-items` then control alignment along the main and cross axes. `gap` adds spacing between the child boxes without outer margins. Give each example its own container to show each value separately.

---

## Q105. Overflow in three fixed-size boxes

**Answer:**

```html
<div class="ov-box hidden-box"><p>Long text that does not fit in the box. Long text that does not fit in the box. Long text that does not fit in the box.</p></div>
<div class="ov-box auto-box"><p>Long text that does not fit in the box. Long text that does not fit in the box. Long text that does not fit in the box.</p></div>
<div class="ov-box scroll-box"><p>Long text that does not fit in the box. Long text that does not fit in the box. Long text that does not fit in the box.</p></div>
```

```css
.ov-box { width: 240px; height: 110px; border: 2px solid #37474f; padding: 8px; margin-bottom: 12px; }
.hidden-box { overflow: hidden; }
.auto-box { overflow: auto; }
.scroll-box { overflow: scroll; }
```

**Explanation:**
- `overflow: hidden` clips the extra content, and the user cannot scroll to it.
- `overflow: auto` adds a scrollbar only when the content overflows.
- `overflow: scroll` always shows scrollbars, even when the content fits.

---

## Q106. Blog article layout with semantic HTML

**Answer:**

```html
<header>
  <h1>Tech Blog</h1>
  <nav>
    <a href="#">Home</a> | <a href="#">Articles</a> | <a href="#">Contact</a>
  </nav>
</header>

<main class="blog-layout">
  <article class="post">
    <h2>Getting Started with CSS Flexbox</h2>
    <img src="flexbox.jpg" alt="Diagram showing flex container and items">
    <p>Flexbox helps arrange items in rows and columns with less effort.</p>
    <p>Read the <a href="https://developer.mozilla.org">official guide</a> for more.</p>
  </article>

  <aside class="sidebar">
    <h3>Related Topics</h3>
    <ul>
      <li>CSS Grid</li>
      <li>Media Queries</li>
      <li>Responsive Design</li>
    </ul>
  </aside>
</main>
```

```css
.blog-layout { display: flex; gap: 24px; padding: 20px; }
.post { flex: 3; }
.sidebar { flex: 1; background-color: #f5f5f5; padding: 16px; border-radius: 8px; }
.post img { width: 100%; border-radius: 6px; }

@media (max-width: 700px) {
  .blog-layout { flex-direction: column; }
}
```

**Explanation:** `<header>` and `<nav>` hold the title and links, and `<main>` contains the article and sidebar. The article takes three parts of the width and the sidebar takes one, and the media query stacks them on small screens.

---

## Q107. Descendant, child, adjacent sibling, and general sibling combinators

**Answer:**

```html
<div class="container">
  <h2>Heading One</h2>
  <p>First paragraph after the heading.</p>
  <p>Second paragraph after the heading.</p>
  <ul>
    <li>Item
      <ul>
        <li><p>Nested paragraph inside a list.</p></li>
      </ul>
    </li>
  </ul>
  <div class="inner"><p>Paragraph inside a nested div.</p></div>
</div>
```

```css
.container p { color: navy; }            /* descendant: all paragraphs, including nested */
.container > p { font-weight: bold; }    /* child: only direct child paragraphs */
h2 + p { color: darkgreen; }             /* adjacent sibling: only the first paragraph after h2 */
h2 ~ p { font-style: italic; }           /* general sibling: all paragraphs after h2 with the same parent */
```

**Explanation:** The descendant selector matches every paragraph inside `.container`. The child selector matches only direct children. The adjacent sibling selector matches just the first paragraph after the heading, and the general sibling selector matches all following paragraphs.

---

## Q108. Animated buttons with transformations

**Answer:**

```html
<button class="b1">Scale</button>
<button class="b2">Rotate</button>
<button class="b3">Translate</button>
<button class="b4">Combined</button>
```

```css
button {
  padding: 12px 24px;
  border: none;
  color: white;
  transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease;
}
.b1 { background-color: #e53935; border-radius: 4px; }
.b2 { background-color: #43a047; border-radius: 20px; }
.b3 { background-color: #1e88e5; border-radius: 0; }
.b4 { background-color: #8e24aa; border-radius: 12px; }

.b1:hover { background-color: #b71c1c; color: #fff9c4; transform: scale(1.1); }
.b2:hover { background-color: #1b5e20; color: #e8f5e9; transform: rotate(10deg); }
.b3:hover { background-color: #0d47a1; color: #e3f2fd; transform: translateX(20px); }
.b4:hover { background-color: #4a148c; color: #f3e5f5; transform: scale(1.05) rotate(-5deg); }
```

**Explanation:** Each button has its own color and radius. `:hover` changes the colors and applies a different transform, and `transition` makes both changes animate smoothly.

---

## Q109. Three pricing cards

**Answer:**

```html
<div class="pricing">
  <div class="plan">
    <h3>Basic</h3>
    <p class="price">Rs. 299 / month</p>
    <ul><li>5 projects</li><li>Email support</li></ul>
    <button>Subscribe</button>
  </div>
  <div class="plan featured">
    <h3>Pro</h3>
    <p class="price">Rs. 799 / month</p>
    <ul><li>Unlimited projects</li><li>Priority support</li><li>Analytics</li></ul>
    <button>Subscribe</button>
  </div>
  <div class="plan">
    <h3>Team</h3>
    <p class="price">Rs. 1,999 / month</p>
    <ul><li>Team workspace</li><li>Admin controls</li><li>Dedicated support</li></ul>
    <button>Subscribe</button>
  </div>
</div>
```

```css
.pricing { display: flex; justify-content: space-between; gap: 20px; }
.plan {
  flex: 1;
  padding: 24px;
  border: 1px solid #cfd8dc;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.12);
  background-color: #ffffff;
  text-align: center;
}
.plan.featured { background-color: #e3f2fd; border: 2px solid #1565c0; }
.plan button {
  padding: 10px 18px;
  background-color: #1565c0;
  color: white;
  border: none;
  border-radius: 6px;
  transition: background-color 0.3s;
}
.plan button:hover { background-color: #0d47a1; }
```

**Explanation:** Flexbox places the cards in an equal-width row. The middle card has a different background through the `.featured` class, and every subscription button changes color on hover.

---

## Q110. Display property comparison

**Answer:**

```html
<h3>Spans set to block</h3>
<span class="block-span">Span 1</span>
<span class="block-span">Span 2</span>

<h3>Divs set to inline</h3>
<div class="inline-div">Div A</div>
<div class="inline-div">Div B</div>

<h3>Inline-block boxes</h3>
<div class="ib">Box 1</div>
<div class="ib">Box 2</div>
<div class="ib">Box 3</div>
```

```css
.block-span { display: block; background: #bbdefb; padding: 6px; margin-bottom: 6px; }
.inline-div { display: inline; background: #c8e6c9; padding: 6px; }
.ib {
  display: inline-block;
  width: 120px;
  height: 60px;
  margin: 10px;
  background: #ffe0b2;
  vertical-align: top;
}
```

**Explanation:** Block spans take a full line, so each one starts on a new line. Inline divs sit beside each other, and their width and height are ignored. Inline-block boxes sit side by side and accept width, height, and margins, but the spacing between them is affected by whitespace in the HTML.

---

## Q111. College timetable with `colspan`

**Answer:**

```html
<table class="timetable">
  <thead>
    <tr>
      <th>Day</th>
      <th>9-10 AM</th>
      <th>10-11 AM</th>
      <th>11-12 PM</th>
      <th>12-1 PM</th>
    </tr>
  </thead>
  <tbody>
    <tr><th>Monday</th><td>HTML</td><td>CSS</td><td>JavaScript</td><td>Lab</td></tr>
    <tr><th>Tuesday</th><td>Maths</td><td>English</td><td>HTML</td><td>Lab</td></tr>
    <tr><th>Wednesday</th><td>CSS</td><td>JavaScript</td><td>Maths</td><td>Project</td></tr>
    <tr><th>Thursday</th><td>English</td><td>HTML</td><td>CSS</td><td>Lab</td></tr>
    <tr><th>Friday</th><td>JavaScript</td><td>Maths</td><td>Project</td><td>Lab</td></tr>
    <tr class="break"><th>Break</th><td colspan="4">Lunch Break (12:30 PM - 1:00 PM)</td></tr>
  </tbody>
</table>
```

```css
.timetable { border-collapse: collapse; width: 100%; }
.timetable th, .timetable td {
  border: 1px solid #455a64;
  padding: 10px;
  text-align: center;
}
.timetable thead th { background-color: #37474f; color: white; }
.timetable tbody th { background-color: #eceff1; }
.timetable .break td { background-color: #fff3e0; font-style: italic; }
```

**Explanation:** `colspan="4"` makes the break cell stretch across all four time columns. Borders, padding, background colors, and centered text make the timetable easier to read.

---

## Q112. `flex-grow`, `flex-shrink`, and `flex-basis` together

**Answer:**

```html
<h3>flex-grow</h3>
<div class="fg-row">
  <div class="g g1">1</div><div class="g g2">2</div><div class="g g3">3</div><div class="g g4">4</div>
</div>

<h3>flex-shrink</h3>
<div class="fs-row">
  <div class="s s1">1</div><div class="s s2">2</div><div class="s s3">3</div><div class="s s4">4</div>
</div>

<h3>flex-basis</h3>
<div class="fb-row">
  <div class="b b1">1</div><div class="b b2">2</div><div class="b b3">3</div><div class="b b4">4</div>
</div>
```

```css
.fg-row, .fs-row, .fb-row { display: flex; gap: 10px; margin-bottom: 16px; background: #eceff1; padding: 8px; }
.g, .s, .b { padding: 12px; background: #5c6bc0; color: white; }

.g1 { flex-grow: 1; }
.g2 { flex-grow: 2; }
.g3 { flex-grow: 3; }
.g4 { flex-grow: 0; }

.fs-row { width: 500px; }
.s { width: 200px; }
.s1 { flex-shrink: 0; }
.s2 { flex-shrink: 1; }
.s3 { flex-shrink: 2; }
.s4 { flex-shrink: 3; }

.b1 { flex-basis: 80px; }
.b2 { flex-basis: 120px; }
.b3 { flex-basis: 160px; }
.b4 { flex-basis: 200px; }
```

**How the three properties work together:**
- `flex-basis` sets each item's starting size.
- If there is extra space, `flex-grow` shares it out in proportion to each value.
- If there is too little space, `flex-shrink` removes space in proportion to each value, weighted by the item's basis.

Resizing the window shows these effects.

---

## Q113. Personal profile card centered on the page

**Answer:**

```html
<body class="page">
  <div class="profile-card">
    <img src="student.jpg" alt="Photo of the student">
    <h2>Riya Sharma</h2>
    <p class="course">B.Tech Computer Science, Year 2</p>
    <p class="bio">Passionate about web development and building useful apps.</p>
    <div class="social">
      <a href="https://github.com">GitHub</a>
      <a href="https://www.linkedin.com">LinkedIn</a>
    </div>
  </div>
</body>
```

```css
.page {
  margin: 0;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #eceff1;
}
.profile-card {
  width: 300px;
  padding: 24px;
  text-align: center;
  background-color: white;
  border: 1px solid #b0bec5;
  border-radius: 14px;
  box-shadow: 0 6px 14px rgba(0, 0, 0, 0.15);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.profile-card img { width: 120px; border-radius: 50%; }
.social a { margin: 0 8px; color: #1565c0; }
.profile-card:hover {
  transform: scale(1.05);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.3);
}
```

**Explanation:** Flexbox on the body centers the card both horizontally and vertically, using `min-height: 100vh`. The hover rule enlarges the card and deepens its shadow, and the transition animates both changes.

---

## Q114. Responsive contact section with a 650px breakpoint

**Answer:**

```html
<section class="contact-wrap">
  <div class="contact-info">
    <h2>Contact Information</h2>
    <p>Email: info@example.com</p>
    <p>Phone: +91 98765 43210</p>
    <p>Address: 12 Main Street, City</p>
  </div>

  <form class="contact-form" action="/contact" method="post">
    <h2>Send a Message</h2>
    <label for="cname">Name:</label>
    <input type="text" id="cname" name="name">

    <label for="cemail">Email:</label>
    <input type="email" id="cemail" name="email">

    <label for="csubject">Subject:</label>
    <input type="text" id="csubject" name="subject">

    <label for="cmessage">Message:</label>
    <textarea id="cmessage" name="message" rows="5"></textarea>

    <button type="submit">Send</button>
  </form>
</section>
```

```css
.contact-wrap { display: flex; gap: 24px; padding: 20px; }
.contact-info, .contact-form { flex: 1; padding: 20px; border: 1px solid #cfd8dc; border-radius: 8px; }
.contact-form input, .contact-form textarea { width: 100%; box-sizing: border-box; margin-bottom: 12px; padding: 8px; }

@media (max-width: 650px) {
  .contact-wrap { flex-direction: column; }
}
```

**Explanation:** The two containers sit side by side on larger screens, and the media query arranges them vertically at 650px or below.

---

## Q115. CSS specificity and conflicting text colors

**Answer:**

```html
<h1>Specificity Demo</h1>
<p>First paragraph, styled by the element selector only.</p>
<p class="note">Second paragraph, styled by a class.</p>
<p id="alert" class="note">Third paragraph, styled by an ID and a class.</p>
```

```css
p { color: blue; }      /* element selector: (0,0,1) */
.note { color: green; } /* class selector: (0,1,0) */
#alert { color: red; }  /* ID selector: (1,0,0) */
```

**Explanation:** The first paragraph is blue. The second is green, because a class beats an element selector. The third is red, because the ID has the highest specificity and wins over both the class and the element rule, even though the class also applies to it.

---

## Q116. Layered cards with `z-index`

**Answer:**

```html
<div class="stack">
  <div class="layer card-a">Card A</div>
  <div class="layer card-b">Card B</div>
  <div class="layer card-c">Card C</div>
</div>
```

```css
.stack { position: relative; width: 500px; height: 300px; }
.layer {
  position: absolute;
  width: 220px;
  height: 140px;
  padding: 12px;
  border-radius: 10px;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.25);
}
.card-a { top: 0; left: 0; background-color: #ffcdd2; border: 2px solid #c62828; z-index: 1; }
.card-b { top: 60px; left: 120px; background-color: #c8e6c9; border: 2px solid #2e7d32; z-index: 2; }
.card-c { top: 120px; left: 240px; background-color: #bbdefb; border: 2px solid #1565c0; z-index: 3; }
```

**Explanation:** Absolute positioning inside the relative parent places the cards at different offsets. The `z-index` values decide which card is on top where they overlap, and the colors, borders, and shadows keep each card distinct.

---

## Q117. Library website with responsive navigation and cards

**Answer:**

```html
<header class="lib-header">
  <h1>City Library</h1>
  <nav class="lib-nav">
    <a href="#">Home</a>
    <a href="#">Books</a>
    <a href="#">Categories</a>
    <a href="#">Contact</a>
  </nav>
</header>

<main class="book-section">
  <article class="book-card">
    <img src="book1.jpg" alt="Cover of Learning HTML">
    <h2>Learning HTML</h2>
    <p>A beginner's guide to structuring web pages.</p>
  </article>
  <article class="book-card">
    <img src="book2.jpg" alt="Cover of Modern CSS">
    <h2>Modern CSS</h2>
    <p>Layouts, animations, and responsive design.</p>
  </article>
  <article class="book-card">
    <img src="book3.jpg" alt="Cover of JavaScript Basics">
    <h2>JavaScript Basics</h2>
    <p>Core concepts for interactive pages.</p>
  </article>
</main>
```

```css
.lib-header { display: flex; justify-content: space-between; align-items: center; padding: 12px 24px; background: #4e342e; color: white; }
.lib-nav { display: flex; gap: 16px; }
.lib-nav a { color: white; text-decoration: none; }

.book-section { display: flex; gap: 20px; padding: 20px; }
.book-card { flex: 1; padding: 16px; border: 1px solid #d7ccc8; border-radius: 8px; background: #fffaf5; }
.book-card img { width: 100%; border-radius: 6px; }

@media (max-width: 900px) {
  .book-section { flex-wrap: wrap; }
  .book-card { flex: 1 1 45%; }
}

@media (max-width: 600px) {
  .lib-header { flex-direction: column; gap: 8px; }
  .lib-nav { flex-direction: column; }
  .book-section { flex-direction: column; }
}
```

**Explanation:** The header and cards use Flexbox. At tablet width, the cards wrap into two columns, and at mobile width, the navigation and cards stack vertically.

---

## Q118. Backgrounds and borders

**Answer:**

```html
<div class="box solid-box">Solid background</div>
<div class="box gradient-box">Linear gradient</div>
<div class="box image-box">Background image</div>
<div class="box dashed-box">Border styles</div>
```

```css
.box {
  width: 260px;
  height: 140px;
  margin: 16px;
  padding: 16px;
  display: inline-block;
  vertical-align: top;
}
.solid-box {
  background-color: #29b6f6;
  border: 2px solid #01579b;
  border-radius: 8px;
}
.gradient-box {
  background-image: linear-gradient(to right, #ff8a65, #ffd54f);
  border: 4px double #bf360c;
  border-radius: 20px;
}
.image-box {
  background-image: url("pattern.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  border: 3px dotted #33691e;
  border-radius: 0;
}
.dashed-box {
  background-color: #f3e5f5;
  border: 3px dashed #6a1b9a;
  border-radius: 30px;
}
```

**Explanation:** The first box uses a solid color. The second uses `linear-gradient`. The third sets an image with `background-size` and `background-position`. The fourth shows a dashed border with a large radius. Margins and padding separate the boxes.

---

## Q119. Multi-section landing page for a web development course

**Answer:**

```html
<header class="site-header">
  <div class="logo">WebDev Academy</div>
  <nav class="site-nav">
    <a href="#features">Features</a>
    <a href="#courses">Courses</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<section class="hero">
  <div class="hero-text">
    <h1>Become a Web Developer</h1>
    <p>Learn HTML, CSS, and JavaScript through practical projects.</p>
    <a class="cta" href="#contact">Enroll Now</a>
  </div>
  <img src="hero.jpg" alt="Student coding on a laptop">
</section>

<section id="features" class="features">
  <h2>Course Features</h2>
  <div class="feature-row">
    <div class="feature-card">Live Projects</div>
    <div class="feature-card">Mentor Support</div>
    <div class="feature-card">Certificate</div>
  </div>
</section>

<footer id="contact" class="site-footer">
  <p>Email: hello@webdevacademy.example</p>
  <p>Phone: +91 98765 43210</p>
  <nav>
    <a href="#">Privacy</a>
    <a href="#">Terms</a>
  </nav>
</footer>
```

```css
.site-header { display: flex; justify-content: space-between; align-items: center; padding: 14px 24px; background: #263238; color: white; }
.site-nav { display: flex; gap: 16px; }
.site-nav a { color: white; text-decoration: none; }

.hero { display: flex; align-items: center; gap: 24px; padding: 40px 24px; background: #e1f5fe; }
.hero-text { flex: 1; }
.hero img { flex: 1; max-width: 45%; border-radius: 10px; }
.cta { display: inline-block; padding: 12px 24px; background: #0277bd; color: white; border-radius: 6px; text-decoration: none; }

.features { padding: 30px 24px; }
.feature-row { display: flex; gap: 16px; }
.feature-card { flex: 1; padding: 20px; border: 1px solid #b0bec5; border-radius: 8px; background: white; }

.site-footer { padding: 20px 24px; background: #263238; color: white; }
.site-footer a { color: #81d4fa; margin-right: 12px; }

@media (max-width: 700px) {
  .hero, .feature-row, .site-header { flex-direction: column; }
  .hero img { max-width: 100%; }
}
```

**Explanation:** The page has a header, a hero section with a call-to-action button, a Flexbox feature row, and a footer with contact information and links. The media query at 700px stacks the header, hero, and features vertically.

---

## Q120. Complete responsive website

**Answer:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Complete Responsive Website</title>
  <style>
    * { box-sizing: border-box; }
    body { margin: 0; font-family: Arial, sans-serif; color: #222; line-height: 1.6; }

    header { display: flex; justify-content: space-between; align-items: center; padding: 14px 24px; background: #1a237e; color: white; }
    nav { display: flex; gap: 16px; }
    nav a { color: white; text-decoration: none; padding: 6px 10px; border-radius: 4px; transition: background-color 0.3s; }
    nav a:hover { background-color: #3949ab; }

    main { display: flex; gap: 24px; padding: 24px; }
    .intro, .register { flex: 1; padding: 20px; border: 1px solid #c5cae9; border-radius: 10px; background: #fafafa; }

    .register input, .register select { display: block; width: 100%; margin: 6px 0 12px; padding: 8px; }
    .register button { padding: 10px 20px; background: #1a237e; color: white; border: none; border-radius: 4px; transition: background-color 0.3s; }
    .register button:hover { background: #0d1260; }

    table { width: 100%; border-collapse: collapse; margin: 20px 0; }
    th, td { border: 1px solid #9fa8da; padding: 10px; text-align: center; }
    th { background: #3949ab; color: white; }
    tbody tr:hover { background: #e8eaf6; }

    .sections { display: flex; gap: 20px; padding: 0 24px 24px; }
    .sections section { flex: 1; padding: 16px; border: 1px solid #c5cae9; border-radius: 8px; }

    footer { padding: 16px 24px; background: #1a237e; color: white; text-align: center; }

    @media (max-width: 900px) {
      main, .sections { flex-direction: column; }
    }

    @media (max-width: 600px) {
      header { flex-direction: column; gap: 8px; }
      nav { flex-direction: column; gap: 6px; }
      table { display: block; overflow-x: auto; white-space: nowrap; }
    }
  </style>
</head>
<body>
  <header>
    <h1>Riverside College</h1>
    <nav>
      <a href="#">Home</a>
      <a href="#">About</a>
      <a href="#">Courses</a>
      <a href="#">Contact</a>
    </nav>
  </header>

  <main>
    <section class="intro">
      <h2>Welcome</h2>
      <p>Riverside College offers practical programmes in computing and design.</p>
    </section>

    <form class="register" action="/register" method="post">
      <h2>Student Registration</h2>
      <label for="fn">Full Name:</label>
      <input type="text" id="fn" name="fullname" required>

      <label for="em">Email:</label>
      <input type="email" id="em" name="email" required>

      <label for="dp">Department:</label>
      <select id="dp" name="dept">
        <option value="">Select</option>
        <option>Computer Science</option>
        <option>Information Technology</option>
        <option>Electronics</option>
      </select>

      <button type="submit">Register</button>
    </form>
  </main>

  <div class="sections">
    <section>
      <h2>Student Information</h2>
      <table>
        <thead>
          <tr><th>Roll No</th><th>Name</th><th>Department</th><th>Marks</th></tr>
        </thead>
        <tbody>
          <tr><td>101</td><td>Asha Patel</td><td>CS</td><td>87</td></tr>
          <tr><td>102</td><td>Rohan Shah</td><td>IT</td><td>78</td></tr>
          <tr><td>103</td><td>Meera Joshi</td><td>EC</td><td>91</td></tr>
        </tbody>
      </table>
    </section>
    <section>
      <h2>Upcoming Events</h2>
      <p>Coding workshop, science fair, and placement drive this month.</p>
    </section>
  </div>

  <footer>
    <p>&copy; 2026 Riverside College. All rights reserved.</p>
  </footer>
</body>
</html>
```

**Explanation:** The page uses semantic elements, a Flexbox header and content layout, a registration form, a styled table, and hover and transition effects. Media queries at 900px and 600px stack the layout for tablets and phones, and the table scrolls horizontally on small screens so it stays usable.
