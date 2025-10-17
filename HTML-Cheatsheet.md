# Day 2: HTML Essentials Cheat Sheet 📋

## 📚 Table of Contents
- [Learning Objectives](#learning-objectives)
- [Why Semantic HTML Matters](#why-semantic-html-matters)
- [Document Structure Tags](#document-structure-tags)
- [Content Tags](#content-tags)
- [Forms & Input Elements](#forms--input-elements)
- [SEO & Meta Tags](#seo--meta-tags)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Code Examples](#code-examples)
- [Resources](#resources)

---

## 🎯 Learning Objectives

By the end of Day 2, you'll understand:
- ✅ Semantic HTML5 tags and their proper usage
- ✅ Document structure and layout elements
- ✅ Heading hierarchy for SEO and accessibility
- ✅ Forms and input validation
- ✅ SEO meta tags and Open Graph protocol
- ✅ Best practices for accessible, production-ready HTML
- ✅ Common mistakes to avoid

---

## 🌟 Why Semantic HTML Matters

### The Problem with Non-Semantic HTML
```html
<!-- ❌ NON-SEMANTIC (Bad) -->
<div class="header">
  <div class="logo">My Website</div>
  <div class="navigation">
    <div class="nav-item">Home</div>
    <div class="nav-item">About</div>
  </div>
</div>
<div class="content">
  <div class="post">
    <div class="title">Article Title</div>
    <div class="text">Article content...</div>
  </div>
</div>
<div class="footer">
  <div class="copyright">© 2025</div>
</div>
```

**Problems:**
- No semantic meaning (everything is a `<div>`)
- Search engines can't understand structure
- Screen readers struggle to navigate
- Hard for developers to maintain
- Zero accessibility benefits

### The Power of Semantic HTML
```html
<!-- ✅ SEMANTIC (Good) -->
<header>
  <h1>My Website</h1>
  <nav>
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/about">About</a></li>
    </ul>
  </nav>
</header>

<main>
  <article>
    <h2>Article Title</h2>
    <p>Article content...</p>
  </article>
</main>

<footer>
  <p>&copy; 2025 My Website</p>
</footer>
```

**Benefits:**
- ✅ **SEO Boost**: Search engines prioritize well-structured semantic content for better indexing
- ✅ **Accessibility**: Screen readers navigate semantic layouts more effectively
- ✅ **Maintainability**: Self-documenting code that any developer can understand
- ✅ **Performance**: Browsers can optimize rendering with proper structure
- ✅ **Future-proof**: AI agents and voice assistants rely on semantic clarity

---

## 🏗️ Document Structure Tags

### Core Layout Elements

#### `<header>`
**Purpose**: Contains introductory content, logo, navigation
```html
<header>
  <img src="logo.png" alt="Company Logo">
  <nav>
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/about">About</a></li>
      <li><a href="/contact">Contact</a></li>
    </ul>
  </nav>
</header>
```

**Use cases:**
- Site-wide header at top of page
- Section headers within articles
- Header of a modal or card component

---

#### `<nav>`
**Purpose**: Defines navigation links block for site-wide or section-specific navigation
```html
<nav aria-label="Main Navigation">
  <ul>
    <li><a href="/" aria-current="page">Home</a></li>
    <li><a href="/products">Products</a></li>
    <li><a href="/blog">Blog</a></li>
  </ul>
</nav>
```

**Best practices:**
- Use `aria-label` to describe navigation purpose
- Use `aria-current="page"` for active link
- Wrap links in `<ul>` and `<li>` for structure
- Can have multiple `<nav>` elements (main nav, footer nav, sidebar nav)

---

#### `<main>`
**Purpose**: Represents primary content unique to the page, used only once per page
```html
<main>
  <h1>Welcome to My Blog</h1>
  <article>
    <h2>Latest Post</h2>
    <p>Content goes here...</p>
  </article>
</main>
```

**Critical rules:**
- ⚠️ **MUST be used only ONCE per page**
- ⚠️ **Cannot be nested** inside `<header>`, `<footer>`, `<article>`, `<aside>`, or `<nav>`
- ✅ Should contain unique page content
- ✅ Screen readers can skip to main content directly using this tag

---

#### `<article>`
**Purpose**: Self-contained, independent content that makes sense on its own
```html
<article>
  <header>
    <h2>Understanding Semantic HTML</h2>
    <p>Published on <time datetime="2025-01-15">January 15, 2025</time></p>
    <p>By <span class="author">John Doe</span></p>
  </header>
  
  <p>Content of the article...</p>
  
  <footer>
    <p>Tags: <a href="/tag/html">HTML</a>, <a href="/tag/web">Web Dev</a></p>
  </footer>
</article>
```

**When to use `<article>`:**
- ✅ Blog posts
- ✅ News articles
- ✅ Forum posts
- ✅ Product cards
- ✅ User comments
- ✅ Any content that could be syndicated or shared independently

**Test**: "Can this content be distributed on its own (RSS feed, social media) and still make sense?" If yes → use `<article>`

---

#### `<section>`
**Purpose**: Groups related content under a common theme or purpose
```html
<section>
  <h2>Our Services</h2>
  <article>
    <h3>Web Design</h3>
    <p>We create beautiful websites...</p>
  </article>
  <article>
    <h3>SEO Optimization</h3>
    <p>Improve your rankings...</p>
  </article>
</section>
```

**When to use `<section>`:**
- ✅ Thematic grouping of content
- ✅ Chapters in a document
- ✅ Tabs in a tabbed interface
- ✅ Feature sections on a landing page

**Difference: `<section>` vs `<article>`**
- `<section>`: Groups related content (needs context)
- `<article>`: Independent content (standalone)

---

#### `<aside>`
**Purpose**: Content tangentially related to main content
```html
<aside>
  <h3>Related Posts</h3>
  <ul>
    <li><a href="/post1">Post 1</a></li>
    <li><a href="/post2">Post 2</a></li>
  </ul>
</aside>
```

**Use cases:**
- Sidebars
- Pull quotes
- Related links
- Advertisements
- Author bio boxes

---

#### `<footer>`
**Purpose**: Footer information for document or section
```html
<footer>
  <p>&copy; 2025 My Company. All rights reserved.</p>
  <nav aria-label="Footer Navigation">
    <a href="/privacy">Privacy Policy</a>
    <a href="/terms">Terms of Service</a>
  </nav>
  <p>Contact: <a href="mailto:hello@example.com">hello@example.com</a></p>
</footer>
```

**Can contain:**
- Copyright information
- Contact details
- Sitemap links
- Social media links
- Related documents

---

## 📊 Heading Hierarchy

### The SEO and Accessibility Foundation
```html
<h1>Main Page Title</h1> <!-- Only ONE per page -->

<section>
  <h2>Section Title</h2>
  
  <article>
    <h3>Article Heading</h3>
    
    <section>
      <h4>Subsection</h4>
      
      <h5>Minor Heading</h5>
      
      <h6>Smallest Heading</h6>
    </section>
  </article>
</section>
```

### Critical Rules

| Rule | Why It Matters |
|------|----------------|
| Only ONE `<h1>` per page | Critical for SEO—tells search engines the main topic |
| Don't skip levels | Skipping h2 → h4 confuses screen readers |
| Use hierarchical order | h1 → h2 → h3 (parent → child structure) |
| Include target keywords in h1 | Improves search ranking for those terms |
| Use headings for structure, not styling | CSS handles visual appearance |

### Bad Example ❌
```html
<h1>Welcome</h1>
<h1>About Us</h1> <!-- ❌ Two h1 tags -->
<h4>Our Services</h4> <!-- ❌ Skipped h2, h3 -->
<h2>Contact</h2> <!-- ❌ Wrong hierarchy -->
```

### Good Example ✅
```html
<h1>Welcome to TechCorp</h1> <!-- Main topic -->
<h2>About Us</h2> <!-- Section -->
<h3>Our Mission</h3> <!-- Subsection -->
<h3>Our Team</h3> <!-- Subsection -->
<h2>Services</h2> <!-- Section -->
<h3>Web Development</h3> <!-- Service -->
<h3>Mobile Apps</h3> <!-- Service -->
```

---

## 📝 Content Tags

### Text Formatting
```html
<!-- Paragraphs -->
<p>This is a paragraph of text.</p>

<!-- Strong importance (bold) -->
<p>This is <strong>very important</strong> information.</p>

<!-- Emphasis (italic) -->
<p>This is <em>emphasized</em> text.</p>

<!-- Marked/highlighted text -->
<p>Search results: <mark>keyword</mark> found.</p>

<!-- Code snippets -->
<p>Use the <code>console.log()</code> function to debug.</p>

<!-- Preformatted text (preserves spaces and line breaks) -->
<pre>
function greet() {
  console.log("Hello!");
}
</pre>

<!-- Quotations -->
<blockquote cite="https://source.com">
  <p>Long quotation goes here.</p>
  <footer>— Author Name</footer>
</blockquote>

<p>As Einstein said, <q>Imagination is more important than knowledge.</q></p>
```

### Important Distinctions

| Semantic Tag | Visual Tag | When to Use |
|--------------|------------|-------------|
| `<strong>` (important) | `<b>` (bold) | Use `<strong>` for semantic emphasis |
| `<em>` (emphasis) | `<i>` (italic) | Use `<em>` for stress emphasis |
| `<mark>` (highlighted) | `<span>` + CSS | Use `<mark>` for relevant highlighting |

---

## 📋 Lists

### Unordered List (Bullets)
```html
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

### Ordered List (Numbers)
```html
<ol>
  <li>Open terminal</li>
  <li>Run <code>npm install</code></li>
  <li>Start dev server</li>
</ol>
```

### Description List (Key-Value Pairs)
```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
  
  <dt>JavaScript</dt>
  <dd>Programming language for web interactivity</dd>
</dl>
```

### Nested Lists
```html
<ul>
  <li>Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </li>
  <li>Backend
    <ul>
      <li>Node.js</li>
      <li>Python</li>
    </ul>
  </li>
</ul>
```

---

## 🔗 Links & Images

### Links (Anchor Tags)
```html
<!-- External link (opens in new tab) -->
<a href="https://example.com" 
   target="_blank" 
   rel="noopener noreferrer">
  Visit Example
</a>

<!-- Internal link -->
<a href="/about">About Us</a>

<!-- Anchor link (same page) -->
<a href="#section-2">Jump to Section 2</a>

<!-- Email link -->
<a href="mailto:hello@example.com">Email Us</a>

<!-- Phone link -->
<a href="tel:+1234567890">Call Us</a>

<!-- Download link -->
<a href="/files/document.pdf" download>Download PDF</a>
```

**Security Note**: Always use `rel="noopener noreferrer"` with `target="_blank"` to prevent security vulnerabilities.

### Images
```html
<!-- Basic image -->
<img src="photo.jpg" 
     alt="Description for screen readers"
     width="600" 
     height="400">

<!-- Responsive image with lazy loading -->
<img src="large-photo.jpg" 
     alt="Beautiful landscape"
     loading="lazy"
     srcset="small.jpg 480w, 
             medium.jpg 800w, 
             large.jpg 1200w"
     sizes="(max-width: 600px) 480px,
            (max-width: 1000px) 800px,
            1200px">

<!-- Figure with caption -->
<figure>
  <img src="chart.png" alt="Sales growth chart">
  <figcaption>Sales increased by 47% in Q4 2024</figcaption>
</figure>
```

**Accessibility Rule**: Always include `alt` text describing image content for screen readers

---

## 📝 Forms & Input Elements

### Basic Form Structure
```html
<form action="/submit" method="POST">
  <!-- Text input -->
  <label for="name">Full Name:</label>
  <input type="text" 
         id="name" 
         name="name" 
         placeholder="John Doe"
         required>
  
  <!-- Email input (built-in validation) -->
  <label for="email">Email:</label>
  <input type="email" 
         id="email" 
         name="email"
         placeholder="john@example.com"
         required>
  
  <!-- Password -->
  <label for="password">Password:</label>
  <input type="password" 
         id="password" 
         name="password"
         minlength="8"
         required>
  
  <!-- Submit button -->
  <button type="submit">Create Account</button>
</form>
```

**Critical Rule**: Always pair `<label>` with `<input>` using matching `for` and `id` attributes for accessibility.

### Advanced Form Inputs
```html
<!-- Textarea -->
<label for="message">Message:</label>
<textarea id="message" 
          name="message" 
          rows="5" 
          cols="50"
          placeholder="Your message here..."></textarea>

<!-- Select dropdown -->
<label for="country">Country:</label>
<select id="country" name="country" required>
  <option value="">-- Select Country --</option>
  <option value="us">United States</option>
  <option value="uk">United Kingdom</option>
  <option value="ca">Canada</option>
</select>

<!-- Multiple select -->
<select name="skills[]" multiple>
  <option value="html">HTML</option>
  <option value="css">CSS</option>
  <option value="js">JavaScript</option>
</select>

<!-- Checkbox -->
<input type="checkbox" id="subscribe" name="subscribe" value="yes">
<label for="subscribe">Subscribe to newsletter</label>

<!-- Radio buttons (same name = mutual exclusion) -->
<fieldset>
  <legend>Choose your plan:</legend>
  
  <input type="radio" id="free" name="plan" value="free" checked>
  <label for="free">Free</label>
  
  <input type="radio" id="pro" name="plan" value="pro">
  <label for="pro">Pro ($9/month)</label>
  
  <input type="radio" id="enterprise" name="plan" value="enterprise">
  <label for="enterprise">Enterprise</label>
</fieldset>
```

### HTML5 Input Types (Built-in Validation)
```html
<!-- Number input -->
<input type="number" 
       name="age" 
       min="18" 
       max="100" 
       step="1"
       required>

<!-- Date picker -->
<input type="date" 
       name="birthdate" 
       min="1900-01-01" 
       max="2025-12-31">

<!-- Time picker -->
<input type="time" name="appointment">

<!-- Color picker -->
<input type="color" name="theme" value="#ff0000">

<!-- URL validation -->
<input type="url" 
       name="website" 
       placeholder="https://example.com">

<!-- Phone number -->
<input type="tel" 
       name="phone" 
       pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
       placeholder="123-456-7890">

<!-- Search input -->
<input type="search" 
       name="q" 
       placeholder="Search..."
       autofocus>

<!-- File upload -->
<input type="file" 
       name="resume" 
       accept=".pdf,.doc,.docx">

<!-- Range slider -->
<input type="range" 
       name="volume" 
       min="0" 
       max="100" 
       value="50">
```

**Pro Tip**: HTML5 input types provide free browser validation—no JavaScript needed for basic checks!

---

## 🔍 SEO & Meta Tags

### Essential Meta Tags
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <!-- Character encoding (MUST be first) -->
  <meta charset="UTF-8">
  
  <!-- Responsive viewport -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  <!-- Page title (50-60 characters, appears in search results) -->
  <title>HTML Essentials Guide | Learn HTML5 in 2025</title>
  
  <!-- Meta description (150-160 characters, appears in search results) -->
  <meta name="description" content="Complete HTML5 guide covering semantic tags, forms, SEO best practices, and accessibility. Master HTML fundamentals for modern web development.">
  
  <!-- Keywords (less important now, but still used) -->
  <meta name="keywords" content="HTML5, semantic HTML, web development, forms, SEO">
  
  <!-- Author -->
  <meta name="author" content="Your Name">
  
  <!-- Robots (control search engine crawling) -->
  <meta name="robots" content="index, follow">
  
  <!-- Open Graph (Facebook, LinkedIn) -->
  <meta property="og:type" content="website">
  <meta property="og:title" content="HTML Essentials Guide">
  <meta property="og:description" content="Master HTML5 fundamentals for modern web development">
  <meta property="og:image" content="https://yoursite.com/og-image.jpg">
  <meta property="og:url" content="https://yoursite.com/html-guide">
  
  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:site" content="@yourusername">
  <meta name="twitter:title" content="HTML Essentials Guide">
  <meta name="twitter:description" content="Master HTML5 fundamentals">
  <meta name="twitter:image" content="https://yoursite.com/twitter-image.jpg">
  
  <!-- Favicon -->
  <link rel="icon" type="image/png" href="/favicon.png">
  
  <!-- Canonical URL (prevents duplicate content issues) -->
  <link rel="canonical" href="https://yoursite.com/html-guide">
</head>
<body>
  <!-- Content here -->
</body>
</html>
```

### SEO Checklist

| Element | Importance | Best Practice |
|---------|-----------|---------------|
| `<title>` | Critical | 50-60 characters, include main keyword |
| `meta description` | High | 150-160 characters, compelling copy |
| `<h1>` | Critical | One per page, main keyword included |
| Heading hierarchy | High | Logical h1 → h2 → h3 structure |
| `alt` text on images | High | Descriptive, include keywords naturally |
| Semantic HTML | Medium | Use `<article>`, `<section>`, not just `<div>` |
| Internal linking | Medium | Link to related pages on your site |
| `lang` attribute | Medium | `<html lang="en">` helps search engines |
| Mobile-friendly | Critical | Viewport meta tag + responsive design |
| Page speed | Critical | Optimize images, minimize HTML |

---

## ⚡ Best Practices

### 1. Always Use Semantic HTML
```html
<!-- ❌ BAD -->
<div class="article">
  <div class="title">Article Title</div>
  <div class="content">Content here...</div>
</div>

<!-- ✅ GOOD -->
<article>
  <h2>Article Title</h2>
  <p>Content here...</p>
</article>
```

### 2. Proper Form Accessibility
```html
<!-- ❌ BAD (no label association) -->
<label>Name:</label>
<input type="text" name="name">

<!-- ✅ GOOD (proper association) -->
<label for="name">Name:</label>
<input type="text" id="name" name="name">
```

### 3. Image Optimization
```html
<!-- ❌ BAD (missing alt, no lazy loading) -->
<img src="large-image.jpg">

<!-- ✅ GOOD (descriptive alt, lazy loading, dimensions) -->
<img src="large-image.jpg" 
     alt="Developer working on laptop with dual monitors"
     width="1200" 
     height="800"
     loading="lazy">
```

### 4. External Links Security
```html
<!-- ❌ BAD (security risk) -->
<a href="https://external.com" target="_blank">Link</a>

<!-- ✅ GOOD (prevents tabnabbing attack) -->
<a href="https://external.com" 
   target="_blank" 
   rel="noopener noreferrer">Link</a>
```

### 5. Button vs Link
```html
<!-- ❌ BAD (button for navigation) -->
<button onclick="location.href='/page'">Go to page</button>

<!-- ✅ GOOD (link for navigation) -->
<a href="/page">Go to page</a>

<!-- ❌ BAD (link for action) -->
<a href="#" onclick="submitForm()">Submit</a>

<!-- ✅ GOOD (button for action) -->
<button type="button" onclick="submitForm()">Submit</button>
```

**Rule**: 
- Use `<a>` for navigation (going somewhere)
- Use `<button>` for actions (doing something)

---

## 🚨 Common Mistakes to Avoid

### 1. Multiple `<h1>` Tags
```html
<!-- ❌ BAD (confuses search engines) -->
<h1>Welcome</h1>
<h1>About Us</h1>
<h1>Contact</h1>

<!-- ✅ GOOD (single h1, h2 for sections) -->
<h1>Welcome to Our Website</h1>
<h2>About Us</h2>
<h2>Contact</h2>
```

### 2. Skipping Heading Levels
```html
<!-- ❌ BAD (skips h2, h3) -->
<h1>Main Title</h1>
<h4>Section Title</h4>

<!-- ✅ GOOD (proper hierarchy) -->
<h1>Main Title</h1>
<h2>Section Title</h2>
<h3>Subsection Title</h3>
```

### 3. Divitis (Div Soup)
```html
<!-- ❌ BAD (meaningless divs everywhere) -->
<div class="container">
  <div class="header-wrapper">
    <div class="header-content">
      <div class="logo-container">Logo</div>
    </div>
  </div>
</div>

<!-- ✅ GOOD (semantic, minimal markup) -->
<header>
  <img src="logo.png" alt="Company Logo">
</header>
```

### 4. Using Deprecated Tags
```html
<!-- ❌ BAD (deprecated HTML4 tags) -->
<center>Centered text</center>
<font color="red">Red text</font>
<marquee>Scrolling text</marquee>
<blink>Blinking text</blink>

<!-- ✅ GOOD (use CSS for styling) -->
<p style="text-align: center;">Centered text</p>
<p style="color: red;">Red text</p>
<!-- Use CSS animations for movement -->
```

### 5. Incorrect Nesting
```html
<!-- ❌ BAD (block element inside inline element) -->
<span>
  <div>Content</div>
</span>

<!-- ❌ BAD (p cannot contain block elements) -->
<p>
  <div>Content</div>
</p>

<!-- ✅ GOOD (proper nesting) -->
<div>
  <p>Content</p>
</div>
```

### 6. Missing Alt Text
```html
<!-- ❌ BAD (no alt text) -->
<img src="product.jpg">

<!-- ❌ BAD (useless alt text) -->
<img src="product.jpg" alt="image">

<!-- ✅ GOOD (descriptive alt text) -->
<img src="product.jpg" alt="Red Nike running shoes with white sole">
```

### 7. Forms Without Labels
```html
<!-- ❌ BAD (inaccessible) -->
<input type="text" placeholder="Enter name">

<!-- ✅ GOOD (accessible) -->
<label for="name">Name:</label>
<input type="text" id="name" name="name" placeholder="Enter name">
```

### 8. Inline Styles (Maintenance Nightmare)
```html
<!-- ❌ BAD (inline styles everywhere) -->
<div style="color: red; font-size: 16px; margin: 10px;">Content</div>

<!-- ✅ GOOD (use CSS classes) -->
<div class="alert-message">Content</div>
```

---

## 💻 Complete Code Examples

### Example 1: Semantic Blog Post
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Understanding Semantic HTML | Web Dev Blog</title>
  <meta name="description" content="Learn why semantic HTML matters for SEO and accessibility">
</head>
<body>
  <header>
    <nav aria-label="Main Navigation">
      <ul>
        <li><a href="/" aria-current="page">Home</a></li>
        <li><a href="/blog">Blog</a></li>
        <li><a href="/about">About</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <article>
      <header>
        <h1>Understanding Semantic HTML</h1>
        <p>Published on <time datetime="2025-01-16">January 16, 2025</time></p>
        <p>By <span class="author">Jane Developer</span></p>
      </header>

      <section>
        <h2>What is Semantic HTML?</h2>
        <p>Semantic HTML uses tags that describe the meaning of content...</p>
        
        <figure>
          <img src="semantic-html.png" 
               alt="Comparison of semantic vs non-semantic HTML structure"
               loading="lazy">
          <figcaption>Semantic HTML provides meaningful structure</figcaption>
        </figure>
      </section>

      <section>
        <h2>Benefits of Semantic HTML</h2>
        <ul>
          <li>Improved SEO rankings</li>
          <li>Better accessibility for screen readers</li>
          <li>Easier code maintenance</li>
        </ul>
      </section>

      <footer>
        <p>Tags: 
          <a href="/tag/html">HTML</a>, 
          <a href="/tag/accessibility">Accessibility</a>
        </p>
      </footer>
    </article>

    <aside>
      <h3>Related Posts</h3>
      <ul>
        <li><a href="/css-basics">CSS Fundamentals</a></li>
        <li><a href="/seo-guide">SEO Best Practices</a></li>
      </ul>
    </aside>
  </main>

  <footer>
    <p>&copy; 2025 Web Dev Blog. All rights reserved.</p>
    <nav aria-label="Footer Navigation">
      <a href="/privacy">Privacy Policy</a>
      <a href="/terms">Terms of Service</a>
    </nav>
  </footer>
</body>
</html>
```

### Example 2: Accessible Contact Form
```html
<form action="/submit" method="POST" novalidate>
  <fieldset>
    <legend>Contact Information</legend>
    
    <div class="form-group">
      <label for="fullname">Full Name: <span aria-label="required">*</span></label>
      <input type="text" 
             id="fullname" 
             name="fullname" 
             required
             aria-required="true"
             aria-describedby="name-help">
      <small id="name-help">Enter your first and last name</small>
    </div>

    <div class="form-group">
      <label for="email">Email: <span aria-label="required">*</span></label>
      <input type="email" 
             id="email" 
             name="email" 
             required
             aria-required="true"
             placeholder="your@email.com">
    </div>

    <div class="form-group">
      <label for="phone">Phone Number:</label>
      <input type="tel" 
             id="phone" 
             name="phone"
             pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
             placeholder="123-456-7890">
    </div>
  </fieldset>

  <fieldset>
    <legend>Message</legend>
    
    <div class="form-group">
      <label for="subject">Subject: <span aria-label="required">*</span></label>
      <select id="subject" name="subject" required>
        <option value="">-- Select Subject --</option>
        <option value="general">General Inquiry</option>
        <option value="support">Technical Support</option>
        <option value="sales">Sales Question</option>
      </select>
    </div>

    <div class="form-group">
      <label for="message">Message: <span aria-label="required">*</span></label>
      <textarea id="message" 
                name="message" 
                rows="5" 
                required
                aria-required="true"
                maxlength="500"></textarea>
      <small>Maximum 500 characters</small>
    </div>

    <div class="form-group">
      <input type="checkbox" 
             id="newsletter" 
             name="newsletter" 
             value="yes">
      <label for="newsletter">Subscribe to our newsletter</label>
    </div>
  </fieldset>

  <div class="form-actions">
    <button type="submit">Send Message</button>
    <button type="reset">Clear Form</button>
  </div>
</form>
```

---

## 📚 Additional Resources

### Official Documentation
- [MDN HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML) - Comprehensive HTML guide
- [W3C HTML Specification](https://html.spec.whatwg.org/) - Official HTML standard
- [HTML5 Doctor](http://html5doctor.com/) - Semantic element usage guides

### Validation Tools
- [W3C HTML Validator](https://validator.w3.org/) - Check HTML validity
- [WAVE Accessibility Tool](https://wave.webaim.org/) - Test accessibility
- [Google Lighthouse](https://developers.google.com/web/tools/lighthouse) - Performance and SEO audit

### Learning Platforms
- [freeCodeCamp HTML Course](https://www.freecodecamp.org/learn/responsive-web-design/)
- [The Odin Project HTML](https://www.theodinproject.com/paths/foundations/courses/foundations)
- [HTML Dog Tutorials](https://htmldog.com/guides/html/)

---

## 🎯 Practice Exercises

### Beginner Level
1. Create a personal portfolio homepage with proper semantic structure
2. Build a blog post layout using `<article>`, `<section>`, and `<aside>`
3. Design an accessible contact form with all input types

### Intermediate Level
1. Create a news website homepage with multiple articles and navigation
2. Build a product page with image gallery and description
3. Design an e-commerce checkout form with validation

### Advanced Level
1. Create a documentation site with table of contents and anchor links
2. Build an accessible data table with sorting functionality
3. Design a multi-step form with progress indicator

---

## ✅ Day 2 Checklist

- [ ] Understand semantic HTML tags and their purpose
- [ ] Master heading hierarchy (h1-h6) for SEO
- [ ] Create accessible forms with proper labels
- [ ] Implement SEO meta tags correctly
- [ ] Use HTML5 input types for validation
- [ ] Avoid common mistakes (multiple h1, divitis, etc.)
- [ ] Write clean, maintainable HTML code
- [ ] Validate HTML using W3C validator

---

## 📢 Share Your Progress

Completed Day 2? Share your learning:
- Tweet with #30DaysOfCheatSheets
- Build a project using semantic HTML
- Help others by answering questions
- Review someone else's HTML code

---

---

Made with ❤️ by [@YourHandle](https://twitter.com/YourHandle) | #30DaysOfCheatSheets
