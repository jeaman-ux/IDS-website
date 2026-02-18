# Joomla Implementation Guide
## Sustainability & Recycling Page

**Quick Implementation Time:** 15-20 minutes
**Difficulty:** Easy
**Last Updated:** February 16, 2026

---

## 📋 What You Need

- ✅ Joomla admin access (Administrator level)
- ✅ Ability to create/edit articles
- ✅ Access to template custom CSS (or use article custom CSS)
- ✅ Hero image file: `hero-dumpster.png` (or your own image)

---

## 🚀 Quick Start (3 Steps)

### Step 1: Create New Article (5 min)

1. Log into Joomla admin: `https://idswaste.com/administrator/`
2. Go to **Content → Articles → New**
3. Set these fields:
   - **Title:** Sustainability and Recycling
   - **Alias:** `sustainability-recycling`
   - **Category:** Choose appropriate category
   - **Status:** Published

### Step 2: Add HTML Content (5 min)

1. Switch editor to **Code/Source** mode (click the `<>` button)
2. Open file: `joomla-content.html`
3. **Copy ALL content** from that file
4. **Paste** into the article editor
5. Click **Save**

### Step 3: Add CSS (5 min)

**Option A: Template Custom CSS (Recommended)**
1. Go to **Extensions → Templates → Your Template**
2. Find **Custom CSS** field
3. Open file: `sustainability-recycling.css`
4. Copy ALL CSS
5. Paste at the bottom of Custom CSS field
6. Click **Save**

**Option B: Article Custom CSS**
1. In your article editor, look for **Custom CSS** field
2. Paste the CSS there
3. Click **Save**

**Option C: Add as stylesheet**
1. Upload `sustainability-recycling.css` to `/templates/your-template/css/`
2. Add this to your template's `index.php`:
```php
$doc->addStyleSheet('templates/your-template/css/sustainability-recycling.css');
```

---

## 🎨 Customization Guide

### Change Colors

Find these CSS variables at the top of the CSS file:

```css
:root {
    --ids-green: #145a3a;        /* Main brand color */
    --ids-green-dark: #0e3d26;   /* Darker shade */
    --text-primary: #0c1018;     /* Main text */
    --text-secondary: #353941;   /* Secondary text */
}
```

**To change colors:**
1. Find the `:root` section in your CSS
2. Replace the hex colors with your brand colors
3. Save and refresh

### Update Contact Links

All contact buttons link to `/contact`. To change:

**Find and replace in HTML:**
- Old: `href="/contact"`
- New: `href="/your-contact-page"`

### Update External Links

Broad Run Recycling links:
- Main site: `https://www.broadrunrecycling.com/`
- Materials page: `https://www.broadrunrecycling.com/materials`

**To change:**
Find these URLs in the HTML and replace with your preferred links.

### Change Images

The page uses one main image: `hero-dumpster.png`

**To replace:**
1. Upload your image to Joomla Media Manager
2. In HTML, find: `src="assets/images/hero-dumpster.png"`
3. Replace with: `src="images/your-folder/your-image.jpg"`

### Adjust Spacing

**Section padding (space between sections):**
```css
section {
    padding: 140px 0;  /* Change to 80px, 100px, 160px, etc. */
}
```

**Button spacing:**
```css
.btn {
    padding: 14px 32px;  /* Adjust padding */
}
```

---

## 📱 Mobile Optimization

The page is fully responsive. Test on:
- Mobile (< 768px)
- Tablet (768px - 991px)
- Desktop (> 992px)

**Mobile settings are in CSS under:**
```css
@media (max-width: 768px) { ... }
@media (max-width: 480px) { ... }
```

---

## ✅ Post-Implementation Checklist

After adding the page, verify:

### Content
- [ ] All text displays correctly
- [ ] No missing sections
- [ ] Headings are properly sized
- [ ] Lists are formatted correctly

### Links
- [ ] "Talk to IDS" buttons go to contact page
- [ ] "See How IDS Supports Sustainability" scrolls to section
- [ ] Broad Run links open in new tabs
- [ ] All external links have `rel="noopener noreferrer"`

### Design
- [ ] Colors match your brand
- [ ] Fonts are consistent with site
- [ ] Hero image displays correctly
- [ ] Buttons look correct
- [ ] Green accent color shows on hover

### Responsive
- [ ] Test on actual mobile device
- [ ] Test on tablet
- [ ] Check all breakpoints in browser dev tools
- [ ] Verify no horizontal scrolling on mobile

### Interactivity
- [ ] Smooth scroll to sections works
- [ ] Hover effects on buttons work
- [ ] Comparison section displays properly
- [ ] All CTAs are clickable

---

## 🐛 Troubleshooting

### CSS Not Applying

**Problem:** Page looks broken, no styling
**Solution:**
1. Clear Joomla cache: System → Clear Cache
2. Clear browser cache: Ctrl+F5 or Cmd+Shift+R
3. Check CSS was pasted in correct location
4. Verify no CSS syntax errors

### Images Not Showing

**Problem:** Broken image icons
**Solution:**
1. Upload images to Joomla Media Manager
2. Update image paths in HTML to match Joomla structure
3. Example: `src="images/sustainability/hero-dumpster.png"`

### Links Not Working

**Problem:** Clicking buttons does nothing
**Solution:**
1. Verify Joomla hasn't added extra HTML
2. Check link URLs are correct for your site
3. Ensure smooth scroll JavaScript is included at bottom

### Layout Broken on Mobile

**Problem:** Content overlaps or looks wrong on phone
**Solution:**
1. Check mobile CSS is included
2. Test with browser dev tools mobile emulation
3. Verify viewport meta tag is in Joomla template

### Section Spacing Too Large/Small

**Problem:** Too much or too little space between sections
**Solution:**
1. Find `section { padding: 140px 0; }` in CSS
2. Change to smaller (80px) or larger (180px) value
3. Test on desktop and mobile

---

## 🎯 SEO Optimization

### Meta Description
Add in article settings:
```
IDS delivers reliable waste service with documented recycling and LEED ready diversion reporting through our partnership with Broad Run Recycling.
```

### Meta Keywords
```
waste management, recycling, LEED reporting, sustainability, construction debris, Broad Run Recycling, diversion reporting
```

### Open Graph (Social Sharing)
If your template supports it, add:
- **OG Title:** Sustainability & Recycling | IDS Waste
- **OG Description:** Recycling you can prove - documented diversion reporting for LEED compliance
- **OG Image:** Upload hero image and use that URL

---

## 📊 Analytics Tracking

### Add Event Tracking to CTAs

If you use Google Analytics, add tracking to buttons:

```html
<!-- Example -->
<a href="/contact"
   class="btn btn-primary"
   onclick="gtag('event', 'click', {'event_category': 'CTA', 'event_label': 'Sustainability CTA'});">
   Contact IDS
</a>
```

---

## 🔄 Updates & Maintenance

### Quarterly Review
- [ ] Check all external links still work
- [ ] Update statistics if needed (700+ Tons Daily, etc.)
- [ ] Review content for accuracy
- [ ] Test on new devices/browsers

### Content Updates
To update text:
1. Go to Content → Articles
2. Find "Sustainability and Recycling"
3. Click Edit
4. Switch to Code view
5. Update text
6. Save

---

## 💡 Tips for Success

1. **Test First:** Always test on a staging site if available
2. **Backup:** Create a backup before making changes
3. **Browser Cache:** Always hard refresh (Ctrl+F5) to see changes
4. **Mobile First:** Always test mobile view
5. **Accessibility:** Ensure keyboard navigation works
6. **Performance:** Use optimized images (WebP format, compressed)

---

## 📞 Need Help?

If you encounter issues:

1. Check browser console for errors (F12 → Console tab)
2. Verify all files were copied completely
3. Ensure Joomla isn't adding extra markup
4. Test with all Joomla plugins temporarily disabled
5. Check template doesn't have conflicting CSS

---

## 🎉 You're Done!

Your sustainability page should now be live at:
**https://idswaste.com/sustainability-recycling**

Share it with your team and start driving conversions!
