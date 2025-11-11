# 🛠️ Minerva Maintenance Guide

This guide covers common maintenance tasks, code organization, and best practices for keeping your Minerva website clean and efficient.

## 📋 Table of Contents

1. [Code Organization](#code-organization)
2. [Regular Maintenance Tasks](#regular-maintenance-tasks)
3. [Adding New Content Workflow](#adding-new-content-workflow)
4. [Styling Best Practices](#styling-best-practices)
5. [Performance Optimization](#performance-optimization)
6. [Backup & Version Control](#backup--version-control)
7. [Common Issues & Solutions](#common-issues--solutions)

---

## 📁 Code Organization

### File Structure Rules

```
✅ ORGANIZED:
years/1.g/funktionir/
├── index.qmd              # Overview of functions
├── linear-functions.qmd   # Specific topic
├── quadratic-functions.qmd
└── exponential-functions.qmd

❌ MESSY:
years/1.g/funktionir/
├── f1.qmd                 # Unclear names
├── temp_backup.qmd        # Old files
├── test123.qmd            # Test files
└── copy_of_functions.qmd  # Duplicates
```

### Naming Conventions

**Files:**
- Use lowercase
- Use hyphens for spaces: `kvadratsetningar-introduktion.qmd`
- Be descriptive: `tol-naturlig-og-heiltol.qmd` not `tol1.qmd`
- No spaces or special characters

**Folders:**
- Lowercase
- Underscores for compound names: `tol_og_algebra`
- Short but clear: `funktionir` not `funktiónir_og_grafikar_2024`

**Sidebar IDs:**
- Use pattern: `sidebar-1g`, `sidebar-2g`, `sidebar-3g`
- Consistent naming makes maintenance easier

### What Goes Where

| Content Type | Location | Example |
|-------------|----------|---------|
| Homepage | `/index.qmd` | Main landing page |
| About page | `/about.qmd` | Information about site |
| Year overview | `/years/1.g/index.qmd` | Year-level home |
| Subject overview | `/years/1.g/funktionir/index.qmd` | Subject home |
| Lesson content | `/years/1.g/funktionir/lesson-name.qmd` | Individual lessons |
| Shared components | `/years/1.g/breadcrumb.html` | Reusable includes |
| Global styles | `/minerva_theme.scss` | All CSS |
| Global scripts | `/navbar-handler.html` | JavaScript |
| Configuration | `/_quarto.yml` | Site settings |

---

## 🔄 Regular Maintenance Tasks

### Weekly Tasks

**1. Check for Broken Links**
```bash
quarto render
# Check terminal output for warnings about missing links
```

**2. Preview on Multiple Devices**
- Desktop browser
- Tablet view (F12 → device toolbar)
- Mobile phone

**3. Review Recent Changes**
```bash
git log --oneline --since="1 week ago"
git diff HEAD~7 HEAD
```

### Monthly Tasks

**1. Update Dependencies**
```bash
quarto check
# Upgrade if new version available
```

**2. Clean Up Generated Files**
```bash
# Remove and regenerate docs
rm -rf docs/
quarto render
```

**3. Review and Clean**
- Remove unused images
- Delete test files
- Archive old content
- Update outdated information

**4. Performance Check**
- Test loading speed
- Check image sizes (compress if >500KB)
- Verify mobile responsiveness

### Quarterly Tasks

**1. Content Audit**
- Review all lessons for accuracy
- Update examples and practice problems
- Check that all TODOs are addressed

**2. SEO & Accessibility**
- Verify all images have alt text
- Check heading hierarchy (H1 → H2 → H3)
- Test with screen reader if possible

**3. Backup Everything**
```bash
# Create full backup
git tag -a v1.0-backup-$(date +%Y%m%d) -m "Quarterly backup"
git push --tags
```

---

## 📝 Adding New Content Workflow

### Checklist for New Lesson

- [ ] Create `.qmd` file in appropriate subject folder
- [ ] Add proper frontmatter (title, sidebar, toc)
- [ ] Include breadcrumb navigation
- [ ] Write content with proper heading structure (##, ###)
- [ ] Add to sidebar in `_quarto.yml`
- [ ] Test locally with `quarto preview`
- [ ] Check TOC appears on right side
- [ ] Verify sidebar navigation works
- [ ] Test on mobile view
- [ ] Commit changes with descriptive message
- [ ] Push and verify deployment

### Template for New Lesson

Save this as a starting point:

```yaml
---
title: "Your Lesson Title Here"
sidebar: sidebar-1g
toc: true
toc-location: right
---

# Include breadcrumb: {{</* include ../breadcrumb.html */>}}

## Introduction

Brief introduction to the topic...

## Key Concepts

### Concept 1

Explanation...

**Example:**

$$
\text{Math formula here}
$$

### Concept 2

More explanation...

## Practice Problems

1. Problem 1
2. Problem 2
3. Problem 3

## Summary

- Key point 1
- Key point 2
- Key point 3

## Further Reading

- [Related Lesson 1](link1.qmd)
- [Related Lesson 2](link2.qmd)
```

### Adding New Subject

**Step-by-step:**

1. **Create folder structure**
   ```bash
   mkdir years/1.g/new-subject
   ```

2. **Create index.qmd**
   ```yaml
   ---
   title: "Subject Name"
   sidebar: sidebar-1g
   ---
   
   ## Overview
   Description of this subject...
   
   ## Topics
   - [Topic 1](topic-1.qmd)
   - [Topic 2](topic-2.qmd)
   ```

3. **Add to `_quarto.yml` sidebar**
   - Find the correct sidebar (`sidebar-1g`)
   - Add new section with emoji icon
   - List all lessons in the subject

4. **Create lessons**
   - Use lesson template above
   - Consistent naming
   - Proper frontmatter

5. **Test thoroughly**
   ```bash
   quarto preview
   # Navigate through all new pages
   ```

---

## 🎨 Styling Best Practices

### When to Edit Styles

**Edit `minerva_theme.scss` when you want to:**
- Change colors site-wide
- Adjust spacing or typography
- Modify hover effects
- Update responsive breakpoints
- Add new component styles

**Don't edit styles for:**
- Content-specific formatting (use Quarto markdown features)
- One-off styling needs (use inline CSS in `.qmd` files)

### CSS Organization

The theme file is organized in sections:

```scss
/* 1. Variables - Change colors, shadows, fonts */
:root { ... }

/* 2. Base Styles - Body, typography */
body { ... }

/* 3. Components - Navbar, sidebar, TOC */
.navbar { ... }

/* 4. Layout - Grid, content area */
#quarto-content { ... }

/* 5. Responsive - Mobile breakpoints */
@media (max-width: 991px) { ... }

/* 6. Utilities - Helpers, animations */
.animate-slide-left { ... }
```

**Add new styles at the appropriate section!**

### Color System

Use CSS variables for consistency:

```scss
/* ✅ GOOD - Uses variables */
.my-element {
  background: var(--minerva-primary);
  color: var(--minerva-text);
}

/* ❌ BAD - Hardcoded colors */
.my-element {
  background: #0F172A;
  color: #1F2937;
}
```

### Responsive Design

Always test at these breakpoints:

- **1200px+** - Large desktop
- **992px-1199px** - Desktop
- **768px-991px** - Tablet
- **576px-767px** - Large phone
- **<576px** - Small phone

Use mobile-first approach:

```scss
/* ✅ GOOD - Mobile first */
.element {
  font-size: 14px;
}

@media (min-width: 768px) {
  .element {
    font-size: 16px;
  }
}

/* ❌ BAD - Desktop first (harder to maintain) */
.element {
  font-size: 16px;
}

@media (max-width: 767px) {
  .element {
    font-size: 14px;
  }
}
```

---

## ⚡ Performance Optimization

### Image Optimization

**Before adding images:**

1. Compress images: Use [TinyPNG](https://tinypng.com/)
2. Resize appropriately:
   - Hero images: 1920x800px
   - Card images: 600x400px
   - Icons: 128x128px
3. Use correct format:
   - Photos: `.jpg`
   - Graphics/logos: `.png`
   - Icons: `.svg`

### Code Optimization

**Keep `_quarto.yml` clean:**
- Remove commented-out sections
- No duplicate entries
- Proper indentation

**Minimize custom JavaScript:**
- Current `navbar-handler.html` is necessary
- Avoid adding more scripts unless critical

### Loading Speed

**Check your site speed:**
1. Build site: `quarto render`
2. Test: Open `docs/index.html` in browser
3. Check DevTools: Network tab → Page load time
4. Goal: <2 seconds on 3G connection

**If slow:**
- Compress images
- Remove unused CSS
- Minimize large math equations on homepage

---

## 💾 Backup & Version Control

### Git Best Practices

**Commit messages:**
```bash
# ✅ GOOD - Clear and descriptive
git commit -m "Add quadratic equations lesson to 1.g functions"
git commit -m "Fix TOC not appearing on mobile devices"
git commit -m "Update color scheme to darker blue theme"

# ❌ BAD - Vague or unclear
git commit -m "updates"
git commit -m "fix stuff"
git commit -m "asdfasdf"
```

**Branching strategy:**
```bash
# Create feature branch
git checkout -b add-statistics-lessons

# Make changes, test thoroughly
quarto preview

# Commit and push
git add .
git commit -m "Add initial statistics lessons for 1.g"
git push origin add-statistics-lessons

# Merge when ready
git checkout main
git merge add-statistics-lessons
git push origin main
```

### Backup Strategy

**What to backup:**
- ✅ All `.qmd` files
- ✅ `_quarto.yml`
- ✅ `minerva_theme.scss`
- ✅ Custom HTML files
- ✅ Images folder
- ❌ `docs/` folder (auto-generated)
- ❌ `.quarto/` folder (cache)

**Automated backups:**
```bash
# Create backup script (backup.sh)
#!/bin/bash
DATE=$(date +%Y%m%d)
tar -czf "backup_minerva_$DATE.tar.gz" \
  --exclude='docs' \
  --exclude='.quarto' \
  --exclude='node_modules' \
  .
```

---

## 🔍 Common Issues & Solutions

### Issue: Sidebar Not Showing

**Symptoms:** Left sidebar missing on lesson pages

**Solutions:**
1. Check frontmatter has `sidebar: sidebar-1g`
2. Verify sidebar ID matches in `_quarto.yml`
3. Restart preview server
4. Clear browser cache

### Issue: TOC Not Appearing

**Symptoms:** No table of contents on right side

**Solutions:**
1. Ensure frontmatter has:
   ```yaml
   toc: true
   toc-location: right
   ```
2. Check heading structure (need at least 2 `##` headings)
3. Verify `_quarto.yml` has grid configuration
4. Check `minerva_theme.scss` has TOC styles

### Issue: Styles Not Updating

**Symptoms:** CSS changes don't appear in browser

**Solutions:**
1. Hard refresh: `Ctrl + Shift + R`
2. Clear browser cache completely
3. Stop and restart `quarto preview`
4. Check browser console for CSS errors
5. Verify no typos in `minerva_theme.scss`

### Issue: Broken Links

**Symptoms:** 404 errors or "Page not found"

**Solutions:**
1. Check file path is correct and relative
2. Use `.qmd` extension in links, not `.html`
3. Verify file exists in correct location
4. Check for typos in filename
5. Run `quarto render` and check for warnings

### Issue: Mobile Layout Broken

**Symptoms:** Content overlaps or sidebar doesn't work on mobile

**Solutions:**
1. Test with browser DevTools device toolbar
2. Check responsive breakpoints in CSS
3. Verify `viewport` meta tag (Quarto adds automatically)
4. Test on actual device, not just emulator
5. Check for hardcoded widths in custom CSS

### Issue: Math Equations Not Rendering

**Symptoms:** LaTeX shows as plain text

**Solutions:**
1. Verify `math: true` in `_quarto.yml`
2. Check syntax: Use `$$` for display, `$` for inline
3. Escape special characters if needed
4. Test with simple equation first: `$x = 5$`
5. Check browser console for KaTeX errors

---

## 📊 Monitoring & Analytics

### What to Track

**User behavior:**
- Most visited pages
- Average time on page
- Mobile vs. desktop ratio
- Popular subjects

**Technical metrics:**
- Page load times
- Broken links
- Error rates
- Browser compatibility

### Setting Up Analytics

**Google Analytics 4:**
1. Create GA4 property
2. Get measurement ID
3. Add to `_quarto.yml`:
   ```yaml
   website:
     google-analytics: "G-XXXXXXXXXX"
   ```

**Simple alternative:**
- Use GitHub Pages insights
- Check commit history for content popularity
- Monitor issues/feedback from users

---

## 🚀 Deployment Checklist

Before deploying updates:

- [ ] Test locally with `quarto preview`
- [ ] Check all links work
- [ ] Verify images load
- [ ] Test on mobile view
- [ ] Review git status for unwanted files
- [ ] Run `quarto render` successfully
- [ ] Check for render errors/warnings
- [ ] Commit with clear message
- [ ] Push to repository
- [ ] Wait for GitHub Pages to deploy (2-5 minutes)
- [ ] Visit live site and spot-check
- [ ] Test critical pages on live site

---

## 📞 Getting Help

**When things go wrong:**

1. **Check this guide** - Common issues section
2. **Search Quarto docs** - [quarto.org/docs](https://quarto.org/docs)
3. **Review error messages** - Often tell you exactly what's wrong
4. **Check git history** - What changed recently?
   ```bash
   git log --oneline -10
   git diff HEAD~1 HEAD
   ```
5. **Ask for help** - GitHub Issues or community forums

**When reporting issues:**
- Describe what you expected
- Describe what happened instead
- Share error messages (copy full text)
- List steps to reproduce
- Mention browser/device used

---

## 📚 Additional Resources

**Quarto:**
- [Official Documentation](https://quarto.org/docs/)
- [Quarto GitHub](https://github.com/quarto-dev/quarto-cli)
- [Quarto Community](https://github.com/quarto-dev/quarto-cli/discussions)

**CSS & Design:**
- [MDN Web Docs](https://developer.mozilla.org/)
- [CSS Tricks](https://css-tricks.com/)
- [Can I Use](https://caniuse.com/) - Check browser support

**Git:**
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)

---

## ✅ Maintenance Checklist

Print or save this checklist:

### Daily (When Working)
- [ ] Commit changes with descriptive messages
- [ ] Test changes in preview before committing
- [ ] Check for console errors

### Weekly
- [ ] Review recent changes
- [ ] Check for broken links
- [ ] Test on mobile device

### Monthly
- [ ] Update Quarto if new version available
- [ ] Clean up unused files
- [ ] Review and update outdated content
- [ ] Check site performance

### Quarterly
- [ ] Full content audit
- [ ] Complete backup
- [ ] Review analytics (if set up)
- [ ] Update documentation

---

**Keep your Minerva site clean, fast, and maintainable!** 🚀

*Last updated: November 2025*
