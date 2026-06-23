# Christi Elliott Portfolio & Course Platform

## Overview

This is a personal portfolio and business website for Christi Elliott, a web designer specializing in custom web design, responsive design, user experience, and brand integration. The project also includes an interactive lash course platform.

**Repository:** `christielliott/Christi-Elliott`  
**Type:** Static HTML/CSS/JavaScript website  
**Primary Purpose:** Professional portfolio, service showcase, and educational course delivery

---

## Project Structure

```
/
├── index.html              # Home page with hero, services, and featured work
├── portfolio.html          # Portfolio gallery showcasing client projects
├── about.html              # About page with background and expertise
├── contact.html            # Contact form for inquiries
├── course.html             # Interactive lash course with 16 modules and 69 lessons
├── style.css               # Shared CSS with design system variables
├── script.js               # Vanilla JavaScript for interactivity
├── images/                 # Image assets (currently empty with .gitkeep)
└── CLAUDE.md               # This file
```

### Page Structure & Responsibilities

- **index.html** - Landing page with hero section, service cards, and featured project showcase
- **portfolio.html** - Grid-based portfolio showcasing client work (currently features "Pink Panther" project)
- **about.html** - Background information and professional expertise
- **contact.html** - Contact form with validation and success feedback
- **course.html** - Interactive course platform with module-based learning and progress tracking

---

## Design System & Styling

### CSS Variables (in style.css)

The project uses a centralized design system with CSS custom properties:

```css
:root {
    --primary: #d946a6;        /* Magenta/Pink - main brand color */
    --primary-dark: #b30d8d;   /* Darker pink for hover states */
    --accent: #fbbf24;         /* Amber/Gold - accent color */
    --dark: #1f2937;           /* Dark gray - text */
    --light: #f9fafb;          /* Light gray - backgrounds */
    --gray: #6b7280;           /* Medium gray - secondary text */
    --border: #e5e7eb;         /* Light gray - borders */
}
```

### Key CSS Patterns

- **Responsive container:** `.container` class with max-width: 1200px and 20px padding
- **Navigation:** Sticky navbar with active state indicators
- **Cards:** Service cards and portfolio items use consistent styling with hover effects
- **Animations:** Fade-in on scroll using Intersection Observer API
- **Grid layouts:** CSS Grid for service cards and portfolio items

---

## JavaScript Functionality

### Core Features (script.js)

1. **Contact Form Handling**
   - Form submission prevention and validation
   - Collects: name, email, company, message
   - Shows success toast notification (fixed position, top-right)
   - Auto-removes notification after 3 seconds
   - Resets form after successful submission

2. **Smooth Scroll Navigation**
   - Intercepts anchor links (`<a href="#...">`)
   - Uses `scrollIntoView({ behavior: 'smooth' })` for smooth transitions
   - Ignores special links (#, #privacy)

3. **Intersection Observer for Animations**
   - Targets: `.service-card`, `.portfolio-item`, `.skill` elements
   - Applies fade-in + slide-up animation on scroll
   - Observes at 10% visibility threshold with 50px bottom margin

### Development Notes

- Pure vanilla JavaScript (no frameworks)
- DOM-ready: All scripts execute after `DOMContentLoaded` event
- No external dependencies
- Animations handled with CSS transitions triggered by JavaScript

---

## Course Platform Details (course.html)

### Structure

- **16 Modules** with 69 total lessons
- **Progress Tracking** - Visual progress bar and completion percentage
- **Module States** - Expandable/collapsible lesson lists
- **Responsive Design** - Adapts to all screen sizes

### Course Features

- Interactive module expand/collapse
- Individual lesson tracking and completion marking
- Progress percentage calculation
- Smooth animations on state changes
- Gradient color scheme (purple/blue theme distinct from main brand)

---

## Current Development State

### Recent Changes (from git log)

1. **Latest** (171478c) - Merged PR #1: "Create lash course with comprehensive modules"
2. (8c67984) - Updated course with 16 modules and 69 lessons
3. (a1bd38d) - Created interactive lash course with 6 modules (initial)
4. (d7e886c) - Initial portfolio website build

### Active Branches

- `claude/claude-md-docs-2b835g` - Current documentation branch
- `claude/build-portfolio-website-CO8wU` - Portfolio development branch

---

## Development Workflows

### Adding New Portfolio Projects

1. Create new section in `portfolio.html` with class `portfolio-item`
2. Add project image to `/images` directory
3. Include project metadata:
   - Title (`<h3>`)
   - Category (`.project-category`)
   - Description (`.project-description`)
   - Technology tags (`.tag` elements)
   - Link to project (`.project-link`)
4. Styling automatically applies via existing CSS classes

### Modifying the Design System

1. Edit CSS variables in `:root` selector (style.css, lines 7-15)
2. All pages inherit changes automatically via CSS cascade
3. Common color updates:
   - Primary/brand colors: `--primary`, `--primary-dark`
   - Accent colors: `--accent`
   - Text colors: `--dark`, `--gray`
   - Background/border colors: `--light`, `--border`

### Adding Course Modules

1. Add new module section in `course.html`
2. Include module header with title and expand toggle
3. Nest lesson items within module container
4. Each lesson should have:
   - Lesson title
   - Content or learning objectives
   - Checkbox or completion indicator
5. Progress tracking automatically updates based on completed lessons

### Form Updates & Contact Handling

1. Form fields are defined in `contact.html`
2. Form submission logic in `script.js` (lines 2-41)
3. Currently logs to console - **no backend integration yet**
4. To integrate email backend:
   - Replace `console.log()` with API call
   - Implement server endpoint to send email
   - Consider using Formspree, SendGrid, or similar service

---

## Testing & Verification

### Manual Testing Checklist

- [ ] **Navigation** - All links between pages work, active states display correctly
- [ ] **Responsive Design** - Pages render correctly on mobile (< 768px), tablet (768px-1024px), desktop
- [ ] **Contact Form** - Submission shows success message, form resets
- [ ] **Course Interactivity** - Modules expand/collapse, progress updates, lessons mark complete
- [ ] **Animations** - Fade-in effects trigger on scroll, smooth navigation works
- [ ] **Images** - All portfolio and course images load correctly

### Browser Compatibility

- Target modern browsers (Chrome, Firefox, Safari, Edge)
- CSS Grid, Flexbox, and Intersection Observer API supported
- Smooth scroll behavior available in all modern browsers

---

## Key Conventions for AI Assistants

### Naming Conventions

- **Classes:** kebab-case (`.service-card`, `.portfolio-item`, `.course-progress`)
- **IDs:** kebab-case (`.contactForm`, `#pink-panther`)
- **CSS Variables:** kebab-case with `--` prefix (`--primary`, `--primary-dark`)
- **HTML Attributes:** Standard lowercase (`id`, `class`, `href`, `alt`)

### Code Style Guidelines

- **HTML:** Semantic structure, 4-space indentation
- **CSS:** Organized by component, comments before major sections
- **JavaScript:** Vanilla JS preferred, event-driven architecture
- **Comments:** Only for non-obvious logic; code should be self-documenting

### When Modifying Code

1. **Test all pages** - Changes may impact multiple files through shared CSS
2. **Preserve responsive design** - Mobile-first approach, test at 320px+ widths
3. **Maintain accessibility** - Use semantic HTML, include alt text for images
4. **Keep animations smooth** - Use `transition` and `transform` for 60fps performance
5. **No external dependencies** - Stick with vanilla JS and CSS3 features

### Common Tasks

**Update styling across all pages:**
```
Edit style.css → Changes propagate to all HTML files via <link>
```

**Add interactivity to a new element:**
```
1. Add element to HTML page
2. Target via selector in script.js
3. Attach event listener in DOMContentLoaded block
```

**Create new page:**
```
1. Create new .html file
2. Copy navbar and footer structure from existing page
3. Link in navbar nav-menu on all pages
4. Styling inherited from shared style.css
```

---

## Performance Considerations

- Lightweight codebase with no build process needed
- Single CSS file for all pages (consider CSS splitting if file grows beyond 15KB)
- Vanilla JS keeps bundle size minimal
- Intersection Observer is efficient for scroll animations
- Images should be optimized before commit to `/images` directory

---

## Future Enhancement Opportunities

1. **Course Backend** - Database for user progress persistence (Firebase, Supabase)
2. **Contact Form Backend** - Email integration (Formspree, Mailgun, AWS SES)
3. **Portfolio CMS** - Headless CMS for easy project updates
4. **Analytics** - Google Analytics or similar for tracking page views
5. **SEO Optimization** - Meta tags, structured data, sitemap.xml
6. **Blog Section** - Markdown-based blog for articles and tutorials
7. **Project Filtering** - Category/tag based portfolio filtering
8. **User Accounts** - Login system for course progress tracking

---

## Troubleshooting

### Navigation Not Working

- Check all `href` attributes point to correct HTML files
- Verify `.active` class applied to current page link
- Ensure file names match exactly (case-sensitive)

### Form Not Submitting

- Verify form element has `id="contactForm"`
- Check all input fields have correct `id` attributes
- Ensure `script.js` is loaded after HTML content

### Animations Not Triggering

- Verify elements have required classes (`.service-card`, `.portfolio-item`, etc.)
- Check browser DevTools for Intersection Observer support
- Ensure `script.js` loads before page content

### Styling Issues

- Clear browser cache and hard refresh (Ctrl+Shift+R or Cmd+Shift+R)
- Check CSS selector specificity
- Verify CSS variables are defined in `:root` block
- Use browser DevTools to inspect computed styles

---

## Getting Help

- Review git log for context on previous changes: `git log --oneline`
- Check active branches for ongoing work: `git branch -a`
- Test locally before committing changes
- Run manual testing checklist before creating pull requests
