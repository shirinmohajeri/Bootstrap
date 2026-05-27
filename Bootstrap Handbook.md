# Bootstrap 5 Notes

These notes are for reviewing Bootstrap when building a project.

---

## 1. Add Bootstrap to HTML

Use Bootstrap CDN inside your HTML file.

### CSS goes inside `<head>`

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet">
```

### JavaScript goes before `</body>`

```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
```

Basic structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet">
  <link rel="stylesheet" href="style.css">

  <title>Bootstrap Project</title>
</head>

<body>

  <!-- Page content here -->

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

---

## 2. Bootstrap 5 Important Changes

Some old Bootstrap 4 code does not work in Bootstrap 5.

| Bootstrap 4 | Bootstrap 5 |
|---|---|
| `data-toggle` | `data-bs-toggle` |
| `data-target` | `data-bs-target` |
| `float-right` | `float-end` |
| `float-left` | `float-start` |
| `btn-block` | `w-100` |
| `ml-3` | `ms-3` |
| `mr-3` | `me-3` |
| `jumbotron` | removed |

---

## 3. Containers

A container keeps content aligned and gives space from left and right.

```html
<div class="container">
  <h1>Hello Bootstrap</h1>
</div>
```

Use it when you want your content to look clean and centered.

---

## 4. Grid System

Bootstrap uses a 12-column grid system.

Basic structure:

```html
<div class="container">
  <div class="row">
    <div class="col-md-6">Left column</div>
    <div class="col-md-6">Right column</div>
  </div>
</div>
```

Meaning:

| Class | Screen Size |
|---|---|
| `col-` | extra small |
| `col-sm-` | small screen, 576px and up |
| `col-md-` | medium screen, 768px and up |
| `col-lg-` | large screen, 992px and up |
| `col-xl-` | extra large screen, 1200px and up |

Example:

```html
<div class="row">
  <div class="col-md-4">Column 1</div>
  <div class="col-md-4">Column 2</div>
  <div class="col-md-4">Column 3</div>
</div>
```

`4 + 4 + 4 = 12`, so three equal columns.

---

## 5. Column Offset

Offset moves a column to the right.

```html
<div class="col-md-3 offset-5">
  Centered content
</div>
```

Use offset when you want to add empty space before a column.

---

## 6. Responsive Images

A responsive image changes size depending on the screen size.

Use:

```html
<img class="img-fluid" src="image.jpg" alt="Image">
```

Bootstrap adds:

```css
max-width: 100%;
height: auto;
```

This means:
- image does not go outside the screen
- image keeps correct proportions
- image becomes smaller on mobile

### Image Styling

```html
<img class="img-fluid rounded shadow" src="image.jpg" alt="Image">
```

| Class | Meaning |
|---|---|
| `img-fluid` | responsive image |
| `rounded` | rounded corners |
| `rounded-5` | more rounded corners |
| `rounded-circle` | circle image |
| `shadow` | shadow effect |
| `float-end` | move image to the right |

---

## 7. Code, Pre, Kbd, and Samp Tags

### `<code>`

Used to show small code text.

```html
<p>Use <code>img-fluid</code> for responsive images.</p>
```

### `<pre>`

Used to keep spaces and line breaks.

```html
<pre>
Hello       World
</pre>
```

### `<pre>` + `<code>`

Used to show code blocks inside a webpage.

```html
<pre>
  <code>
&lt;h1&gt;Hello&lt;/h1&gt;
  </code>
</pre>
```

Important:

```html
&lt;
```

means `<`

```html
&gt;
```

means `>`

### `<kbd>`

Used to show keyboard keys.

```html
<p>Press <kbd>Ctrl</kbd> + <kbd>P</kbd> to print.</p>
```

### `<samp>`

Used to show computer or terminal output.

```html
<samp>File not found</samp>
```

---

## 8. Tables

Basic Bootstrap table:

```html
<table class="table">
  <thead>
    <tr>
      <th>Firstname</th>
      <th>Lastname</th>
      <th>Email</th>
    </tr>
  </thead>

  <tr>
    <td>John</td>
    <td>Doe</td>
    <td>john@example.com</td>
  </tr>
</table>
```

Useful table classes:

| Class | Meaning |
|---|---|
| `table` | basic Bootstrap table |
| `table-dark` | dark table |
| `table-primary` | blue table |
| `table-bordered` | table borders |
| `table-success` | green row |
| `table-danger` | red row |

Example:

```html
<table class="table table-primary table-bordered">
  <tr class="table-danger">
    <td>John</td>
    <td>Doe</td>
    <td>john@example.com</td>
  </tr>
</table>
```

---

## 9. Buttons

Bootstrap buttons need two classes:

```html
<button class="btn btn-primary">Click Me</button>
```

`btn` creates button style.  
`btn-primary` gives the color.

### Button Colors

```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-danger">Danger</button>
<button class="btn btn-warning">Warning</button>
<button class="btn btn-info">Info</button>
<button class="btn btn-light">Light</button>
<button class="btn btn-dark">Dark</button>
```

### `btn-danger`

Usually red. Use for dangerous actions:

```html
<button class="btn btn-danger">Delete</button>
```

Examples:
- Delete
- Remove
- Cancel
- Error action

### `btn-dark`

Usually black/dark gray. Use for simple dark style:

```html
<button class="btn btn-dark">Read More</button>
```

### Full-Width Button

Bootstrap 5 uses:

```html
<button class="btn btn-primary w-100">Click Me</button>
```

Do not use old Bootstrap 4:

```html
btn-block
```

---

## 10. Dropdown Menu

In Bootstrap 5, use:

```html
data-bs-toggle="dropdown"
```

Example:

```html
<div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown">
    Class
  </button>

  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">English Class</a></li>
    <li><a class="dropdown-item" href="#">Italian Class</a></li>
    <li><a class="dropdown-item" href="#">German Class</a></li>
  </ul>
</div>
```

Important:

```html
data-toggle="dropdown"
```

is Bootstrap 4 and does not work in Bootstrap 5.

---

## 11. Input Groups

Input groups are used for search bars, amount fields, and buttons inside input fields.

### Search Input

```html
<div class="input-group">
  <input type="text" class="form-control" placeholder="Search here">
  <button class="btn btn-success" type="submit">Search</button>
</div>
```

### Amount Input

```html
<div class="input-group input-group-sm">
  <span class="input-group-text">$</span>
  <input type="text" class="form-control" placeholder="Enter Amount">
  <span class="input-group-text">$</span>
</div>
```

---

## 12. Jumbotron / Hero Section

In Bootstrap 4, `jumbotron` was used to show a big important message.

Example in Bootstrap 4:

```html
<div class="jumbotron">
  <h1>This is heading</h1>
  <p>This is a description</p>
</div>
```

But in Bootstrap 5, `jumbotron` was removed.

Use this instead:

```html
<div class="container bg-light p-5 rounded shadow">
  <h1 class="display-6">This is heading</h1>
  <p class="lead">This is a description about the heading</p>
</div>
```

Meaning:

| Class | Meaning |
|---|---|
| `bg-light` | light background |
| `p-5` | padding |
| `rounded` | rounded corners |
| `shadow` | shadow effect |
| `display-6` | large heading |
| `lead` | larger paragraph text |

---

## 13. Cards

Cards are useful for creating clean content boxes.

```html
<div class="card shadow">
  <div class="card-body">
    <h5 class="card-title">Grid System</h5>
    <p class="card-text">I practiced containers, rows, and columns.</p>
  </div>
</div>
```

Useful card classes:

| Class | Meaning |
|---|---|
| `card` | creates card |
| `card-body` | content area |
| `card-title` | card heading |
| `card-text` | card paragraph |
| `shadow` | shadow effect |
| `h-100` | full height card |

---

## 14. Spacing Classes

Bootstrap spacing classes are very useful.

Examples:

```html
mt-5
mb-4
py-5
p-5
```

Meaning:

| Class | Meaning |
|---|---|
| `m` | margin |
| `p` | padding |
| `t` | top |
| `b` | bottom |
| `s` | start / left |
| `e` | end / right |
| `x` | left and right |
| `y` | top and bottom |

Examples:

```html
<div class="mt-5">Margin top</div>
<div class="mb-4">Margin bottom</div>
<div class="p-5">Padding all sides</div>
<div class="py-5">Padding top and bottom</div>
```

---

## 15. Simple Project Page Example

```html
<section class="hero text-center text-white">
  <div class="container">
    <h1 class="display-4 fw-bold">Bootstrap 5 Practice Project</h1>
    <p class="lead">A beginner project for practicing Bootstrap layout, components, and utilities.</p>
    <a href="#topics" class="btn btn-light mt-3">View My Practice</a>
  </div>
</section>
```

CSS:

```css
.hero {
  background: linear-gradient(135deg, #6610f2, #0d6efd);
  padding: 100px 0;
}

.card {
  border: none;
  border-radius: 20px;
}

.card:hover {
  transform: translateY(-5px);
  transition: 0.3s;
}

footer {
  background-color: #212529;
}
```

---

## 16. Best Project Structure

```text
Bootstrap-Project/
│
├── index.html
├── style.css
├── README.md
└── notes.md
```

---

## 17. Quick Checklist Before Starting a Bootstrap Project

- Add Bootstrap CSS in `<head>`
- Add custom `style.css` after Bootstrap CSS
- Add Bootstrap JS before `</body>`
- Use `container`
- Use `row`
- Use `col`
- Use `img-fluid` for images
- Use `data-bs-toggle` for dropdowns
- Use `w-100` instead of `btn-block`
- Use Bootstrap 5 classes, not old Bootstrap 4 classes
- 
 ---
 ---

## 18. Cards: Card Body, Card Title, and Links

Bootstrap cards are used to create clean content boxes for websites.

Cards are very useful for:

- Product sections
- Blog posts
- Portfolio projects
- User profiles
- Dashboard widgets

---

### Basic Card Structure

```html
<div class="card" style="width: 18rem;">

  <div class="card-body">

    <h5 class="card-title">
      Card Title
    </h5>

    <p class="card-text">
      This is a simple Bootstrap card example.
    </p>

    <a href="#" class="btn btn-primary">
      Read More
    </a>

  </div>

</div>
```

---

## Important Card Classes

| Class | Meaning |
|---|---|
| `card` | Creates the card container |
| `card-body` | Main content area inside the card |
| `card-title` | Card heading/title |
| `card-text` | Paragraph text inside card |
| `btn` | Bootstrap button |
| `btn-primary` | Blue button style |

---

## What is `card-body`?

`card-body` is the section where we put:

- title
- text
- buttons
- links
- content

Example:

```html
<div class="card-body">
   Content here
</div>
```

Without `card-body`, the content will not have proper spacing and styling.

---

## What is `card-title`?

Used for the main heading inside the card.

Example:

```html
<h5 class="card-title">
   Bootstrap Card
</h5>
```

Usually used for:
- product names
- course titles
- blog titles
- project names

---

## What is Card Link?

Links inside cards are usually buttons or clickable text.

Example:

```html
<a href="#" class="btn btn-primary">
   Read More
</a>
```

This creates a Bootstrap button link.

---

## Card With Shadow

```html
<div class="card shadow" style="width: 18rem;">
```

`shadow` adds a shadow effect around the card.

---

## Card With Image

```html
<div class="card" style="width: 18rem;">

   <img src="image.jpg" class="card-img-top">

   <div class="card-body">

      <h5 class="card-title">
         Nature Image
      </h5>

      <p class="card-text">
         This is a Bootstrap card with image.
      </p>

      <a href="#" class="btn btn-success">
         Explore
      </a>

   </div>

</div>
```

---

## Useful Card Classes

| Class | Meaning |
|---|---|
| `card-img-top` | Image on top of card |
| `shadow` | Shadow effect |
| `rounded` | Rounded corners |
| `h-100` | Equal card height |
| `text-center` | Center text |
| `bg-dark` | Dark background |
| `text-white` | White text |

---

## Example: Dark Card

```html
<div class="card bg-dark text-white shadow">

   <div class="card-body">

      <h5 class="card-title">
         Dark Card
      </h5>

      <p class="card-text">
         Bootstrap dark card example.
      </p>

   </div>

</div>
```

---

## Visualization

```text
+----------------------+
|      Image           |
|----------------------|
|   Card Title         |
|   Card Description   |
|                      |
|   [ Read More ]      |
+----------------------+
```

---

## When to Use Cards

Cards are commonly used for:

- ecommerce products
- portfolio projects
- blog sections
- service boxes
- dashboard widgets
- course cards
- pricing cards
- ---
---

## 19. Card List Group

Bootstrap provides `list-group` to create organized lists inside cards.

List groups are useful for:

- product features
- menu lists
- task lists
- pricing details
- dashboard items

---

## Basic List Group

```html
<ul class="list-group">
   <li class="list-group-item">Item 1</li>
   <li class="list-group-item">Item 2</li>
   <li class="list-group-item">Item 3</li>
</ul>
```

---

## Explanation

| Class | Meaning |
|---|---|
| `list-group` | Creates the list container |
| `list-group-item` | Creates each list item |

---

## Card With List Group

```html
<div class="card" style="width: 18rem;">

   <div class="card-body">

      <h5 class="card-title">
         Laptop Features
      </h5>

      <p class="card-text">
         Basic laptop information
      </p>

   </div>

   <ul class="list-group list-group-flush">

      <li class="list-group-item">
         Intel Core i7
      </li>

      <li class="list-group-item">
         16GB RAM
      </li>

      <li class="list-group-item">
         512GB SSD
      </li>

   </ul>

</div>
```

---

## Important Classes

| Class | Meaning |
|---|---|
| `list-group` | Creates list container |
| `list-group-item` | Creates list item |
| `list-group-flush` | Removes outer borders and connects list smoothly to card |

---

## What is `list-group-flush`?

`list-group-flush` removes extra spacing and borders around the list.

Without it:

```text
List has extra outer border
```

With it:

```text
List fits smoothly inside card
```

---

## Colored List Items

Bootstrap allows colored list items.

Example:

```html
<ul class="list-group">

   <li class="list-group-item list-group-item-primary">
      Primary Item
   </li>

   <li class="list-group-item list-group-item-success">
      Success Item
   </li>

   <li class="list-group-item list-group-item-danger">
      Danger Item
   </li>

</ul>
```

---

## List Group Colors

| Class | Color |
|---|---|
| `list-group-item-primary` | blue |
| `list-group-item-success` | green |
| `list-group-item-danger` | red |
| `list-group-item-warning` | yellow |
| `list-group-item-dark` | dark |

---

## List Group With Active Item

```html
<ul class="list-group">

   <li class="list-group-item active">
      Active Item
   </li>

   <li class="list-group-item">
      Second Item
   </li>

</ul>
```

`active` highlights the selected item.

---

## Visualization

```text
+----------------------+
|   Laptop Features    |
|----------------------|
| Intel Core i7        |
| 16GB RAM             |
| 512GB SSD            |
+----------------------+
```

---

## When to Use List Groups

Use list groups for:

- feature lists
- menu sections
- settings lists
- notifications
- dashboard items
- product specifications
- task management
- ---
---

## 20. Card Header & Footer

Bootstrap cards can also contain:

- card header
- card footer

These sections help organize the card structure.

---

## Basic Card Header & Footer

```html
<div class="card" style="width: 18rem;">

   <div class="card-header">
      Featured
   </div>

   <div class="card-body">

      <h5 class="card-title">
         Special Title
      </h5>

      <p class="card-text">
         This is a description inside the card body.
      </p>

      <a href="#" class="btn btn-primary">
         Learn More
      </a>

   </div>

   <div class="card-footer">
      Card Footer
   </div>

</div>
```

---

## Important Classes

| Class | Meaning |
|---|---|
| `card-header` | Top section of the card |
| `card-body` | Main content area |
| `card-footer` | Bottom section of the card |

---

## What is `card-header`?

`card-header` creates the top area of the card.

Usually used for:

- category name
- notifications
- labels
- menu title
- featured section

Example:

```html
<div class="card-header">
   Featured
</div>
```

---

## What is `card-footer`?

`card-footer` creates the bottom area of the card.

Usually used for:

- buttons
- dates
- links
- additional information
- status

Example:

```html
<div class="card-footer">
   Updated 2 days ago
</div>
```

---

## Card With Header, Body, and Footer

```html
<div class="card shadow" style="width: 20rem;">

   <div class="card-header bg-dark text-white">
      Laptop Product
   </div>

   <div class="card-body">

      <h5 class="card-title">
         XYZ Computer
      </h5>

      <p class="card-text">
         High performance laptop for developers.
      </p>

      <a href="#" class="btn btn-success">
         Buy Now
      </a>

   </div>

   <div class="card-footer text-muted">
      Last updated 2 days ago
   </div>

</div>
```

---

## Explanation of Extra Classes

| Class | Meaning |
|---|---|
| `shadow` | Adds shadow effect |
| `bg-dark` | Dark background |
| `text-white` | White text color |
| `text-muted` | Light gray text |

---

## Visualization

```text
+--------------------------+
|      Laptop Product      |  ← card-header
|--------------------------|
| XYZ Computer             |
| High performance laptop  |
| [ Buy Now ]              |
|--------------------------|
| Last updated 2 days ago  |  ← card-footer
+--------------------------+
```

---

## When to Use Header & Footer

Use card headers and footers for:

- product cards
- blog posts
- notifications
- dashboards
- pricing cards
- ecommerce websites
- admin panels
- profile cards
- --
---

## 21. Align Text Inside Card

Bootstrap provides text alignment classes to control the position of text inside a card.

---

## Text Alignment Classes

| Class | Meaning |
|---|---|
| `text-start` | Align text to the left |
| `text-center` | Align text to the center |
| `text-end` | Align text to the right |

---

## Card With Center Text

```html
<div class="card text-center" style="width: 18rem;">

   <div class="card-body">

      <h5 class="card-title">
         Center Card
      </h5>

      <p class="card-text">
         This card text is aligned in the center.
      </p>

      <a href="#" class="btn btn-primary">
         Learn More
      </a>

   </div>

</div>
```

---

## Card With Right Text

```html
<div class="card text-end" style="width: 18rem;">

   <div class="card-body">

      <h5 class="card-title">
         Right Card
      </h5>

      <p class="card-text">
         This card text is aligned to the right.
      </p>

      <a href="#" class="btn btn-dark">
         Read More
      </a>

   </div>

</div>
```

---

## Card With Left Text

```html
<div class="card text-start" style="width: 18rem;">

   <div class="card-body">

      <h5 class="card-title">
         Left Card
      </h5>

      <p class="card-text">
         This card text is aligned to the left.
      </p>

      <a href="#" class="btn btn-success">
         Start
      </a>

   </div>

</div>
```

---

## Important Note

Put the alignment class on the main card:

```html
<div class="card text-center">
```

or inside `card-body`:

```html
<div class="card-body text-center">
```

Both work.

---

## Visualization

```text
text-start

+----------------------+
| Title                |
| Description text     |
| [Button]             |
+----------------------+

text-center

+----------------------+
|        Title         |
|   Description text   |
|       [Button]       |
+----------------------+

text-end

+----------------------+
|                Title |
|     Description text |
|             [Button] |
+----------------------+
```

---

## When to Use

Use text alignment inside cards for:

- pricing cards
- product cards
- profile cards
- dashboard widgets
- portfolio sections
---
---

## 22. Card Image Overlay (Top & Bottom Text)

Bootstrap provides:

```html
card-img-overlay
```

to place text directly on top of an image.

This is useful for:

- banners
- hero sections
- product advertisements
- portfolio cards
- featured content

---

## Basic Card Image Overlay

```html
<div class="card text-white">

   <img 
      class="card-img"
      src="image.jpg"
      alt="Card image">

   <div class="card-img-overlay">

      <h5 class="card-title">
         This is the title
      </h5>

      <p class="card-text">
         This is a paragraph
      </p>

   </div>

</div>
```

---

## Important Classes

| Class | Meaning |
|---|---|
| `card` | Creates card container |
| `card-img` | Full image inside card |
| `card-img-overlay` | Places content over image |
| `card-title` | Title text |
| `card-text` | Paragraph text |
| `text-white` | White text color |

---

## What is `card-img-overlay`?

`card-img-overlay` allows us to place text on top of the image.

Example:

```html
<div class="card-img-overlay">
   Content here
</div>
```

Without it:

```text
Text appears under image
```

With it:

```text
Text appears on top of image
```

---

## Important Structure

Correct structure:

```html
<div class="card">

   <img class="card-img">

   <div class="card-img-overlay">
      Text here
   </div>

</div>
```

`card-img-overlay` must be inside `.card`.

---

## Overlay Text at Top

By default, overlay text appears near the top.

Example:

```html
<div class="card-img-overlay">

   <h5 class="card-title">
      Coffee Title
   </h5>

   <p class="card-text">
      Coffee description
   </p>

</div>
```

---

## Overlay Text at Bottom

We can move overlay text to the bottom using flexbox utilities.

Example:

```html
<div class="card text-white">

   <img class="card-img" src="image.jpg">

   <div class="card-img-overlay d-flex flex-column justify-content-end">

      <h5 class="card-title">
         Coffee Title
      </h5>

      <p class="card-text">
         Coffee description
      </p>

   </div>

</div>
```

---

## Explanation of Extra Classes

| Class | Meaning |
|---|---|
| `d-flex` | Activates flexbox |
| `flex-column` | Vertical layout |
| `justify-content-end` | Moves content to bottom |

---

## Visualization

### Top Overlay

```text
+--------------------------+
| Title                    |
| Paragraph                |
|                          |
|          Image           |
|                          |
+--------------------------+
```

---

### Bottom Overlay

```text
+--------------------------+
|                          |
|          Image           |
|                          |
| Title                    |
| Paragraph                |
+--------------------------+
```

---

## Better Styled Example

```html
<div class="card text-white shadow">

   <img 
      class="card-img"
      src="image.jpg">

   <div class="card-img-overlay d-flex flex-column justify-content-end">

      <h5 class="card-title">
         Coffee Product
      </h5>

      <p class="card-text">
         Fresh coffee with beautiful presentation.
      </p>

   </div>

</div>
```
---

## Important Note

If the text is difficult to read on the image:

- use `text-white`
- use darker images
- add background overlay later with CSS

---

## When to Use Card Image Overlay

Use overlays for:

- hero banners
- advertisements
- product highlights
- featured blog posts
- portfolio showcases
- landing pages
- ecommerce cards
---
---

## 23. Card Colors

Bootstrap provides color utility classes to change the background and text colors of cards.

Card colors are useful for:

- alerts
- notifications
- pricing cards
- dashboards
- product highlights
- status cards

---

## Basic Colored Card

```html
<div class="card bg-primary text-white" style="width: 18rem;">

   <div class="card-body">

      <h5 class="card-title">
         Primary Card
      </h5>

      <p class="card-text">
         This is a Bootstrap primary card.
      </p>

   </div>

</div>
```

---

## Important Classes

| Class | Meaning |
|---|---|
| `bg-primary` | Blue background |
| `bg-success` | Green background |
| `bg-danger` | Red background |
| `bg-warning` | Yellow background |
| `bg-info` | Light blue background |
| `bg-dark` | Dark background |
| `bg-light` | Light background |
| `text-white` | White text color |
| `text-dark` | Dark text color |

---

## Common Card Colors

### Primary Card

```html
<div class="card bg-primary text-white">
```

Used for:
- main content
- important information

---

### Success Card

```html
<div class="card bg-success text-white">
```

Used for:
- success messages
- completed actions

---

### Danger Card

```html
<div class="card bg-danger text-white">
```

Used for:
- errors
- warnings
- delete actions

---

### Warning Card

```html
<div class="card bg-warning text-dark">
```

Used for:
- alerts
- notifications
- warnings

Important:

```html
text-dark
```

is better because yellow background is very bright.

---

### Dark Card

```html
<div class="card bg-dark text-white">
```

Used for:
- dark UI
- dashboards
- modern layouts

---

## Multiple Color Examples

```html
<div class="card bg-primary text-white mb-3">
   <div class="card-body">
      <h5 class="card-title">Primary Card</h5>
   </div>
</div>

<div class="card bg-success text-white mb-3">
   <div class="card-body">
      <h5 class="card-title">Success Card</h5>
   </div>
</div>

<div class="card bg-danger text-white mb-3">
   <div class="card-body">
      <h5 class="card-title">Danger Card</h5>
   </div>
</div>
```

---

## Explanation of Extra Class

| Class | Meaning |
|---|---|
| `mb-3` | Margin bottom |

Used to add space between cards.

---

## Visualization

```text
+----------------------+
|  Primary Card        |
|  Blue Background     |
+----------------------+

+----------------------+
|  Success Card        |
|  Green Background    |
+----------------------+

+----------------------+
|  Danger Card         |
|  Red Background      |
+----------------------+
```

---

## Combining With Other Classes

We can combine colors with:

```html
shadow
rounded
text-center
```

Example:

```html
<div class="card bg-dark text-white shadow rounded text-center">

   <div class="card-body">

      <h5 class="card-title">
         Dark Card
      </h5>

      <p class="card-text">
         Bootstrap dark card example.
      </p>

   </div>

</div>
```

---

## Important Note

Always make sure the text color is readable.

Examples:

```html
bg-dark + text-white
bg-warning + text-dark
```

Good contrast is important.

---

## When to Use Colored Cards

Use colored cards for:

- dashboard statistics
- pricing sections
- notifications
- warning messages
- ecommerce products
- admin panels
- portfolio sections
---
---

## 24. Card Groups & Decks

Bootstrap allows multiple cards to be displayed together using:

- card groups
- card decks

These are useful for creating:

- product sections
- pricing layouts
- portfolio cards
- blog cards
- dashboard cards

---

## What is a Card Group?

`card-group` combines multiple cards into one connected layout.

All cards automatically get:

- equal height
- equal width
- connected structure

---

## Basic Card Group

```html
<div class="card-group">

   <div class="card">

      <div class="card-body">

         <h5 class="card-title">
            Card 1
         </h5>

         <p class="card-text">
            This is first card.
         </p>

      </div>

   </div>

   <div class="card">

      <div class="card-body">

         <h5 class="card-title">
            Card 2
         </h5>

         <p class="card-text">
            This is second card.
         </p>

      </div>

   </div>

</div>
```

---

## Important Classes

| Class | Meaning |
|---|---|
| `card-group` | Groups cards together |
| `card` | Individual card |
| `card-body` | Content area |

---

## What Happens in Card Group?

Bootstrap automatically:
- makes cards same height
- aligns cards evenly
- removes spacing between cards

---

## Visualization

```text
+-------------+-------------+
| Card 1      | Card 2      |
| Text        | Text        |
+-------------+-------------+
```

---

## Card Group With Images

```html
<div class="card-group">

   <div class="card">

      <img class="card-img-top" src="image1.jpg">

      <div class="card-body">

         <h5 class="card-title">
            Laptop
         </h5>

         <p class="card-text">
            Gaming laptop
         </p>

      </div>

   </div>

   <div class="card">

      <img class="card-img-top" src="image2.jpg">

      <div class="card-body">

         <h5 class="card-title">
            Camera
         </h5>

         <p class="card-text">
            Professional camera
         </p>

      </div>

   </div>

</div>
```

---

## What is Card Deck?

In Bootstrap 4:

```html
card-deck
```

was used to create equal width cards with spacing.

Example:

```html
<div class="card-deck">
```

---

## Important Bootstrap 5 Note

Bootstrap 5 removed:

```html
card-deck
```

Instead, Bootstrap 5 recommends using:

```html
row
col
gutter classes
```

Example:

```html
<div class="row g-4">

   <div class="col-md-4">

      <div class="card h-100">

         <div class="card-body">

            <h5 class="card-title">
               Card 1
            </h5>

         </div>

      </div>

   </div>

   <div class="col-md-4">

      <div class="card h-100">

         <div class="card-body">

            <h5 class="card-title">
               Card 2
            </h5>

         </div>

      </div>

   </div>

</div>
```

---

## Explanation of Extra Classes

| Class | Meaning |
|---|---|
| `row` | Bootstrap row |
| `col-md-4` | Responsive column |
| `g-4` | Gutter spacing |
| `h-100` | Equal height cards |

---

## Why Use `h-100`?

```html
h-100
```

makes all cards same height even if content size is different.

---

## Better Bootstrap 5 Layout

Modern Bootstrap projects usually use:

```html
row + col + card
```

instead of old:

```html
card-deck
```

because it is:
- more flexible
- responsive
- easier to control

---

## Visualization

```text
+-------------+   +-------------+   +-------------+
| Card 1      |   | Card 2      |   | Card 3      |
| Text        |   | Text        |   | Text        |
+-------------+   +-------------+   +-------------+
```

---

## When to Use Card Groups

Use grouped cards for:

- ecommerce products
- pricing tables
- portfolio projects
- blog sections
- service sections
- dashboard widgets
- team member cards
---
### Create Space Between Cards

Bootstrap uses:

```html
g-1
g-2
g-3
g-4
g-5
```

to create spacing between cards and columns.

---

## Example

```html
<div class="container">

   <!-- g-4 adds space between cards -->
   <div class="row g-4">

      <div class="col-md-3">

         <div class="card">

            <div class="card-header">
               Header
            </div>

            <div class="card-body">

               <h5 class="card-title">
                  Title
               </h5>

               <p class="card-text">
                  Some text
               </p>

            </div>

         </div>

      </div>

   </div>

</div>
```

---

## Gutter Sizes

| Class | Space Size |
|---|---|
| `g-1` | very small space |
| `g-2` | small space |
| `g-3` | medium space |
| `g-4` | large space |
| `g-5` | very large space |

---

## Horizontal Space Only

```html
<div class="row gx-5">
```

`gx` = horizontal spacing (left and right)

---

## Vertical Space Only

```html
<div class="row gy-5">
```

`gy` = vertical spacing (top and bottom)

---

## Most Common Usage

```html
<div class="row g-4">
```

or

```html
<div class="row g-5">
```

Used for:
- cards
- dashboards
- ecommerce products
- portfolio layouts
- blog sections
  ---
  ---

## 26. Nav Pills

Bootstrap provides `nav-pills` to create navigation links with pill-style active buttons.

---

## Basic Nav Pills Example

```html
<div class="container">

   <ul class="nav nav-pills">

      <li class="nav-item">
         <a class="nav-link" href="#">
            Home
         </a>
      </li>

      <li class="nav-item">
         <a class="nav-link" href="#">
            Contact
         </a>
      </li>

      <li class="nav-item">
         <a class="nav-link" href="#">
            About
         </a>
      </li>

      <li class="nav-item">
         <a class="nav-link active" href="#">
            Product
         </a>
      </li>

   </ul>

</div>
```

---

## Important Classes

| Class | Meaning |
|---|---|
| `nav` | Creates navigation menu |
| `nav-pills` | Creates pill-style navigation |
| `nav-item` | Creates each navigation item |
| `nav-link` | Styles each navigation link |
| `active` | Shows the selected/current page |

---

## What is `nav-pills`?

`nav-pills` makes the active link look like a rounded button.

Example:

```html
<ul class="nav nav-pills">
```

Result:

```text
Home   Contact   About   [ Product ]
```

`Product` is active because it has:

```html
class="nav-link active"
```

---

## Difference Between `nav-tabs` and `nav-pills`

| Class | Look |
|---|---|
| `nav-tabs` | Tab style |
| `nav-pills` | Rounded pill/button style |

Example:

```html
<ul class="nav nav-tabs">
```

```html
<ul class="nav nav-pills">
```

---

## Center Nav Pills

```html
<ul class="nav nav-pills justify-content-center">
```

`justify-content-center` moves the nav to the center.

---

## Right Nav Pills

```html
<ul class="nav nav-pills justify-content-end">
```

`justify-content-end` moves the nav to the right.

---

## Vertical Nav Pills

```html
<ul class="nav nav-pills flex-column">
```

`flex-column` makes the navigation vertical.

---

## When to Use Nav Pills

Use `nav-pills` for:

- website menus
- dashboard tabs
- profile pages
- category filters
- product sections
- admin panels
