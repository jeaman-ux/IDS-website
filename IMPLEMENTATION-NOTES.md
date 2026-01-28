# Implementation Notes for Joomla Development Team

## Technical Implementation Guide

### Joomla Integration

This page is designed to be implemented as a standard Joomla article or custom component page within your existing Shaper HelixUltimate template.

#### Recommended Implementation Method

**Option 1: Custom HTML Module (Recommended)**
1. Create a new Joomla article
2. Set editor to "Code Editor" or disable WYSIWYG
3. Paste the HTML from `sustainability-recycling.html` (excluding the header placeholder section)
4. Assign the article to a menu item with URL alias: `sustainability-recycling`

**Option 2: Template Override**
1. Create a custom template override in `/templates/shaper_helixultimate/html/com_content/article/`
2. Implement the HTML structure within the Joomla template framework
3. This provides more control over the layout and module positions

### Header Integration

The HTML file includes this placeholder comment:
```html
<!-- REPLACE THIS SECTION WITH EXISTING JOOMLA SITE HEADER -->
```

Replace this with your standard Joomla header include:
```php
<jdoc:include type="modules" name="header" style="none" />
```

Or use your template's specific header structure.

### CSS Integration

The `sustainability-recycling.css` file contains all page-specific styles. Integrate it using one of these methods:

**Method 1: Template Custom CSS**
1. Add the CSS to your HelixUltimate template's custom CSS area
2. Navigate to: Components → HelixUltimate → Options → Custom Code
3. Paste the CSS into the "Custom CSS" field

**Method 2: Separate Stylesheet**
1. Upload `sustainability-recycling.css` to `/templates/shaper_helixultimate/css/`
2. Enqueue the stylesheet in your template or article using:
```php
JHtml::_('stylesheet', 'templates/shaper_helixultimate/css/sustainability-recycling.css');
```

**Method 3: Page-Specific CSS (Easiest)**
1. In the article settings, use the "Custom CSS" field if available
2. Or add a `<style>` tag directly in the article HTML

### JavaScript Components

The page includes two interactive components:

#### 1. Accordion Functionality
- Pure vanilla JavaScript, no dependencies
- Automatically initializes on page load
- Uses `.accordion-item` and `.accordion-content` classes
- Supports multiple accordions per page

#### 2. Tab Functionality
- Pure vanilla JavaScript, no dependencies
- Automatically initializes on page load
- Uses `.tab-button` and `.tab-panel` classes
- Aria attributes for accessibility

Both components are included inline in the HTML file. If you prefer external JavaScript:
1. Extract the `<script>` tags to a separate `.js` file
2. Enqueue using Joomla's script system

### Responsive Design

The page uses standard media queries:
- **Mobile-first approach**
- **Breakpoint at 768px** for tablet and up
- **Breakpoint at 992px** for desktop

Matches your existing site's breakpoints:
- Tablet: 991px (from existing site analysis)
- Mobile: 480px (from existing site analysis)

### Accessibility Considerations

The HTML includes:
- Semantic HTML5 elements (`<section>`, `<article>`, `<nav>`)
- Proper heading hierarchy (H1 → H2 → H3)
- ARIA attributes for accordion and tab components
- Alt text placeholders for any images you may add
- Keyboard navigation support for interactive elements

### Testing Checklist

#### Functionality Tests
- [ ] All CTAs link to correct destinations
- [ ] Contact page links work (`/contact` or your contact URL)
- [ ] External Broad Run Recycling links open in new tabs
- [ ] Accordion expands/collapses smoothly
- [ ] Tab switching works properly
- [ ] Only one accordion can be open at a time (or multiple, based on preference)

#### Responsive Tests
- [ ] Test on mobile devices (320px to 767px)
- [ ] Test on tablets (768px to 991px)
- [ ] Test on desktop (992px and up)
- [ ] Verify no horizontal scroll on mobile
- [ ] Verify CTAs are easily tappable (min 44px touch target)

#### Browser Compatibility
- [ ] Chrome/Edge (Chromium)
- [ ] Firefox
- [ ] Safari (desktop and iOS)
- [ ] Mobile browsers (Android Chrome, iOS Safari)

#### Joomla-Specific Tests
- [ ] Page renders correctly within HelixUltimate template
- [ ] No conflicts with existing template CSS
- [ ] No JavaScript errors in console
- [ ] Page loads within acceptable performance metrics

### Performance Optimization

1. **CSS Minification:** Minify the CSS file before production
2. **Lazy Loading:** If images are added, implement lazy loading
3. **Cache:** Ensure Joomla caching is enabled for static content
4. **CDN:** Use existing CDN for any external resources

### Content Management

Make these elements easily editable for future updates:
- All body copy and bullet points
- CTA button text and links
- External links (Broad Run website)
- Contact page URL
- Color scheme variables (consider using CSS custom properties)

### Known Considerations

1. **E-commerce Integration:** The page does not include EasyStore components but can coexist with your existing e-commerce setup
2. **Analytics:** Add Google Analytics event tracking to CTAs if desired
3. **Conversion Tracking:** Consider adding conversion pixels to the contact form CTAs
4. **SEO:** Ensure proper meta tags, Open Graph tags, and schema markup are added via Joomla

### Support and Modifications

If modifications are needed:
- The HTML structure uses clear, semantic class names
- CSS is organized by section with clear comments
- JavaScript is well-commented and modular
- All interactive elements degrade gracefully without JavaScript

### Recommended Joomla Extensions

Consider these extensions for enhanced functionality:
- **Custom CSS and JavaScript:** For easier code management
- **Regular Labs Advanced Module Manager:** For flexible module placement
- **Accessibility Checker:** To verify WCAG compliance

## Questions or Issues?

If you encounter any technical issues during implementation or need clarification on any design decisions, please refer back to the original specifications or the README.md file in this package.
