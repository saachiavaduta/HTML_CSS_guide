# Section C: Long-Answer and Practical Questions (Part 1: Q48-Q70)

---

## Q48. Heading, two paragraphs, and a button

**Answer:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Q48 Styled Page</title>
  <style>
    body { background-color: lightgray; }
    h1 { color: darkblue; }
    .text { font-size: 18px; line-height: 1.5; }
    #first { background-color: yellow; }
    button { padding: 10px 20px; background-color: #1e88e5; color: white; border: none; }
    button:hover { background-color: green; }
  </style>
</head>
<body>
  <h1>Welcome</h1>
  <p id="first" class="text">First paragraph of text.</p>
  <p class="text">Second paragraph of text.</p>
  <button>Click me</button>
</body>
</html>
```

**Explanation:** The element selector colors the heading, the class `.text` styles both paragraphs, the ID `#first` targets only the first paragraph, and `:hover` changes the button color on mouse-over.

---

## Q49. Head elements, semantic elements, and a hyperlink page

**Answer:**
- `<title>` sets the text shown in the browser tab and used by search engines.
- `<meta>` gives metadata, such as character set, viewport, and description.
- `<link>` connects external resources, usually stylesheets.
- `<script>` embeds or loads JavaScript.

| Element | Purpose |
|---------|---------|
| `<section>` | Thematic grouping of related content, usually with a heading |
| `<article>` | Self-contained content that could be reused on its own |
| `<aside>` | Content related to, but not central to, the surrounding content |
| `<main>` | The dominant content of the page, used once per page |

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Example Page</title>
  <link rel="stylesheet" href="style.css">
  <script src="script.js" defer></script>
</head>
<body>
  <main>
    <h1>Welcome</h1>
    <p>This page links to an external website.</p>
    <a href="https://www.example.org">Visit Example.org</a>
  </main>
</body>
</html>
```

**Explanation:** `<head>` contents are not displayed on the page, except through the title tab. `<main>` should appear once, while `<section>`, `<article>`, and `<aside>` can be repeated.

---

## Q50. Student table and registration form

**Answer:**

```html
<table border="1">
  <thead>
    <tr><th>Roll Number</th><th>Name</th><th>Marks</th></tr>
  </thead>
  <tbody>
    <tr><td>101</td><td>Asha Patel</td><td>85</td></tr>
    <tr><td>102</td><td>Rohan Shah</td><td>78</td></tr>
    <tr><td>103</td><td>Meera Joshi</td><td>91</td></tr>
  </tbody>
</table>

<form action="/register" method="post">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required>

  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required>

  <label for="password">Password:</label>
  <input type="password" id="password" name="password">

  <label for="dept">Department:</label>
  <select id="dept" name="dept">
    <option value="">Select</option>
    <option value="cs">Computer Science</option>
    <option value="it">Information Technology</option>
    <option value="ec">Electronics</option>
  </select>

  <button type="submit">Submit</button>
</form>
```

**Explanation:** `<thead>`, `<tbody>`, and `<th>` give the table its structure. `required` makes the name and email fields mandatory, and each label is linked by `for` and `id`.

---

## Q51. Ordered list, unordered list, link, and `<nav>` benefit

**Answer:**

```html
<h2>Exam Preparation Steps</h2>
<ol>
  <li>Read the syllabus</li>
  <li>Make a study timetable</li>
  <li>Revise class notes</li>
  <li>Solve previous papers</li>
  <li>Take mock tests</li>
</ol>

<h2>Web Browsers</h2>
<ul>
  <li>Google Chrome</li>
  <li>Mozilla Firefox</li>
  <li>Microsoft Edge</li>
  <li>Safari</li>
</ul>

<p>Learn more at <a href="https://developer.mozilla.org">MDN Web Docs</a>.</p>
```

**Benefit of `<nav>`:** It tells screen readers and search engines that the group contains navigation, so users can find menus quickly.

**Explanation:** `<ol>` numbers its items and `<ul>` uses bullets. The `<nav>` benefit is improved accessibility and clearer page structure.

---

## Q52. Three cards in a wrapping flex row

**Answer:**

```html
<div class="card-row">
  <div class="card">
    <h3>Design</h3>
    <p>Layouts, colors, and user experience.</p>
  </div>
  <div class="card">
    <h3>Development</h3>
    <p>Building pages with HTML, CSS, and JavaScript.</p>
  </div>
  <div class="card">
    <h3>Testing</h3>
    <p>Checking that the page works as intended.</p>
  </div>
</div>
```

```css
.card-row {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 16px;
}
.card {
  width: 30%;
  padding: 20px;
  border: 2px solid navy;
  border-radius: 10px;
  background-color: #e8f0fe;
}
```

**Explanation:** `justify-content: space-between` spaces the cards out horizontally, `flex-wrap: wrap` moves them to new lines when space runs out, and `gap` adds spacing between rows and columns.

---

## Q53. Positioning, link hover, and the purpose of `transform`

**Answer:**

- `static`: the default, in normal flow. Offsets are ignored.
- `relative`: stays in normal flow and space, but is shifted by offsets.
- `absolute`: removed from normal flow and placed relative to its nearest positioned ancestor.

```css
a {
  color: blue;
}
a:hover {
  color: red;
  text-decoration: none;
}
```

**Purpose of `transform`:** It moves, rotates, scales, or skews an element visually without changing the layout of other elements.

**Explanation:** `:hover` applies the styles only while the pointer is over the link. `text-decoration: none` removes the underline.

---

## Q54. Student profile page

**Answer:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Student Profile</title>
  <style>
    .profile img { width: 150px; border-radius: 50%; }
  </style>
</head>
<body>
  <section class="profile">
    <h1>Riya Sharma</h1>
    <img src="student.jpg" alt="Photo of Riya Sharma smiling">
    <p>Riya is a second-year computer science student who enjoys building web applications.</p>
  </section>

  <hr>

  <section class="skills">
    <h2>Technical Skills</h2>
    <ul>
      <li>HTML and CSS</li>
      <li>JavaScript</li>
      <li>Python</li>
    </ul>
    <a href="https://www.example-institute.edu">Visit the institute website</a>
  </section>
</body>
</html>
```

**Explanation:** `alt` describes the image, `<hr>` draws the horizontal line between sections, and the link points to the institute website.

---

## Q55. Feature cards with a 700px media query

**Answer:**

```html
<section class="features">
  <h2>Our Features</h2>
  <p>Three useful features for every student.</p>
  <div class="feature-cards">
    <div class="feature-card">Fast Learning</div>
    <div class="feature-card">Expert Mentors</div>
    <div class="feature-card">Flexible Timing</div>
  </div>
</section>
```

```css
.feature-cards { display: flex; gap: 16px; }
.feature-card { flex: 1; padding: 16px; border: 1px solid #ccc; border-radius: 8px; }

@media (max-width: 700px) {
  .feature-cards { flex-direction: column; }
}
```

**Explanation:** The cards sit in a row by default. At 700px or less, `flex-direction: column` stacks them vertically.

---

## Q56. Display values, button hover, and `transition`

**Answer:**

- `display: block`: starts a new line and takes the full available width. Width and height apply.
- `display: inline`: sits within the text line and takes only its content width. Width and height do not apply, and vertical padding does not affect layout.
- `display: inline-block`: sits within the text line, but width and height apply like a block.

```css
button {
  background-color: #1e88e5;
  color: white;
  padding: 10px 20px;
  transition: background-color 0.3s ease;
}
button:hover {
  background-color: orange;
  color: white;
}
```

**Purpose of `transition`:** It animates changes between property values over a set duration, such as a background color change on hover.

---

## Q57. Pale blue page with dark green heading

**Answer:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Q57 Styled Page</title>
  <style>
    body { background-color: #e3f2fd; }
    h1 { color: darkgreen; }
    .text { font-size: 17px; line-height: 1.6; }
    #second { background-color: lightyellow; }
    button { padding: 10px 20px; background-color: #1e88e5; color: white; border: none; }
    button:hover { background-color: purple; }
  </style>
</head>
<body>
  <h1>Learning Hub</h1>
  <p class="text">The first paragraph.</p>
  <p id="second" class="text">The second paragraph has a light yellow background.</p>
  <button>Start</button>
</body>
</html>
```

**Explanation:** This follows the same structure as Q48, with different values. The class applies to both paragraphs, and the ID applies only to the second.

---

## Q58. Ordered list, unordered list, link, and semantic benefit

**Answer:**

```html
<h2>Steps to Learn Web Development</h2>
<ol>
  <li>Learn HTML basics</li>
  <li>Learn CSS layout</li>
  <li>Learn JavaScript fundamentals</li>
  <li>Build small projects</li>
  <li>Learn version control with Git</li>
</ol>

<h2>Programming Languages</h2>
<ul>
  <li>JavaScript</li>
  <li>Python</li>
  <li>Java</li>
  <li>C++</li>
</ul>

<p>Practice on <a href="https://www.freecodecamp.org">freeCodeCamp</a>.</p>
```

**Advantage of semantic elements:** They make the page structure clear to search engines and assistive technology, which improves accessibility and SEO.

---

## Q59. Document structure and page-structure elements

**Answer:**

- `<!DOCTYPE html>` tells the browser this is an HTML5 document.
- `<html>` is the root element that wraps the whole page.
- `<head>` holds metadata, such as the title and stylesheets, which is not displayed.
- `<body>` holds the visible content.

| Element | Purpose |
|---------|---------|
| `<header>` | Introductory content, such as a logo and title, for a page or section |
| `<nav>` | Major navigation links |
| `<main>` | The primary content of the page |
| `<footer>` | Closing information, such as copyright and contact details |

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sample Page</title>
</head>
<body>
  <h1>Hello World</h1>
  <p>This is a sample paragraph.</p>
  <a href="https://example.com">Visit Example</a>
</body>
</html>
```

---

## Q60. Typography properties

**Answer:**

```html
<style>
  body { font-family: Arial, sans-serif; }
  .intro   { font-size: 20px; font-weight: bold; text-align: center; }
  .body    { font-size: 16px; line-height: 1.6; text-align: justify; }
  .emphasis{ font-weight: bold; }
  .link    { text-decoration: underline; color: blue; }
  .nolink  { text-decoration: none; }
</style>

<h1>Typography Demo</h1>
<p class="intro">Paragraph one uses a larger, bold, centered style.</p>
<p class="body">Paragraph two uses <span class="emphasis">bold</span> text with comfortable line spacing.</p>
<p class="body">Paragraph three shows <a class="link" href="#">an underlined link</a>.</p>
<p class="body nolink">Paragraph four has no text decoration.</p>
```

**Explanation:** `font-family` sets the typeface, `font-size` and `font-weight` set size and thickness, `text-align` sets alignment, `line-height` sets vertical spacing, and `text-decoration` adds or removes lines.

---

## Q61. Feedback form with mandatory email

**Answer:**

```html
<form action="/feedback" method="post">
  <label for="fname">Name:</label>
  <input type="text" id="fname" name="name">

  <label for="femail">Email:</label>
  <input type="email" id="femail" name="email" required>

  <label for="msg">Message:</label>
  <textarea id="msg" name="message" rows="4"></textarea>

  <label for="rating">Rating:</label>
  <select id="rating" name="rating">
    <option>Excellent</option>
    <option>Good</option>
    <option>Average</option>
    <option>Poor</option>
  </select>

  <button type="submit">Submit</button>
</form>
```

**Explanation:** `required` makes the email field mandatory, and `type="email"` also checks the format.

---

## Q62. Three flex cards with wrapping

**Answer:**

```html
<div class="skills-row">
  <div class="skill-card"><h3>HTML</h3><p>Structure of web pages.</p></div>
  <div class="skill-card"><h3>CSS</h3><p>Styling and layout.</p></div>
  <div class="skill-card"><h3>JavaScript</h3><p>Behavior and interaction.</p></div>
</div>
```

```css
.skills-row {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
  gap: 12px;
}
.skill-card {
  width: 28%;
  padding: 20px;
  border: 2px solid #333;
  border-radius: 12px;
  background-color: #fff8e1;
}
```

**Explanation:** `space-evenly` gives equal spacing around the cards, and `flex-wrap: wrap` lets them move to new lines when there is not enough space.

---

## Q63. Animated buttons with `:hover`, `transition-duration`, and `scale()`

**Answer:**

```html
<button class="btn">Red</button>
<button class="btn">Green</button>
<button class="btn big">Blue</button>
```

```css
.btn {
  padding: 12px 24px;
  color: white;
  border: none;
  transition-duration: 0.4s;
}
.btn:nth-child(1) { background-color: crimson; }
.btn:nth-child(2) { background-color: seagreen; }
.btn:nth-child(3) { background-color: royalblue; }

.btn:hover { background-color: black; }
.big:hover { transform: scale(1.2); }
```

**Explanation:** `transition-duration` makes the color change smooth, and `transform: scale(1.2)` enlarges the blue button by 20% on hover.

---

## Q64. `::first-letter` and `::before`

**Answer:**

```html
<h1>Pseudo-Elements</h1>
<p>Web development is an exciting field.</p>
<p>HTML gives a page its structure.</p>
<p>CSS controls how the page looks.</p>
```

```css
p::first-letter {
  font-size: 2em;
  font-weight: bold;
  color: darkred;
}
p::before {
  content: "★ ";
  color: goldenrod;
}
```

**Explanation:** `::first-letter` styles the first letter of each paragraph, and `::before` inserts generated content before each paragraph. The `content` property is required for `::before` to appear.

---

## Q65. Fixed button and sticky heading

**Answer:**

```html
<section class="content">
  <h2 class="sticky-heading">Section Heading</h2>
  <p>Scroll the page to see the sticky heading remain at the top.</p>
  <!-- add enough paragraphs to make the page scroll -->
</section>

<button class="fixed-btn">Back to Top</button>
```

```css
.sticky-heading {
  position: sticky;
  top: 0;
  background-color: white;
}
.fixed-btn {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
```

**Difference:** A `fixed` element stays in the same place on the screen while the page scrolls, and it is removed from the normal layout. A `sticky` element behaves normally until it reaches a set offset, such as `top: 0`, and then stays there only within its parent section.

---

## Q66. Three images with alt text and captions

**Answer:**

```html
<h2>Campus Gallery</h2>
<figure>
  <img src="library.jpg" alt="Front view of the college library">
  <h3>Library</h3>
  <figcaption>The central library building.</figcaption>
</figure>
<figure>
  <img src="lab.jpg" alt="Students working in the computer lab">
  <h3>Computer Lab</h3>
  <figcaption>Students practising coding.</figcaption>
</figure>
<figure>
  <img src="ground.jpg" alt="Students playing on the sports ground">
  <h3>Sports Ground</h3>
  <figcaption>Evening practice session.</figcaption>
</figure>
```

**Explanation:** `<figure>` and `<figcaption>` connect each caption with its image, and each `alt` describes the image for screen readers.

---

## Q67. Flex items with different `flex-shrink` values

**Answer:**

```html
<div class="shrink-demo">
  <div class="box a">Box A</div>
  <div class="box b">Box B</div>
  <div class="box c">Box C</div>
</div>
```

```css
.shrink-demo {
  display: flex;
  width: 600px;
  gap: 10px;
}
.box { width: 250px; padding: 10px; border: 1px solid #333; }
.a { flex-shrink: 0; }  /* does not shrink */
.b { flex-shrink: 1; }  /* shrinks normally */
.c { flex-shrink: 3; }  /* shrinks most */
```

**Explanation:** Each box is 250px wide, plus 20px of padding and 2px of border, so each takes 272px. With the two 10px gaps, the three need 836px in a 600px container, so the container must shrink them. Box A keeps its width, while Box C shrinks the most because its `flex-shrink` value is highest. Making the container narrower makes the difference more visible.

---

## Q68. Page using `<header>`, `<nav>`, `<main>`, `<section>`, and `<footer>`

**Answer:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Semantic Page</title>
</head>
<body>
  <header>
    <h1>My College</h1>
  </header>

  <nav>
    <a href="#">Home</a> |
    <a href="#">About</a> |
    <a href="#">Contact</a>
  </nav>

  <main>
    <section>
      <h2>Welcome</h2>
      <p>This section introduces the college.</p>
    </section>
    <section>
      <h2>Courses</h2>
      <p>Explore our undergraduate programmes.</p>
    </section>
  </main>

  <footer>
    <p>&copy; 2026 My College</p>
  </footer>
</body>
</html>
```

**Explanation:** Each element gives the page a clear role, and `&copy;` is an HTML entity for the copyright symbol.

---

## Q69. Heading, paragraph, and three responsive cards

**Answer:**

```html
<section>
  <h2>Why Choose Us</h2>
  <p>Our programmes are designed for practical learning.</p>
  <div class="cards">
    <div class="card">Practical Labs</div>
    <div class="card">Industry Projects</div>
    <div class="card">Placement Support</div>
  </div>
</section>
```

```css
.cards { display: flex; gap: 16px; }
.card { flex: 1; padding: 16px; border: 1px solid #aaa; border-radius: 8px; }

@media (max-width: 600px) {
  .cards { flex-direction: column; }
}
```

**Explanation:** The cards sit in a row on wider screens, and the media query at 600px stacks them vertically.

---

## Q70. Contact form with mandatory Name and Email

**Answer:**

```html
<form action="/contact" method="post">
  <label for="cname">Name:</label>
  <input type="text" id="cname" name="name" required>

  <label for="cemail">Email:</label>
  <input type="email" id="cemail" name="email" required>

  <label for="phone">Phone Number:</label>
  <input type="tel" id="phone" name="phone">

  <label for="subject">Subject:</label>
  <input type="text" id="subject" name="subject">

  <label for="message">Message:</label>
  <textarea id="message" name="message" rows="5"></textarea>

  <button type="submit">Submit</button>
</form>
```

**Explanation:** `required` makes Name and Email mandatory. `type="tel"` gives phone-style input on mobile devices, and each label is connected to its field through `for` and `id`.
