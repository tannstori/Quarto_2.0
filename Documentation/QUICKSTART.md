# 🚀 Quick Start Guide for Contributors

New to the Minerva project? This guide will get you up and running in 5 minutes!

## Prerequisites

1. **Install Quarto**: https://quarto.org/docs/get-started/
2. **Clone the repository** (if using Git)
3. **Open in your text editor** (VS Code recommended)

## Your First 5 Minutes

### 1. Preview the Site (1 minute)

```bash
cd quarto_2_test
quarto preview
```

Your browser will open automatically. The site will auto-reload when you make changes!

### 2. Make a Small Edit (2 minutes)

**Edit the homepage:**
1. Open `index.qmd`
2. Change any text
3. Save the file
4. Watch the browser auto-reload ✨

### 3. Add a New Lesson (2 minutes)

**Create a test lesson:**
1. Copy an existing lesson file in `years/1.g/funktionir/`
2. Rename it to `my-test-lesson.qmd`
3. Change the title in the frontmatter
4. Add it to `_quarto.yml` under the Funktiónir section

## Common Tasks

### Adding Content

**New lesson page:**
```bash
# 1. Create file
years/1.g/subject-name/my-lesson.qmd

# 2. Add frontmatter:
---
title: "My Lesson"
sidebar: sidebar-1g
toc: true
toc-location: right
---

# 3. Add to _quarto.yml sidebar
```

**New subject:**
```bash
# 1. Create folder
mkdir years/1.g/new-subject

# 2. Create index.qmd in that folder

# 3. Add section to _quarto.yml sidebar
```

### Customizing Design

**Change colors:**
- Edit `minerva_theme.scss`
- Modify the `:root` variables at the top
- Save and see changes instantly

**Change fonts:**
- Edit the `@import` line in `minerva_theme.scss`
- Update `--main-font` variable

### Building for Production

```bash
# Generate the site
quarto render

# Site is created in docs/ folder
# Ready to deploy to GitHub Pages!
```

## File Structure at a Glance

```
Important files you'll edit:
├── _quarto.yml          ← Site configuration & sidebars
├── minerva_theme.scss   ← All styling
├── index.qmd            ← Homepage
├── years/
│   └── 1.g/
│       ├── index.qmd    ← Year overview
│       └── subject/
│           └── *.qmd    ← Lesson files

Don't edit these:
├── docs/                ← Auto-generated
├── .quarto/             ← Cache
└── navbar-handler.html  ← Works automatically
```

## Cheat Sheet

### Markdown Basics

```markdown
## Heading Level 2
### Heading Level 3

**Bold text**
*Italic text*

[Link text](url.qmd)

- List item 1
- List item 2

1. Numbered item
2. Numbered item
```

### Math Equations

```markdown
Inline math: $E = mc^2$

Display math:
$$
f(x) = x^2 + 2x + 1
$$
```

### Callout Boxes

```markdown
::: {.callout-note}
## Note
Important information here
:::

::: {.callout-warning}
## Warning
Be careful about this!
:::

::: {.callout-tip}
## Tip
Pro tip here
:::
```

## Git Workflow (Optional)

```bash
# 1. Create a branch for your changes
git checkout -b add-my-lesson

# 2. Make your changes and save

# 3. Test locally
quarto preview

# 4. Commit your changes
git add .
git commit -m "Add lesson about quadratic equations"

# 5. Push your branch
git push origin add-my-lesson

# 6. Create a Pull Request on GitHub
```

## Troubleshooting

**Preview not working?**
```bash
quarto preview --stop
quarto preview
```

**Styles not updating?**
- Hard refresh: `Ctrl + Shift + R` (Windows) or `Cmd + Shift + R` (Mac)

**Sidebar not showing?**
- Check frontmatter has `sidebar: sidebar-1g`
- Check `_quarto.yml` syntax (spaces, not tabs)

**TOC not showing?**
- Add `toc: true` to frontmatter
- Need at least 2 `##` headings in content

## Need More Help?

📖 **Full Documentation:**
- `README.md` - Complete guide
- `MAINTENANCE.md` - Detailed maintenance guide
- [Quarto Docs](https://quarto.org/docs/)

🐛 **Found a Bug?**
- Check `MAINTENANCE.md` Common Issues section
- Create an issue on GitHub

💬 **Questions?**
- Ask in GitHub Discussions
- Contact the maintainers

## Tips for Success

✅ **Do:**
- Test changes before committing
- Use descriptive commit messages
- Keep files organized
- Ask questions when unsure

❌ **Don't:**
- Edit files in `docs/` folder
- Use spaces in filenames
- Forget to add new pages to `_quarto.yml`
- Commit broken code

## Next Steps

1. ✅ Read this guide
2. ✅ Preview the site locally
3. ✅ Make a test edit
4. 📖 Read `README.md` for more details
5. 🎨 Customize colors and design
6. 📝 Add your first lesson
7. 🚀 Deploy to GitHub Pages

---

**Welcome to the Minerva project! 🎓**

You're now ready to contribute. Happy coding!

*For detailed guides, see README.md and MAINTENANCE.md*
