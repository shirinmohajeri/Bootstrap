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
