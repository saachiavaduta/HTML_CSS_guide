# 2. Forms, Tables, Lists, and Semantic Sections

**Notes to read:** `HTML/06.Table`, `HTML/07.List`, `HTML/11.Sementic_Elements`, `HTML/13.Form`, `HTML/08.Inline_And_Block_Elements`

## Lists

- `<ul>` is an **unordered** list. Items get bullets. Use it when order does not matter (Q51, Q106).
- `<ol>` is an **ordered** list. Items are numbered. Use it for steps or rankings (Q51, Q58).
- `<li>` is a list item and goes inside either list type.
- `<ol>` takes `type` (`1`, `A`, `a`, `I`, `i`), `start` (first number), and `reversed` (counts down). `<ul>`'s `type` attribute is deprecated.
- `<dl>` is a description list. Each term is a `<dt>` and its description is a `<dd>`.

The order of items is the main difference between `<ul>` and `<ol>`. Both can be nested inside an `<li>`.

## Tables

A table is for **tabular data**, not for layout.

```html
<table>
  <thead>
    <tr><th>Roll No</th><th>Name</th></tr>
  </thead>
  <tbody>
    <tr><td>101</td><td>Asha Patel</td></tr>
  </tbody>
</table>
```

- `<table>` wraps the whole table.
- `<tr>` is a row.
- `<th>` is a header cell, and `<td>` is a data cell.
- `<thead>`, `<tbody>` split the header from the data, which helps accessibility and styling (Q50, Q100).
- `colspan="4"` makes one cell span four columns, which is how the break row in the timetable works (Q111).
- `rowspan` makes one cell span several rows.
- `<th>` is bold and centred by default. `<tfoot>` groups footer rows, and `<caption>` gives the table a title shown above it.
- `border-collapse: collapse` merges neighbouring borders into one line (Q100).

Q120 uses `display: block; overflow-x: auto;` on the table on small screens, so a wide table scrolls instead of breaking the layout.

## Forms

A form collects user input and sends it to a server.

```html
<form action="/register" method="post">
  ...
</form>
```

- `action` is the URL that receives the data (Q41).
- `method` says how it is sent. `get` puts the data in the URL and `post` sends it in the request body.

### Labels

```html
<label for="email">Email:</label>
<input type="email" id="email" name="email">
```

The `for` attribute must match the input's `id`. Clicking the label then focuses the input, and screen readers announce it (Q42). Wrapping the input inside the label also works.

A **placeholder** is a hint inside an empty field. It disappears when the user types, so it does not replace a label (Q46).

### Input types

| Type | Use | Question |
|------|-----|----------|
| `text` | Free text | Q50, Q70 |
| `email` | Email, checked for format | Q61, Q70 |
| `password` | Hidden characters | Q50 |
| `tel` | Phone numbers, shows number keypad on phones | Q70, Q92 |
| `date` | Date picker | Q92, Q103 |
| `radio` | **One** choice from a group. Share the same `name` | Q19, Q88 |
| `checkbox` | **Several** choices, each on its own | Q7, Q88 |

Radio buttons share a `name`, which is what makes them mutually exclusive (Q19). Checkboxes use different values under one name, so several can be selected (Q7).

### Other controls

- `<select>` with `<option>` items is a dropdown (Q50, Q61). `<select>` also takes `multiple` and `size`. Each `<option>` takes `value`, `selected`, and `disabled`.
- `<textarea rows="4" cols="30">` is a multi-line text box (Q61). `rows` and `cols` set its size.
- `required` makes a field mandatory. The browser stops submission until it has a value (Q16, Q70).

### Grouping

```html
<fieldset>
  <legend>Overall Rating</legend>
  <input type="radio" ...>
</fieldset>
```

`<fieldset>` draws a box around related controls. `<legend>` is its caption (Q5, Q88). Do not confuse it with `<caption>`, which labels a table.

## Semantic sections

Semantic elements describe **what** content is, not just how it looks. This helps screen readers and search engines (Q27).

| Element | Meaning | Questions |
|---------|---------|-----------|
| `<header>` | Introductory content, such as a logo or title | Q59, Q68, Q106 |
| `<nav>` | Major navigation links | Q36, Q51, Q68 |
| `<main>` | The main content, used once per page | Q49, Q106 |
| `<section>` | A thematic group, usually with a heading | Q49, Q68 |
| `<article>` | Self-contained content, such as a blog post | Q9, Q106, Q117 |
| `<aside>` | Related but secondary content, such as a sidebar | Q9, Q106 |
| `<footer>` | Closing information | Q59, Q68, Q120 |
| `<figure>` / `<figcaption>` | Self-contained content (image, diagram, code) and its caption | Q66, Q98 |
| `<div>` / `<span>` | No meaning. Use only for styling hooks | Q9 |

**Key test:** could this content stand alone and still make sense? If yes, it is an `<article>`. If it only relates to the content around it, it is an `<aside>`.

## Block and inline elements

- **Block** elements (`<div>`, `<p>`, `<h1>`, `<ul>`, `<ol>`, `<form>`, `<section>`, `<article>`) start a new line and fill the width of their parent.
- **Inline** elements (`<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, `<abbr>`, `<q>`) sit inside a line of text and take only as much width as their content.
- A block element can contain both block and inline elements. An inline element should contain only inline content and text, so putting a `<div>` inside a `<span>` is wrong.
- A `<div>` is a generic block container with no meaning. Use a semantic element when one fits, and use `<div>` for grouping and styling.

The note's comparison table is the quickest revision: block takes a full line, inline takes content width. This is the foundation for the `display` property in file 05, because CSS `display` can change either behaviour.

## Exam tip

For forms and tables, examiners look for `for`/`id` pairs, `thead`/`tbody`, `required` on the mandatory fields, and a correct `action` and `method`.
