# IDS Sustainability Page - Joomla Implementation Guide

## Quick Start (5 Minutes)

### Option 1: All-in-One (Easiest)
1. Go to **Content → Articles → New**
2. Title: "Sustainability and Recycling"
3. Switch the editor to **Code/Source** mode
4. Copy the entire contents of `sustainability-complete-article.html`
5. Paste into the article editor
6. Save and close

**This includes everything:** CSS and HTML in one file. No separate CSS setup needed.

### Option 2: Separate CSS (For Custom CSS Field)
1. **Add CSS to Template:**
   - Go to **System → Site Templates → Your Template**
   - Find the **Custom CSS** field or **user.css** tab
   - Copy contents of `sustainability-joomla-scoped.css` and paste it
   - Save

2. **Add HTML to Article:**
   - Go to **Content → Articles → New**
   - Title: "Sustainability and Recycling"
   - Switch to **Code/Source** mode
   - Copy the HTML portion from `sustainability-complete-article.html` (everything inside the `<div class="sustainability-page">` tag)
   - Paste and save

### Step 2: Upload Images
1. Go to **Content → Media**
2. Create a folder: `images/sustainability/`
3. Upload your images with these names:
   - `hero-dumpster.png` - Main hero image
   - `benefit-1.jpg` through `benefit-4.jpg` - Benefit cards
   - `broad-run-facility.jpg` - Facility image
   - `broad-run-process.jpg` - Process image
   - `final-cta-bg.jpg` - Final CTA background

### Step 3: Update Links
1. Find all instances of `/contact` in the HTML
2. Replace with your actual contact page URL (e.g., `/contact-us` or `/index.php/contact`)

### Step 4: Test
1. View the article on your site
2. Test on mobile devices
3. Check all links work correctly
4. Verify images load properly

---

## Detailed Implementation Instructions

### Method 1: All-in-One (Recommended)

**Best for:** Quick setup, testing, or sites without custom CSS access

1. **Create Article:**
   - Go to **Content → Articles → New**
   - Set Title: "Sustainability and Recycling"
   - Set Category as appropriate
   - Switch editor to **Code/Source** mode
   - Copy entire contents of `sustainability-complete-article.html`
   - Paste into the editor
   - Save article

2. **Create Menu Item:**
   - Go to **Menus → [Your Menu] → Add New Menu Item**
   - Menu Item Type: **Articles → Single Article**
   - Select your sustainability article
   - Set menu title (e.g., "Sustainability")
   - Save and close

**Benefits:**
- Everything in one file (CSS + HTML + JavaScript)
- No template modifications needed
- Fully scoped and isolated
- Easy to backup and transfer

### Method 2: Separate CSS (Alternative)

**Best for:** Sites with custom CSS access, cleaner separation

1. **Add CSS to Template:**
   - Navigate to: **Extensions → Templates → Templates**
   - Click on your active template
   - Find the **Custom CSS** field or **user.css** tab
   - Paste the contents of `sustainability-joomla-scoped.css`
   - **Note:** CSS is scoped to `.sustainability-page` - won't affect other pages
   - Click **Save & Close**

2. **Create Article:**
   - Go to **Content → Articles → New**
   - Set Title: "Sustainability and Recycling"
   - Switch to **Code/Source** mode
   - Extract only the HTML portion from `sustainability-complete-article.html`
   - (Everything between `<div class="sustainability-page">` and its closing `</div>`)
   - Paste and save article

3. **Create Menu Item** (same as Method 1, step 2)

---

## Image Setup

### Required Images

| File Name | Dimensions | Description | Usage |
|-----------|-----------|-------------|--------|
| `hero-dumpster.png` | 800x600px min | Main hero image | Top of page, right side |
| `benefit-1.jpg` | 800x400px | Benefit card 1 | Sustainability section |
| `benefit-2.jpg` | 800x400px | Benefit card 2 | Sustainability section |
| `benefit-3.jpg` | 800x400px | Benefit card 3 | Sustainability section |
| `benefit-4.jpg` | 800x400px | Benefit card 4 | Sustainability section |
| `broad-run-facility.jpg` | 1200x600px | Facility exterior | Broad Run section |
| `broad-run-process.jpg` | 800x800px | Process/equipment | Broad Run section |
| `final-cta-bg.jpg` | 1920x1080px | Background image | Final CTA section |

### Image Upload Steps

1. **Via Joomla Media Manager:**
   - Go to **Content → Media**
   - Click **Create New Folder** → Name it "sustainability"
   - Navigate into the sustainability folder
   - Click **Upload** and select all your images
   - Verify images uploaded correctly

2. **Via FTP:**
   - Connect to your site via FTP
   - Navigate to `/images/`
   - Create folder: `sustainability`
   - Upload all images to `/images/sustainability/`

### Image Optimization Tips

- **Format:** Use WebP for better compression (with JPG fallback)
- **Size:** Keep all images under 500KB each
- **Dimensions:** Use exact dimensions listed above for best results
- **Tools:** Use TinyPNG or ImageOptim before uploading
- **Alt Text:** Already included in HTML for SEO

---

## Link Customization

### Update Internal Links

Find and replace these links in the HTML:

| Original Link | Replace With | Location |
|---------------|--------------|----------|
| `/contact` | Your contact page URL | Multiple locations |
| `#section-a-sustainability` | Keep as-is | Hero CTA (smooth scroll) |
| `#section-b-broadrun` | Keep as-is | Optional |
| `#section-c-reporting` | Keep as-is | Optional |

### Joomla Link Format Examples

```html
<!-- If using menu item alias: -->
<a href="/contact-us">Talk to IDS</a>

<!-- If using SEF URLs: -->
<a href="/index.php/contact">Talk to IDS</a>

<!-- If using menu item ID: -->
<a href="index.php?Itemid=123">Talk to IDS</a>
```

**How to Find Your Contact Page URL:**
1. Go to **Menus → Main Menu** (or your menu)
2. Find your Contact page
3. Note the **Alias** field - this becomes `/alias-name`
4. Or use the full URL from your live site

---

## Customization Guide

### Change Brand Colors

Edit the CSS variables at the top of `sustainability-joomla-scoped.css`:

```css
.sustainability-page {
    --ids-green: #145a3a;        /* Change to your primary color */
    --ids-green-dark: #0e3d26;   /* Darker shade for hovers */
}
```

**Where colors are used:**
- Buttons (primary and hover states)
- Links and underlines
- Section labels and eyebrows
- Icons and accents

### Adjust Spacing

```css
.sustainability-page {
    --container-max-width: 1280px;  /* Page width */
    --container-padding: 60px;      /* Side margins */
    --section-padding: 100px;       /* Section spacing */
}
```

**Tips:**
- Reduce `container-max-width` for narrower content
- Increase `section-padding` for more breathing room
- Adjust `container-padding` for mobile/desktop differences

### Modify Typography

```css
/* Change font family */
.sustainability-page {
    font-family: 'Your-Font', -apple-system, sans-serif;
}

/* Adjust heading sizes */
h1 {
    font-size: clamp(2.5rem, 5vw, 4rem); /* min, scale, max */
}
h2 {
    font-size: clamp(2rem, 4vw, 3rem);
}
```

### Button Styles

```css
/* Customize button appearance */
.btn {
    padding: 10px 20px;        /* Button padding */
    border-radius: 6px;        /* Corner roundness */
    font-size: 1rem;           /* Text size */
}

/* Larger buttons */
.btn-large {
    padding: 12px 28px;
}
```

### Section Background Colors

```css
/* Change section backgrounds */
.hero-section {
    background: transparent;    /* or #f9fafb for light gray */
}

.broadrun-section {
    background: #ffffff;        /* white background */
}

.reporting-section {
    background: #f9fafb;        /* light gray */
}

.final-cta-section {
    background: #f9fafb;        /* light gray */
}
```

---

## Troubleshooting

### Issue: CSS Not Loading

**Solution 1: Clear Joomla Cache**
1. Go to **System → Clear Cache**
2. Select all items
3. Click **Delete**
4. Reload the page

**Solution 2: Check CSS Location**
- Verify CSS file exists in correct location
- Check file permissions (should be 644)
- View page source and search for "sustainability" to see if CSS loaded

**Solution 3: Use Inline CSS**
- If external CSS fails, add `<style>` tags directly in article
- Paste minified CSS between `<style>` and `</style>`

### Issue: Images Not Showing

**Check Image Paths:**
```html
<!-- Default path -->
<img src="images/sustainability/hero-dumpster.png" />

<!-- If images are in different location, update all paths -->
<img src="/images/sustainability/hero-dumpster.png" />
<!-- or -->
<img src="media/images/sustainability/hero-dumpster.png" />
```

**Verify Image Upload:**
1. Go to **Content → Media**
2. Navigate to sustainability folder
3. Confirm all images are present
4. Check image file names match exactly (case-sensitive)

### Issue: Buttons Not Working

**Check Link URLs:**
- Verify `/contact` was replaced with actual URL
- Test links in browser
- Check for JavaScript errors in browser console

**Smooth Scroll Not Working:**
- Ensure JavaScript at bottom of HTML is present
- Check browser console for errors
- Try adding target section IDs if missing

### Issue: Layout Broken on Mobile

**Check Responsive CSS:**
- Ensure all media queries are included
- Test on actual mobile device, not just browser resize
- Check for conflicting template CSS

**Common Fixes:**
```css
/* Add if mobile view is too narrow */
@media (max-width: 768px) {
    .container {
        padding: 0 20px; /* More padding */
    }
}
```

### Issue: Template Conflicts

**Conflicting Styles:**
If template CSS conflicts with page CSS:

```css
/* Add higher specificity to page CSS */
.sustainability-page .hero-section {
    /* Your styles */
}

/* Or use !important (last resort) */
.hero-section {
    padding: 120px 0 !important;
}
```

### Issue: Fonts Not Loading

**Solution 1: Check Font Link**
Ensure Roboto font is loaded in template or article:
```html
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
```

**Solution 2: Use System Fonts**
```css
.sustainability-page {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
}
```

---

## Performance Optimization

### 1. Image Optimization

**Before Upload:**
- Resize to exact dimensions needed
- Compress with TinyPNG or ImageOptim
- Convert to WebP format with JPG fallback

**Lazy Loading (Optional):**
Add to all `<img>` tags:
```html
<img src="..." alt="..." loading="lazy">
```

### 2. CSS Optimization

**Already Minified:**
The `sustainability-joomla.min.css` file is already minified for production.

**Further Optimization:**
- Combine with site CSS to reduce HTTP requests
- Use Critical CSS for above-the-fold content
- Enable GZIP compression on server

### 3. JavaScript Optimization

**Current Script:**
- Minimal JavaScript (only smooth scroll)
- Already optimized and compressed
- Runs only after page load

**Optional: Remove JavaScript**
If smooth scrolling isn't needed, remove the `<script>` section entirely.

### 4. Caching

**Enable Joomla Cache:**
1. Go to **System → Global Configuration**
2. Click **System** tab
3. Set **Cache** to "ON - Conservative Caching"
4. Save

**Browser Caching:**
Add to `.htaccess`:
```apache
<IfModule mod_expires.c>
    ExpiresActive On
    ExpiresByType text/css "access plus 1 year"
    ExpiresByType image/jpeg "access plus 1 year"
    ExpiresByType image/png "access plus 1 year"
</IfModule>
```

---

## SEO Optimization

### Article Settings

1. **Title:** "Sustainability and Recycling | IDS Waste"
2. **Alias:** "sustainability-recycling" (for clean URLs)
3. **Meta Description:** Use the one from original file
4. **Meta Keywords:** sustainability, recycling, LEED, waste management, construction debris

### On-Page SEO

**Already Included:**
- Semantic HTML structure (h1, h2, h3, h4)
- Descriptive alt text on all images
- Proper heading hierarchy
- Internal linking structure
- External links with rel="noopener noreferrer"

**Additional Recommendations:**
- Enable SEF URLs in Joomla
- Add schema markup for Organization
- Submit to Google Search Console
- Monitor Core Web Vitals

---

## Accessibility Checklist

The page already includes:

- ✅ Semantic HTML structure
- ✅ Alt text on all images
- ✅ Sufficient color contrast
- ✅ Keyboard-navigable links and buttons
- ✅ Responsive design for all screen sizes
- ✅ Focus states on interactive elements
- ✅ SVG icons with proper semantics

**Test Accessibility:**
1. Use browser keyboard navigation (Tab key)
2. Test with screen reader (NVDA, JAWS, VoiceOver)
3. Run Lighthouse audit in Chrome DevTools
4. Check contrast with WebAIM Contrast Checker

---

## Browser Compatibility

**Tested and Working:**
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile Safari (iOS 14+)
- Chrome Mobile (Android 10+)

**Features Used:**
- CSS Grid (supported all modern browsers)
- CSS Custom Properties (IE11 not supported)
- Flexbox (universal support)
- clamp() function (modern browsers)

**IE11 Support:**
Not officially supported due to CSS custom properties, but graceful degradation occurs.

---

## Testing Checklist

### Before Launch

- [ ] All images load correctly
- [ ] All links work (especially /contact links)
- [ ] Buttons have hover states
- [ ] Smooth scroll works for anchor links
- [ ] Mobile view looks correct
- [ ] Tablet view looks correct
- [ ] Desktop view looks correct
- [ ] Text is readable (contrast)
- [ ] Forms work (if any)
- [ ] Page loads in under 3 seconds

### Cross-Browser Testing

- [ ] Chrome (desktop)
- [ ] Firefox (desktop)
- [ ] Safari (desktop)
- [ ] Edge (desktop)
- [ ] Safari (iOS)
- [ ] Chrome (Android)

### Functionality Testing

- [ ] Navigation works
- [ ] External links open in new tab
- [ ] Internal links scroll smoothly
- [ ] Images are sharp (not pixelated)
- [ ] Text is legible at all sizes
- [ ] Buttons are clickable
- [ ] Layout doesn't break on narrow screens

---

## Maintenance

### Regular Updates

**Quarterly:**
- Check for broken links
- Update images if needed
- Review content for accuracy
- Test on latest browsers

**Annually:**
- Review CSS for optimization opportunities
- Update color scheme if brand changes
- Add new features or sections
- Audit page performance

### Content Updates

**To Update Text:**
1. Go to **Content → Articles**
2. Find "Sustainability and Recycling" article
3. Click to edit
4. Switch to **Code/Source** mode
5. Make changes
6. Save and close

**To Update Images:**
1. Upload new image to **Content → Media**
2. Note the file name
3. Edit article in **Code/Source** mode
4. Find `<img src="images/sustainability/OLD-NAME.jpg">`
5. Replace with new file name
6. Save

### Version Control

**Keep Backups:**
- Save copy of working HTML
- Save copy of working CSS
- Document any customizations
- Note Joomla version and template used

---

## Support Resources

### Joomla Resources
- Joomla Documentation: https://docs.joomla.org/
- Joomla Forums: https://forum.joomla.org/
- Joomla Stack Exchange: https://joomla.stackexchange.com/

### CSS Resources
- MDN Web Docs: https://developer.mozilla.org/
- CSS-Tricks: https://css-tricks.com/
- Can I Use: https://caniuse.com/

### Testing Tools
- Google PageSpeed Insights: https://pagespeed.web.dev/
- GTmetrix: https://gtmetrix.com/
- WebAIM Contrast Checker: https://webaim.org/resources/contrastchecker/
- WAVE Accessibility Tool: https://wave.webaim.org/

---

## Quick Reference

### File Structure
```
joomla-implementation/
├── sustainability-complete-article.html     (Complete article with CSS + HTML + JS)
├── sustainability-joomla-scoped.css         (Scoped CSS - for custom CSS field)
└── IMPLEMENTATION-GUIDE.md                  (This file)
```

**Which files to use:**
- **Quick Setup:** Use `sustainability-complete-article.html` (recommended - all-in-one)
- **Separate CSS:** Use `sustainability-joomla-scoped.css` + HTML from complete article
```

### Color Variables Quick Reference
```css
--ids-green: #145a3a;           /* Primary brand color */
--ids-green-dark: #0e3d26;      /* Hover/active states */
--text-primary: #0c1018;        /* Body text */
--text-secondary: #353941;      /* Secondary text */
--text-muted: #6b7280;          /* Subtle text */
```

### Spacing Quick Reference
```css
--container-max-width: 1280px;  /* Page width */
--container-padding: 60px;      /* Side spacing */
--section-padding: 100px;       /* Vertical spacing */
```

---

## Need Help?

If you encounter issues not covered in this guide:

1. Check browser console for errors (F12 → Console tab)
2. Verify all files are in correct locations
3. Clear Joomla cache and browser cache
4. Test in different browser
5. Check for template conflicts
6. Review Joomla error logs

---

**Version:** 1.0
**Last Updated:** 2024
**Compatible With:** Joomla 3.x, 4.x, 5.x
