# 📚 Minerva - Faroese Mathematics Education Platform# Minerva Classroom – README



A modern, responsive Quarto website for teaching mathematics in Faroese. Built with a focus on clean design, intuitive navigation, and excellent user experience.Minerva Classroom is a Quarto website template for math & science lessons, organized by year and subject. It’s based on Quarto and borrows the navigation/sidebar structure of the Network Science Notes site:contentReference[oaicite:3]{index=3}. Each lesson page includes video embeds and LaTeX examples.



## 🚀 Quick Start## Quickstart



### Prerequisites1. **Install Quarto**: Follow the instructions on the [Quarto website](https://quarto.org/docs/get-started/) to install Quarto on your system.

- [Quarto](https://quarto.org/docs/get-started/) (latest version)2. **Clone the repository**:  

- A text editor (VS Code recommended)

- Git (optional, for version control)3. **Preview locally**:  

In the project folder, run `quarto preview`. This will build and serve the site locally (auto-refresh as you edit).

### Installation & Setup4. **Build the site**:  

Run `quarto render` to generate the site into the `docs/` folder.

1. **Clone or download this repository**5. **Enable GitHub Pages**:  

   ```bashCommit and push your files, then in your GitHub repo settings enable Pages from the `docs/` folder. The site will be published at `https://<user>.github.io/<repo>/` :contentReference[oaicite:4]{index=4}.

   git clone <your-repo-url>

   cd quarto_2_test## Adding a New Lesson

   ```

- Copy an existing lesson file (e.g. `years/year7/matematik/lesson-01-fractions.qmd`) and rename it (e.g. `lesson-03-newtopic.qmd`).

2. **Preview the website locally**- Edit the **title** and content in the YAML header of the new file. Update text, math, etc. Replace the dummy `{{< video ... >}}` URL with your own video link.

   ```bash- Add the new filename to the sidebar navigation in `_quarto.yml`. For example, under the appropriate subject:

   quarto preview```yaml

   ```website:

   This will open your browser at `http://localhost:####` with live reload enabled. sidebar:

   - section: "Matematik"

3. **Build for production**     href: years/year7/matematik/index.qmd

   ```bash     contents:

   quarto render       - years/year7/matematik/lesson-01-fractions.qmd

   ```       - years/year7/matematik/lesson-02-linear-equations.qmd

   The site will be generated in the `docs/` folder, ready for deployment.       - years/year7/matematik/lesson-03-newtopic.qmd   # <-- new lesson


### Deployment

#### GitHub Pages
1. Push your repository to GitHub
2. Go to Settings → Pages
3. Select `Deploy from a branch`
4. Choose the `main` branch and `/docs` folder
5. Save and wait for deployment

Your site will be live at: `https://yourusername.github.io/your-repo-name/`

---

## 📁 Project Structure

```
quarto_2_test/
├── _quarto.yml              # Main configuration file
├── minerva_theme.scss       # Custom theme styling
├── navbar-handler.html      # Dynamic navbar behavior
├── footer.html              # Footer with sponsor section
├── index.qmd                # Homepage
├── about.qmd                # About page
├── years/                   # Course content organized by year
│   ├── 1.g/                 # First year (Støddfrøði C)
│   │   ├── index.qmd        # Year overview page
│   │   ├── breadcrumb.html  # Navigation breadcrumb
│   │   ├── tol_og_algebra/  # Subject: Numbers & Algebra
│   │   ├── funktionir/      # Subject: Functions
│   │   ├── geometri/        # Subject: Geometry
│   │   ├── hagfrodi/        # Subject: Statistics
│   │   ├── likindarokning/  # Subject: Probability
│   │   └── kapitalrokning/  # Subject: Finance
│   └── 2.g/                 # Second year (Støddfrøði B)
│       └── index.qmd        # Year overview page
└── docs/                    # Generated website (don't edit manually)
```

---

## 🎨 Customizing Your Site

### Changing Colors & Branding

Edit `minerva_theme.scss` and modify the CSS variables at the top:

```scss
:root {
  --minerva-primary: #0F172A;        /* Main dark color */
  --minerva-secondary: #3B82F6;      /* Accent blue */
  --minerva-accent: #8B5CF6;         /* Purple highlights */
  --minerva-success: #10B981;        /* Green for success */
  --minerva-warning: #F59E0B;        /* Amber for warnings */
  
  /* Add your custom colors here */
}
```

### Changing the Site Title & URL

Edit `_quarto.yml`:

```yaml
website:
  title: "Your Site Name"        # Changes navbar title
  site-url: "https://yoursite.com"  # Your actual URL
```

### Customizing the Navbar

Edit the navbar section in `_quarto.yml`:

```yaml
navbar:
  left:
    - icon: house-fill
      text: "Home"
      href: index.qmd
    - text: "About Us"
      href: about.qmd
    # Add more navigation items here
```

### Changing Fonts

Edit `minerva_theme.scss` at the top:

```scss
@import url('https://fonts.googleapis.com/css2?family=YourFont:wght@300;400;600;700&display=swap');

:root {
  --main-font: 'YourFont', sans-serif;
}
```

---

## 📝 Adding Content

### Adding a New Lesson Page

1. **Create the file** in the appropriate subject folder:
   ```bash
   years/1.g/funktionir/my-new-lesson.qmd
   ```

2. **Add frontmatter** at the top of the file:
   ```yaml
   ---
   title: "My New Lesson Title"
   sidebar: sidebar-1g
   toc: true
   toc-location: right
   ---
   
   ## Introduction
   
   Your lesson content here...
   ```

3. **Add to sidebar navigation** in `_quarto.yml`:
   ```yaml
   - section: "📈 Funktiónir"
     contents:
       - years/1.g/funktionir/existing-lesson.qmd
       - years/1.g/funktionir/my-new-lesson.qmd  # <-- Add here
   ```

4. **Render and preview**:
   ```bash
   quarto preview
   ```

### Adding a New Subject

1. **Create the folder structure**:
   ```bash
   mkdir years/1.g/new-subject
   ```

2. **Create an index page** (`years/1.g/new-subject/index.qmd`):
   ```yaml
   ---
   title: "New Subject Name"
   sidebar: sidebar-1g
   ---
   
   ## Welcome to New Subject
   
   Brief description...
   
   ### Lessons
   
   - [Lesson 1](lesson-01.qmd)
   - [Lesson 2](lesson-02.qmd)
   ```

3. **Add to the sidebar** in `_quarto.yml`:
   ```yaml
   sidebar:
     - id: sidebar-1g
       contents:
         - section: "🎯 New Subject"  # Add emoji icon
           href: years/1.g/new-subject/index.qmd
           collapsed: true
           contents:
             - years/1.g/new-subject/lesson-01.qmd
             - years/1.g/new-subject/lesson-02.qmd
   ```

### Adding a New Year Level

1. **Create the folder**:
   ```bash
   mkdir years/3.g
   ```

2. **Create the index page** (`years/3.g/index.qmd`):
   ```yaml
   ---
   title: "Støddfrøði A - 3.g"
   page-layout: full
   ---
   
   :::: {.page-header}
   # 📐 Støddfrøði A
   ### Third Year Mathematics
   ::::
   
   ## Subjects
   
   - [Subject 1](subject1/index.qmd)
   - [Subject 2](subject2/index.qmd)
   ```

3. **Create a new sidebar** in `_quarto.yml`:
   ```yaml
   sidebar:
     - id: sidebar-3g
       title: "📐 Støddfrøði A"
       location: left
       style: "docked"
       collapse-level: 2
       contents:
         - text: "🏠 Tilbaka til Øll Evni"
           href: years/3.g/index.qmd
         - section: "📊 Subject 1"
           href: years/3.g/subject1/index.qmd
           contents:
             # Add lessons here
   ```

4. **Link from homepage** in `index.qmd`:
   ```html
   <a href="years/3.g/index.qmd" class="year-card">
     <h2>📐 Støddfrøði A</h2>
     <p>3.g - Advanced Mathematics</p>
   </a>
   ```

---

## 🎯 Layout System Explained

### Three-Column Layout

The site uses a three-column layout on lesson pages:

```
┌──────────────┬─────────────────────┬──────────────┐
│   Sidebar    │   Main Content      │     TOC      │
│   (Left)     │    (Center)         │   (Right)    │
│              │                     │              │
│ - Subjects   │ - Lesson text       │ - Page jump  │
│ - Lessons    │ - Examples          │ - Quick nav  │
│ - Topics     │ - Exercises         │              │
└──────────────┴─────────────────────┴──────────────┘
```

### Grid Configuration

Edit in `_quarto.yml`:

```yaml
format:
  html:
    grid:
      sidebar-width: 300px    # Left sidebar width
      body-width: 900px       # Main content width
      margin-width: 250px     # Right TOC width
```

### Page Layouts

Different layouts for different pages:

- **`page-layout: full`** - Wide layout (homepage, year overview pages)
- **`page-layout: article`** - Standard with sidebars (lesson pages)
- No layout specified - Uses default from `_quarto.yml`

---

## 🎨 Styling System

### CSS Architecture

The site uses **two stylesheets** that work together:

**1. `styles.css`** - Main styling (cards, layout, content)
**2. `minerva_theme.scss`** - Theme enhancements (navbar, TOC, animations)

**Structure:**
1. **CSS Variables** - Colors, shadows, spacing  
2. **Typography** - Fonts, headings, text styles
3. **Content & Cards** - Main content area, lesson cards
4. **Sidebar** - Left navigation styling
5. **TOC** - Right sidebar table of contents (minerva_theme.scss)
6. **Navbar** - Top navigation (minerva_theme.scss)
7. **Responsive** - Mobile-friendly breakpoints

### Responsive Breakpoints

```scss
@media (max-width: 991px) { /* Tablets */ }
@media (max-width: 768px) { /* Small tablets */ }
@media (max-width: 576px) { /* Mobile phones */ }
```

### Adding Custom Styles

Add your custom styles at the bottom of `minerva_theme.scss`:

```scss
/* ========================================
   Custom Styles
   ======================================== */

.my-custom-class {
  background: var(--minerva-primary);
  color: white;
  padding: 20px;
  border-radius: 12px;
}
```

---

## 🧭 Navigation Features

### Breadcrumb Navigation

Shows users where they are in the site hierarchy.

**To add breadcrumbs** to a lesson page:
```qmd
---
title: "My Lesson"
---

## Content starts here
```

### Sidebar Icons

Use emojis for visual navigation in `_quarto.yml`:

```yaml
- section: "📚 Tøl og Algebra"    # Numbers icon
- section: "📈 Funktiónir"        # Chart icon
- section: "📐 Geometri"          # Triangle icon
- section: "📊 Hagfrøði"          # Bar chart icon
- section: "🎲 Líkindarokning"    # Dice icon
- section: "💰 Kapitalrokning"    # Money icon
```

**Emoji resources:**
- [Emojipedia](https://emojipedia.org/)
- [Unicode Emoji List](https://unicode.org/emoji/charts/full-emoji-list.html)

### Dynamic Navbar

The navbar automatically adjusts based on the page:
- **Homepage**: Shows standard navigation
- **Year pages**: Updates title and back button
- **Lesson pages**: Shows appropriate back link

This is handled by `navbar-handler.html` (no editing needed unless you want to customize behavior).

---

## 📱 Mobile Responsiveness

The site is fully responsive:

- **Desktop (>991px)**: Three-column layout with both sidebars
- **Tablet (768-991px)**: Sidebar becomes collapsible overlay
- **Mobile (<768px)**: Simplified layout, touch-friendly navigation

### Testing Mobile View

1. **In browser**: Press `F12` → Toggle device toolbar
2. **Preview on device**: Find your local IP with `ipconfig`, then visit `http://your-ip:port` on your phone

---

## 🔧 Maintenance & Best Practices

### File Organization

✅ **Do:**
- Keep related lessons in the same subject folder
- Use descriptive filenames: `kvadratsetningar-introduktion.qmd`
- Add frontmatter to every `.qmd` file
- Include breadcrumb navigation on lesson pages

❌ **Don't:**
- Edit files in the `docs/` folder (generated automatically)
- Use spaces in filenames (use hyphens or underscores)
- Forget to add new pages to the sidebar in `_quarto.yml`

### Content Guidelines

**Lesson Page Template:**
```yaml
---
title: "Lesson Title"
sidebar: sidebar-1g
toc: true
toc-location: right
---

---

## Introduction

```

## Introduction

Brief overview of the topic...

## Main Concept

### Definition

Detailed explanation...

### Example

**Example 1:** 

$$
f(x) = x^2 + 2x + 1
$$

### Practice Problems

1. Problem 1...
2. Problem 2...

## Summary

Key takeaways...
```

### Math Equations

Use LaTeX for math:

**Inline:** `$E = mc^2$` → $E = mc^2$

**Display:**
```latex
$$
\int_0^1 x^2 \, dx = \frac{1}{3}
$$
```

---

## 🐛 Troubleshooting

### Preview not working

```bash
# Kill any running preview servers
quarto preview --stop

# Clear cache and restart
rm -rf .quarto
quarto preview
```

### Styles not updating

1. Hard refresh: `Ctrl + Shift + R` (Windows) or `Cmd + Shift + R` (Mac)
2. Clear browser cache
3. Stop and restart preview server

### Sidebar not showing new pages

1. Check `_quarto.yml` syntax (proper indentation with spaces, not tabs)
2. Verify file path is correct
3. Restart preview server

### TOC not appearing

Make sure your lesson page has:
```yaml
---
toc: true
toc-location: right
---
```

And has proper heading structure:
```markdown
## Section 1
### Subsection 1.1
### Subsection 1.2
## Section 2
```

---

## 📚 Useful Resources

### Quarto Documentation
- [Quarto Websites](https://quarto.org/docs/websites/)
- [Quarto Publishing](https://quarto.org/docs/publishing/)
- [Markdown Basics](https://quarto.org/docs/authoring/markdown-basics.html)

### Math & LaTeX
- [LaTeX Math Symbols](https://www.cmor-faculty.rice.edu/~heinken/latex/symbols.pdf)
- [KaTeX Supported Functions](https://katex.org/docs/supported.html)

### Design Resources
- [CSS Tricks](https://css-tricks.com/)
- [Google Fonts](https://fonts.google.com/)
- [Coolors (Color Palettes)](https://coolors.co/)

---

## 🤝 Contributing

### Making Changes

1. Create a new branch for your changes
2. Make your edits
3. Test locally with `quarto preview`
4. Commit and push your changes
5. Deploy by rendering: `quarto render`

### Version Control

```bash
# Save your work
git add .
git commit -m "Add new lesson on quadratic equations"
git push

# Deploy to GitHub Pages (if docs/ is committed)
# Changes will appear in a few minutes
```

---

## 📊 Site Analytics (Optional)

To add Google Analytics:

1. Get your GA4 Measurement ID
2. Add to `_quarto.yml`:
   ```yaml
   website:
     google-analytics: "G-XXXXXXXXXX"
   ```

---

## 🎓 Educational Features

### Video Embeds

```markdown
{{< video https://www.youtube.com/watch?v=VIDEO_ID >}}
```

### Interactive Elements

```markdown
::: {.callout-note}
## Important Note
Remember this key concept!
:::

::: {.callout-warning}
## Common Mistake
Watch out for this error!
:::

::: {.callout-tip}
## Pro Tip
Here's a shortcut!
:::
```

### Code Blocks

```markdown
```python
def quadratic(a, b, c):
    discriminant = b**2 - 4*a*c
    return discriminant
`` `
```

---

## 📄 License

[Add your license information here]

---

## 🙏 Acknowledgments

- Built with [Quarto](https://quarto.org/)
- Inspired by modern educational platforms
- Designed for the Faroese mathematics community

---

**Made with ❤️ for Faroese students**

*Last updated: November 2025*
