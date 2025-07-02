# HTML Tags Reference Guide

## Document Structure Tags

### `<html>`
The root element that wraps all content on the page.
```html
<html lang="en">
  <!-- All page content goes here -->
</html>
```

### `<head>`
Contains metadata about the document that isn't displayed on the page.
```html
<head>
  <title>Page Title</title>
  <meta charset="UTF-8">
</head>
```

### `<body>`
Contains all the visible content of the webpage.
```html
<body>
  <h1>Welcome to my website</h1>
  <p>This is visible content.</p>
</body>
```

## Metadata Tags

### `<title>`
Sets the title shown in the browser tab and search results.
```html
<title>My Amazing Website</title>
```

### `<meta>`
Provides metadata about the document.
```html
<meta charset="UTF-8">
<meta name="description" content="A brief description of the page">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### `<link>`
Links to external resources like CSS files or favicons.
```html
<link rel="stylesheet" href="styles.css">
<link rel="icon" href="favicon.ico">
```

### `<script>`
Includes JavaScript code or links to external scripts.
```html
<script src="script.js"></script>
<script>
  console.log("Hello, World!");
</script>
```

### `<style>`
Contains CSS styles for the document.
```html
<style>
  body { font-family: Arial, sans-serif; }
  h1 { color: blue; }
</style>
```

## Text Content Tags

### Headings (`<h1>` to `<h6>`)
Create hierarchical headings from largest to smallest.
```html
<h1>Main Title</h1>
<h2>Chapter Title</h2>
<h3>Section Title</h3>
<h4>Subsection</h4>
<h5>Minor Heading</h5>
<h6>Smallest Heading</h6>
```

### `<p>`
Defines a paragraph of text.
```html
<p>This is a paragraph with some text content.</p>
```

### `<br>`
Inserts a line break (self-closing tag).
```html
<p>First line<br>Second line</p>
```

### `<hr>`
Creates a horizontal rule or divider line (self-closing tag).
```html
<p>Content above</p>
<hr>
<p>Content below</p>
```

## Text Formatting Tags

### `<strong>` and `<b>`
Make text bold. `<strong>` indicates importance, `<b>` is purely visual.
```html
<p>This is <strong>important text</strong> and this is <b>bold text</b>.</p>
```

### `<em>` and `<i>`
Make text italic. `<em>` indicates emphasis, `<i>` is purely visual.
```html
<p>This is <em>emphasized text</em> and this is <i>italic text</i>.</p>
```

### `<u>`
Underlines text.
```html
<p>This text is <u>underlined</u>.</p>
```

### `<small>`
Makes text smaller than the surrounding text.
```html
<p>Regular text <small>smaller text</small> regular text.</p>
```

### `<mark>`
Highlights text with a background color.
```html
<p>This is <mark>highlighted text</mark> in a paragraph.</p>
```

### `<sub>` and `<sup>`
Create subscript and superscript text.
```html
<p>H<sub>2</sub>O (water) and E=mc<sup>2</sup> (Einstein's equation)</p>
```

### `<del>` and `<ins>`
Show deleted and inserted text.
```html
<p>The price is <del>$100</del> <ins>$80</ins>.</p>
```

## List Tags

### `<ul>` and `<li>`
Create unordered (bulleted) lists.
```html
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

### `<ol>` and `<li>`
Create ordered (numbered) lists.
```html
<ol>
  <li>Step one</li>
  <li>Step two</li>
  <li>Step three</li>
</ol>
```

### `<dl>`, `<dt>`, and `<dd>`
Create description lists with terms and definitions.
```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

## Link and Navigation Tags

### `<a>`
Creates hyperlinks to other pages or sections.
```html
<a href="https://example.com">External link</a>
<a href="page.html">Internal link</a>
<a href="#section1">Link to section on same page</a>
<a href="mailto:email@example.com">Email link</a>
```

### `<nav>`
Defines a navigation section.
```html
<nav>
  <ul>
    <li><a href="home.html">Home</a></li>
    <li><a href="about.html">About</a></li>
    <li><a href="contact.html">Contact</a></li>
  </ul>
</nav>
```

## Image and Media Tags

### `<img>`
Embeds images (self-closing tag).
```html
<img src="image.jpg" alt="Description of image" width="300" height="200">
```

### `<figure>` and `<figcaption>`
Groups media content with its caption.
```html
<figure>
  <img src="chart.png" alt="Sales chart">
  <figcaption>Monthly sales data for 2023</figcaption>
</figure>
```

### `<video>`
Embeds video content.
```html
<video controls width="400">
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.webm" type="video/webm">
  Your browser doesn't support video.
</video>
```

### `<audio>`
Embeds audio content.
```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
  <source src="audio.ogg" type="audio/ogg">
  Your browser doesn't support audio.
</audio>
```

## Table Tags

### `<table>`, `<tr>`, `<td>`, `<th>`
Create tables with rows, cells, and headers.
```html
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
      <th>City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>25</td>
      <td>New York</td>
    </tr>
    <tr>
      <td>Jane</td>
      <td>30</td>
      <td>London</td>
    </tr>
  </tbody>
</table>
```

### `<thead>`, `<tbody>`, `<tfoot>`
Group table sections for better structure.
```html
<table>
  <thead>
    <tr><th>Product</th><th>Price</th></tr>
  </thead>
  <tbody>
    <tr><td>Laptop</td><td>$999</td></tr>
    <tr><td>Phone</td><td>$599</td></tr>
  </tbody>
  <tfoot>
    <tr><td>Total</td><td>$1598</td></tr>
  </tfoot>
</table>
```

### `<caption>`
Provides a table caption.
```html
<table>
  <caption>Employee Information</caption>
  <tr>
    <th>Name</th>
    <th>Department</th>
  </tr>
</table>
```

## Form Tags

### `<form>`
Creates a form for user input.
```html
<form action="/submit" method="post">
  <!-- Form elements go here -->
</form>
```

### `<input>`
Creates various input fields (self-closing tag).
```html
<input type="text" name="username" placeholder="Enter username">
<input type="password" name="password">
<input type="email" name="email">
<input type="number" name="age" min="1" max="100">
<input type="checkbox" name="subscribe" id="sub">
<input type="radio" name="gender" value="male" id="male">
<input type="submit" value="Submit">
```

### `<textarea>`
Creates a multi-line text input.
```html
<textarea name="message" rows="4" cols="50" placeholder="Enter your message"></textarea>
```

### `<select>` and `<option>`
Create dropdown menus.
```html
<select name="country">
  <option value="us">United States</option>
  <option value="uk">United Kingdom</option>
  <option value="ca">Canada</option>
</select>
```

### `<label>`
Associates a label with a form control.
```html
<label for="username">Username:</label>
<input type="text" id="username" name="username">

<!-- Or wrap the input -->
<label>
  Password:
  <input type="password" name="password">
</label>
```

### `<button>`
Creates clickable buttons.
```html
<button type="submit">Submit Form</button>
<button type="button" onclick="alert('Hello!')">Click Me</button>
<button type="reset">Reset Form</button>
```

### `<fieldset>` and `<legend>`
Group related form elements.
```html
<fieldset>
  <legend>Personal Information</legend>
  <label>Name: <input type="text" name="name"></label>
  <label>Email: <input type="email" name="email"></label>
</fieldset>
```

## Semantic HTML5 Tags

### `<header>`
Defines the header section of a page or section.
```html
<header>
  <h1>Website Title</h1>
  <nav>
    <a href="home.html">Home</a>
    <a href="about.html">About</a>
  </nav>
</header>
```

### `<main>`
Defines the main content area of a page.
```html
<main>
  <h1>Page Title</h1>
  <p>Main content goes here.</p>
</main>
```

### `<section>`
Defines a distinct section of content.
```html
<section>
  <h2>About Us</h2>
  <p>Information about the company.</p>
</section>
```

### `<article>`
Defines independent, self-contained content.
```html
<article>
  <h2>Blog Post Title</h2>
  <p>Posted on <time datetime="2023-12-01">December 1, 2023</time></p>
  <p>Blog post content...</p>
</article>
```

### `<aside>`
Defines content aside from the main content (sidebar).
```html
<aside>
  <h3>Related Links</h3>
  <ul>
    <li><a href="link1.html">Related Article 1</a></li>
    <li><a href="link2.html">Related Article 2</a></li>
  </ul>
</aside>
```

### `<footer>`
Defines the footer section of a page or section.
```html
<footer>
  <p>&copy; 2023 Company Name. All rights reserved.</p>
  <address>
    Contact us at <a href="mailto:info@example.com">info@example.com</a>
  </address>
</footer>
```

## Generic Container Tags

### `<div>`
A generic block-level container for styling and layout.
```html
<div class="container">
  <div class="sidebar">Sidebar content</div>
  <div class="main-content">Main content</div>
</div>
```

### `<span>`
A generic inline container for styling small portions of text.
```html
<p>This is <span class="highlight">highlighted text</span> in a paragraph.</p>
```

## Quote and Citation Tags

### `<blockquote>`
Defines a block quotation from another source.
```html
<blockquote cite="https://example.com">
  <p>To be or not to be, that is the question.</p>
</blockquote>
```

### `<q>`
Defines a short inline quotation.
```html
<p>Shakespeare wrote <q>All the world's a stage</q>.</p>
```

### `<cite>`
Defines the title of a creative work.
```html
<p>I just read <cite>The Great Gatsby</cite> by F. Scott Fitzgerald.</p>
```

## Code and Technical Tags

### `<code>`
Defines inline computer code.
```html
<p>Use the <code>console.log()</code> function to debug JavaScript.</p>
```

### `<pre>`
Preserves whitespace and formatting (preformatted text).
```html
<pre>
function hello() {
    console.log("Hello, World!");
}
</pre>
```

### `<kbd>`
Defines keyboard input.
```html
<p>Press <kbd>Ctrl</kbd> + <kbd>C</kbd> to copy.</p>
```

### `<samp>`
Defines sample output from a computer program.
```html
<p>The program output was: <samp>Hello, World!</samp></p>
```

### `<var>`
Defines a variable in programming or mathematical context.
```html
<p>The formula is <var>y</var> = <var>mx</var> + <var>b</var>.</p>
```

## Other Useful Tags

### `<time>`
Defines a specific time or date.
```html
<p>The event is on <time datetime="2023-12-25">Christmas Day</time>.</p>
<p>Posted <time datetime="2023-12-01T14:30">today at 2:30 PM</time>.</p>
```

### `<address>`
Defines contact information for the author or owner.
```html
<address>
  Written by <a href="mailto:author@example.com">John Doe</a><br>
  123 Main Street<br>
  Anytown, USA 12345
</address>
```

### `<abbr>`
Defines an abbreviation or acronym.
```html
<p>The <abbr title="World Wide Web">WWW</abbr> was invented in 1989.</p>
```

### `<details>` and `<summary>`
Create collapsible content sections.
```html
<details>
  <summary>Click to expand</summary>
  <p>This content is hidden by default and can be toggled.</p>
</details>
```

### `<progress>`
Shows the progress of a task.
```html
<progress value="70" max="100">70%</progress>
```

### `<meter>`
Displays a scalar measurement within a known range.
```html
<meter value="6" min="0" max="10">6 out of 10</meter>
<meter value="0.8">80%</meter>
```

This comprehensive guide covers the most commonly used HTML tags. Each tag serves a specific purpose in structuring and presenting web content, and many can be combined with CSS for styling and JavaScript for interactivity.
