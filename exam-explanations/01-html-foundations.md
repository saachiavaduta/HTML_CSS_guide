# 1. HTML Foundations

**Notes to read:** `HTML/01.Introduction_To_HTML_And_CSS`, `HTML/02.Paragraph_and_Heading_Tag`, `HTML/03.Image`, `HTML/05.Linking`, `HTML/12.Entities_And_Symbols`, `HTML/15.Meta_Tags`, `HTML/16.Favicon`

## The big idea

HTML describes the **structure and meaning** of content. CSS controls how it looks. JavaScript controls behaviour. A web page is a tree of elements, and the browser builds that tree from your HTML.

## Elements, tags, and attributes

- A **tag** is the text in angle brackets, such as `<p>` or `</p>`.
- An **element** is the whole construct: the opening tag, the content, and the closing tag. `<p>Hello</p>` is one element.
- An **attribute** is a name-value pair inside the opening tag, such as `href="..."` or `alt="..."`.

Q29 asks for the difference: the element is the structure, and the attribute adds information about that structure.

## The document skeleton

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Page title</title>
</head>
<body>
  <h1>Visible content</h1>
</body>
</html>
```

- `<!DOCTYPE html>` tells the browser to use modern HTML5 rules. It is a declaration, not a tag (Q12).
- `<html>` is the root element.
- `<head>` holds information about the page that is not shown in the body: title, metadata, stylesheets, and scripts (Q59).
- `<body>` holds everything visible.

## Head elements

| Element | Purpose | Questions |
|---------|---------|-----------|
| `<title>` | Text in the browser tab and in search results | Q49, Q59 |
| `<meta charset="UTF-8">` | Character encoding, so symbols display correctly | Q48, Q120 |
| `<meta name="viewport" content="width=device-width, initial-scale=1.0">` | Makes the page scale properly on phones | Q91, Q120 |
| `<link rel="stylesheet">` | Connects an external CSS file | Q49 |
| `<script src="..." defer>` | Loads JavaScript. `defer` runs it after the HTML is parsed (Q14) | Q14, Q49 |

## Headings and paragraphs

`<h1>` to `<h6>` are headings, with `<h1>` the most important. `<p>` is a paragraph. Browsers add space around paragraphs by default, and the heading level tells both users and search engines how the content is organised (Q48, Q57, Q68). The note recommends one `<h1>` per page, for the main title, and using heading levels in logical order rather than skipping levels.

## Links

`<a href="...">text</a>` creates a hyperlink. The `href` attribute holds the destination (Q2). Links are inline elements, so they sit inside a line of text. Use `#` as a placeholder destination when a link does not yet have a target (Q84, Q96).

## Images and alternative text

```html
<img src="library.jpg" alt="Front view of the college library">
```

- `src` is the file location.
- `alt` describes the image. It appears if the image fails to load, and screen readers read it aloud (Q30).
- Decorative images can use an empty value, `alt=""`.

Q66 and Q98 show `<figure>` and `<figcaption>`. A figure groups an image with its caption, so the link between them is explicit.

## Entities and symbols

An entity starts with `&` and ends with `;`. It can be named (`&copy;`), decimal (`&#169;`), or hexadecimal (`&#xA9;`). Some characters have special meaning in HTML, so they must be written as **entities**:

| Entity | Shows | Why |
|--------|-------|-----|
| `&lt;` | `<` | Stops the browser reading it as a tag (Q4) |
| `&gt;` | `>` | Same reason |
| `&amp;` | `&` | `&` starts an entity |
| `&copy;` | © | A symbol not on the keyboard (Q68, Q120) |
| `&nbsp;` | A non-breaking space | Keeps text such as `10 km` on one line |

## Favicon and meta tags

The favicon is the small icon in the browser tab. It is linked inside `<head>` with `<link rel="icon" href="favicon.png" type="image/png">`. The note's examples use `.ico`, `.png`, and `.svg` files. Meta tags such as `description` give search engines a summary of the page.

## Exam tip

For a basic page question (Q48, Q49, Q57, Q91), always include the doctype, `lang`, `charset`, a title, and a body. Examiners check for these.
