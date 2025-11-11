# Changelog

All notable changes to the Minerva website will be documented in this file.

## [2.0.0] - November 2025

### Major Refactor & Cleanup

#### ✨ Added
- **Comprehensive README.md** - Complete guide for using and customizing the site
- **MAINTENANCE.md** - Detailed maintenance guide with best practices
- **Right sidebar TOC** - Table of contents now appears on the right side of lesson pages
- **Breadcrumb navigation** - Easy way to navigate back to overview pages
- **Emoji icons** - Visual navigation in sidebar (📚, 📈, 📐, 📊, 🎲, 💰)
- **Smooth hover effects** - Elegant animations on TOC and cards
- **Three-column layout** - Left sidebar + content + right TOC

#### 🎨 Changed
- **Dual stylesheet system** - styles.css (main styling) + minerva_theme.scss (theme enhancements)
- **Improved card design** - Modern, responsive cards for lessons and topics
- **Enhanced mobile responsiveness** - Better experience on tablets and phones
- **Updated color scheme** - Professional blue and purple palette
- **Refined typography** - Inter font family, improved readability

#### 🗑️ Removed
- **Legacy code** - Cleaned up old comments and unused styles
- **Duplicate CSS** - Removed redundant styling between files
- **Navbar emoji animation** - Removed distracting bounce effect
- **TODO comments** - Fixed site-url placeholder

#### 🐛 Fixed
- **Main page layout** - Removed white horizontal lines in hero section
- **Sidebar navigation** - Subject navigation now on left, page TOC on right
- **Mobile sidebar** - Fixed overlay behavior on small screens
- **TOC visibility** - Resolved CSS issues preventing TOC from appearing

#### 📚 Documentation
- Added comprehensive README with setup, customization, and troubleshooting
- Created maintenance guide with best practices and checklists
- Documented code structure and organization
- Added examples for common tasks (adding lessons, subjects, years)

---

## [1.0.0] - Initial Release

### Initial Features
- Basic Quarto website structure
- Year-based organization (1.g, 2.g)
- Subject-based lessons
- LaTeX math support
- Responsive design
- GitHub Pages deployment

---

## How to Update This Changelog

When making significant changes, add them under a new version header:

```markdown
## [X.Y.Z] - YYYY-MM-DD

### Added
- New features you added

### Changed
- Changes to existing features

### Fixed
- Bug fixes

### Removed
- Removed features
```

Use semantic versioning:
- **Major (X)**: Breaking changes, complete redesigns
- **Minor (Y)**: New features, no breaking changes
- **Patch (Z)**: Bug fixes, small improvements
