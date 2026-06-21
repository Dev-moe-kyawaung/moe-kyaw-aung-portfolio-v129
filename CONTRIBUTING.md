# Contributing to Moe Kyaw Aung Portfolio V129

Thank you for your interest in contributing! This document provides guidelines and instructions for contributing to this project.

---

## 🤝 Code of Conduct

Please read and follow our [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) to maintain a respectful and inclusive community.

---

## 📋 How to Contribute

### **1. Reporting Bugs**

If you find a bug, please open an issue with:
- **Clear title** describing the bug
- **Detailed description** of the issue
- **Steps to reproduce** the problem
- **Expected behavior** vs actual behavior
- **Screenshots** or code snippets if applicable
- **Environment** (browser, OS, etc.)

**Example:**
```markdown
## Bug: Contact form not submitting

### Description
The contact form displays a success message but doesn't actually send data.

### Steps to Reproduce
1. Open the portfolio website
2. Scroll to contact section
3. Fill in all fields
4. Click "Send Message"
5. Check network tab - no POST request

### Expected Behavior
Form should submit data to backend server

### Actual Behavior
Form shows success message without sending data

### Environment
- Browser: Chrome 120
- OS: Windows 10
```

### **2. Suggesting Enhancements**

Feature requests are welcome! Please provide:
- **Motivation** - Why is this feature useful?
- **Detailed description** - How should it work?
- **Possible implementation** - Your ideas
- **Alternative solutions** - Any other approaches?

**Example:**
```markdown
## Enhancement: Add blog section

### Motivation
Portfolio needs a blog to share technical content and improve SEO.

### Description
Add a new blog section with:
- Blog post listing page
- Individual post pages
- Category filtering
- Search functionality
- Comments section

### Implementation Ideas
- Could use markdown files for posts
- Could integrate with headless CMS
```

### **3. Pull Requests**

#### **Before You Start**
1. Fork the repository
2. Create a new branch for your feature
3. Make sure you have the latest changes
4. Follow the coding standards

#### **Process**
```bash
# 1. Fork and clone
git clone https://github.com/YOUR_USERNAME/moe-kyaw-aung-portfolio-v129.git
cd moe-kyaw-aung-portfolio-v129

# 2. Create feature branch
git checkout -b feature/amazing-feature

# 3. Make your changes
# ... edit files ...

# 4. Commit with clear messages
git commit -m "Add amazing feature: description"

# 5. Push to your fork
git push origin feature/amazing-feature

# 6. Open Pull Request on GitHub
```

#### **PR Guidelines**
- Use clear, descriptive title
- Reference related issues (#123)
- Describe what changes do
- Explain why changes are needed
- Include before/after if applicable
- Keep PR focused (one feature per PR)

**Example PR Description:**
```markdown
## Description
This PR adds dark/light mode toggle to portfolio website.

## Related Issue
Closes #45

## Changes
- Added theme toggle button in navbar
- Implemented CSS custom properties for theming
- Added localStorage persistence
- Updated all color variables

## Testing
- Tested in Chrome, Firefox, Safari
- Verified localStorage persistence
- Checked mobile responsiveness

## Screenshots
[Before/After screenshots]
```

---

## 🎨 Coding Standards

### **HTML**
- Use semantic HTML5 elements
- Proper document structure
- Descriptive id/class names
- Comments for complex sections

```html
<!-- Example: Good HTML -->
<section class="hero-section" id="home">
    <!-- Hero content -->
    <h1 class="hero-title">Title</h1>
    <p class="hero-description">Description</p>
</section>
```

### **CSS**
- Use CSS custom properties (variables)
- Follow mobile-first approach
- Proper media query structure
- Clear selector naming

```css
/* Example: Good CSS */
:root {
    --color-primary: #00d4ff;
    --spacing-lg: 2.5rem;
}

.button {
    padding: var(--spacing-sm);
    color: var(--color-primary);
}

@media (max-width: 768px) {
    .button {
        padding: var(--spacing-xs);
    }
}
```

### **JavaScript**
- Vanilla JavaScript preferred
- Clear variable names
- Comments for complex logic
- Event delegation where applicable

```javascript
// Example: Good JavaScript
document.addEventListener('DOMContentLoaded', () => {
    // Initialize features
    setupThemeToggle();
    setupScrollAnimations();
});

function setupThemeToggle() {
    // Toggle between light and dark themes
    const toggle = document.getElementById('themeToggle');
    toggle.addEventListener('click', changeTheme);
}
```

---

## 📝 Commit Messages

Use clear, descriptive commit messages:

```bash
# Good
git commit -m "Add dark mode toggle to navbar"
git commit -m "Fix: Contact form validation not working"
git commit -m "Improve mobile navigation responsiveness"

# Bad
git commit -m "Update"
git commit -m "Fix stuff"
git commit -m "Changes"
```

**Format:**
```
<type>: <description>

<optional body>
<optional footer>
```

**Types:**
- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation
- `style:` CSS/styling
- `refactor:` Code improvement
- `perf:` Performance improvement
- `test:` Tests
- `chore:` Build, dependencies

---

## 🧪 Testing

Before submitting a PR:

### **Browser Testing**
- [ ] Chrome/Edge (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Mobile browsers

### **Responsive Testing**
- [ ] Desktop (1920px+)
- [ ] Tablet (768px)
- [ ] Mobile (480px)
- [ ] Small phone (320px)

### **Feature Testing**
- [ ] Dark/light mode toggle
- [ ] Navigation menu
- [ ] Form submission
- [ ] Scroll animations
- [ ] Mobile hamburger menu
- [ ] Social links

### **Performance Testing**
- [ ] Lighthouse score > 90
- [ ] Page load time < 2s
- [ ] No console errors
- [ ] Smooth animations

---

## 📚 Documentation

If you add new features, please update:
- [ ] README.md (if it's a major feature)
- [ ] CHANGELOG.md (add entry)
- [ ] Inline code comments
- [ ] This CONTRIBUTING.md (if needed)

---

## 🎯 Development Workflow

### **Setup Development Environment**
```bash
# Clone repository
git clone https://github.com/Dev-moe-kyawaung/moe-kyaw-aung-portfolio-v129.git
cd moe-kyaw-aung-portfolio-v129

# Create feature branch
git checkout -b feature/your-feature-name

# Make changes to moe-kyaw-aung-portfolio-v129.html
# Open in browser: file:///path/to/file.html

# Test thoroughly
# Commit changes
git add .
git commit -m "feat: Your feature description"

# Push to fork
git push origin feature/your-feature-name

# Open Pull Request on GitHub
```

### **Local Testing**
```bash
# Using Python's simple server
python -m http.server 8000

# Using Node.js
npx http-server

# Using PHP
php -S localhost:8000

# Then open: http://localhost:8000/moe-kyaw-aung-portfolio-v129.html
```

---

## ✅ Contribution Checklist

Before submitting:
- [ ] Code follows style guidelines
- [ ] Changes are well-commented
- [ ] No console errors/warnings
- [ ] Tested on multiple browsers
- [ ] Responsive design works
- [ ] Updated documentation
- [ ] Added to CHANGELOG.md
- [ ] PR description is clear

---

## 🎓 Learning Resources

- [MDN Web Docs](https://developer.mozilla.org/)
- [Bootstrap 5 Docs](https://getbootstrap.com/docs/5.0/)
- [CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)

---

## 🚀 Recognition

Contributors will be:
- Added to CHANGELOG.md
- Mentioned in README.md contributors section
- Given credit in commits
- Recognized for their contributions

---

## 📞 Questions?

- **GitHub Issues** - Report bugs or suggest features
- **GitHub Discussions** - Ask questions, share ideas
- **Email** - hello@moekyawaung.dev

---

## 📜 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to make this portfolio better! 🙏

**Happy coding!** 🚀
