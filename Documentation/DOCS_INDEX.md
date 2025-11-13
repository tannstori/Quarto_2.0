# 📚 Documentation Index

Welcome to the Minerva project documentation! This index helps you find the right guide for your needs.

---

## 🎯 I Want To...

### Get Started
- **Install and preview the site** → [QUICKSTART.md](./QUICKSTART.md) (5 minutes)
- **Understand the project structure** → [README.md](./README.md) - Project Structure section
- **Deploy to GitHub Pages** → [README.md](./README.md) - Deployment section

### Customize the Site
- **Change colors and fonts** → [README.md](./README.md) - Customizing Your Site
- **Modify the navbar** → [README.md](./README.md) - Customizing the Navbar
- **Adjust layout spacing** → [README.md](./README.md) - Layout System
- **Add custom styles** → [MAINTENANCE.md](./MAINTENANCE.md) - Styling Best Practices

### Add Content
- **Add a new lesson** → [README.md](./README.md) - Adding a New Lesson
- **Create a new subject** → [README.md](./README.md) - Adding a New Subject
- **Add a year level** → [README.md](./README.md) - Adding a New Year Level
- **Use math equations** → [README.md](./README.md) - Math Equations section

### Maintain the Site
- **Perform regular maintenance** → [MAINTENANCE.md](./MAINTENANCE.md) - Regular Maintenance Tasks
- **Optimize performance** → [MAINTENANCE.md](./MAINTENANCE.md) - Performance Optimization
- **Manage backups** → [MAINTENANCE.md](./MAINTENANCE.md) - Backup & Version Control
- **Follow best practices** → [MAINTENANCE.md](./MAINTENANCE.md) - File Organization

### Fix Problems
- **Troubleshoot common issues** → [README.md](./README.md) - Troubleshooting section
- **Fix styling issues** → [MAINTENANCE.md](./MAINTENANCE.md) - Common Issues & Solutions
- **Debug build errors** → [MAINTENANCE.md](./MAINTENANCE.md) - Troubleshooting section

### Understand Changes
- **See what's new** → [CHANGELOG.md](./CHANGELOG.md)
- **Review project overview** → [PROJECT_SUMMARY.md](./PROJECT_SUMMARY.md)

---

## 📖 Documentation Files

### [README.md](./README.md) - Main User Guide
**Who it's for:** All users (beginners to advanced)  
**Length:** ~30 minutes to read  
**Content:**
- Installation and setup
- Project structure overview
- Complete customization guide
- Step-by-step content addition
- Layout and styling system
- Navigation features
- Mobile responsiveness
- Troubleshooting
- Useful resources

**Start here if:** You're new to the project or need a comprehensive reference.

---

### [QUICKSTART.md](./QUICKSTART.md) - 5-Minute Guide
**Who it's for:** New contributors who want to start fast  
**Length:** 5-10 minutes  
**Content:**
- Rapid setup (3 steps)
- Your first edit
- Common tasks at a glance
- Markdown cheat sheet
- Quick troubleshooting
- Git workflow basics

**Start here if:** You want to dive in quickly and learn by doing.

---

### [MAINTENANCE.md](./MAINTENANCE.md) - Maintainer Guide
**Who it's for:** Site maintainers and advanced users  
**Length:** Reference guide (read as needed)  
**Content:**
- Code organization principles
- Regular maintenance schedules
- Detailed workflow checklists
- Styling best practices
- Performance optimization
- Backup strategies
- Common issues with solutions
- Analytics setup

**Start here if:** You're responsible for maintaining the site long-term.

---

### [CHANGELOG.md](./CHANGELOG.md) - Version History
**Who it's for:** All users  
**Length:** 2-5 minutes per version  
**Content:**
- Version 2.0 major refactor details
- Template for documenting future changes
- Semantic versioning guide

**Start here if:** You want to know what changed in recent updates.

---

### [PROJECT_SUMMARY.md](./PROJECT_SUMMARY.md) - Overview
**Who it's for:** Project managers, new team members  
**Length:** 10-15 minutes  
**Content:**
- High-level overview of changes
- Before/after comparisons
- Technical stack overview
- Quality checks and verification
- Achievement summary

**Start here if:** You need a bird's-eye view of the project.

---

## 🎓 Learning Path

### For Complete Beginners

1. **Start:** [QUICKSTART.md](./QUICKSTART.md) - Get site running locally
2. **Learn:** [README.md](./README.md) - Project Structure & File Organization  
3. **Practice:** Make a test edit, preview changes
4. **Expand:** [README.md](./README.md) - Adding Content section
5. **Master:** [MAINTENANCE.md](./MAINTENANCE.md) as needed

**Estimated time:** 1-2 hours to feel comfortable

---

### For Experienced Developers

1. **Skim:** [PROJECT_SUMMARY.md](./PROJECT_SUMMARY.md) - Understand project state
2. **Reference:** [README.md](./README.md) - Note customization options
3. **Deep dive:** [MAINTENANCE.md](./MAINTENANCE.md) - Technical details
4. **Check:** [CHANGELOG.md](./CHANGELOG.md) - Recent changes

**Estimated time:** 30 minutes to get up to speed

---

### For Content Creators

1. **Start:** [QUICKSTART.md](./QUICKSTART.md) - Setup and first edit
2. **Learn:** [README.md](./README.md) - Adding Content section
3. **Reference:** [README.md](./README.md) - Math Equations, Callouts
4. **Tips:** [MAINTENANCE.md](./MAINTENANCE.md) - Content Guidelines

**Estimated time:** 30 minutes to start creating

---

### For Maintainers

1. **Overview:** [PROJECT_SUMMARY.md](./PROJECT_SUMMARY.md) - Current state
2. **Setup:** [README.md](./README.md) - Deployment and configuration
3. **Process:** [MAINTENANCE.md](./MAINTENANCE.md) - Full maintenance guide
4. **Track:** [CHANGELOG.md](./CHANGELOG.md) - Document your changes

**Estimated time:** 2-3 hours for comprehensive understanding

---

## 📋 Quick Reference Cards

### Adding a New Lesson
```yaml
# 1. Create file: years/1.g/subject/lesson-name.qmd
# 2. Add frontmatter:
---
title: "Lesson Title"
sidebar: sidebar-1g
toc: true
toc-location: right
---
# 3. Add to _quarto.yml sidebar
# 4. Test with: quarto preview
```
*Detailed guide:* [README.md - Adding a New Lesson](./README.md#adding-a-new-lesson-page)

---

### Changing Colors
```scss
/* Edit minerva_theme.scss */
:root {
  --minerva-primary: #YourColor;
  --minerva-secondary: #YourColor;
}
```
*Detailed guide:* [README.md - Changing Colors](./README.md#changing-colors--branding)

---

### Common Git Commands
```bash
git status                    # Check changes
git add .                     # Stage all changes
git commit -m "Description"   # Commit with message
git push                      # Push to remote
```
*Detailed guide:* [MAINTENANCE.md - Version Control](./MAINTENANCE.md#backup--version-control)

---

## 🔍 Search Tips

**To find specific information:**

1. **Use your editor's search** (Ctrl+F / Cmd+F) across all `.md` files
2. **Check the TOC** at the top of README.md and MAINTENANCE.md
3. **Scan section headers** - they're designed to be descriptive

**Common search terms:**
- "add lesson" → Adding content guides
- "color" or "theme" → Customization sections
- "error" or "not working" → Troubleshooting sections
- "mobile" or "responsive" → Mobile responsiveness sections
- "sidebar" or "toc" → Navigation configuration

---

## 🆘 Still Can't Find What You Need?

1. **Check the index** at the top of this file ("I Want To...")
2. **Read the appropriate guide** based on your role (see Learning Path)
3. **Search the documentation** files for keywords
4. **Check Quarto docs** - https://quarto.org/docs/
5. **Create an issue** on GitHub with your question

---

## 📊 Documentation Stats

| File | Length | Audience | Time to Read |
|------|--------|----------|--------------|
| [README.md](./README.md) | ~600 lines | All users | 30 min |
| [QUICKSTART.md](./QUICKSTART.md) | ~200 lines | New users | 5 min |
| [MAINTENANCE.md](./MAINTENANCE.md) | ~650 lines | Maintainers | Reference |
| [CHANGELOG.md](./CHANGELOG.md) | ~100 lines | All users | 5 min |
| [PROJECT_SUMMARY.md](./PROJECT_SUMMARY.md) | ~400 lines | Managers | 15 min |
| **Total Documentation** | **~2000 lines** | **Various** | **1-2 hours** |

---

## 💡 Documentation Philosophy

Our documentation follows these principles:

1. **Beginner-friendly** - Assume no prior knowledge
2. **Task-oriented** - Focus on "how to do X"
3. **Well-organized** - Easy to navigate and scan
4. **Example-rich** - Show, don't just tell
5. **Up-to-date** - Maintained with code changes

---

## 🔄 Keeping Documentation Updated

When you make changes to the project:

1. **Update README.md** if you change features or workflow
2. **Update MAINTENANCE.md** if you change maintenance procedures
3. **Update CHANGELOG.md** with version and changes
4. **Keep examples accurate** - test all code snippets

---

## ✨ Make This Documentation Better

Found an error? Have a suggestion? Ways to contribute:

1. **Fix typos** - Create a PR with corrections
2. **Add examples** - Share useful patterns you've discovered
3. **Improve clarity** - Rewrite confusing sections
4. **Add screenshots** - Visual guides are helpful
5. **Create tutorials** - Write step-by-step walkthroughs

---

## 📞 Get Help

- 📖 **Documentation Issues**: Check this index and search guides
- 🐛 **Technical Issues**: See [MAINTENANCE.md - Troubleshooting](./MAINTENANCE.md#common-issues--solutions)
- 💬 **Questions**: GitHub Discussions or Issues
- 🆘 **Urgent**: Contact maintainers directly

---

**Happy documenting! 📚✨**

*This index is your map through the Minerva documentation ecosystem.*

---

Last updated: November 2025
