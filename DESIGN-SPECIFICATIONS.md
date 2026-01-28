# Design Specifications - Sustainability and Recycling Page

**Project:** IDS Website Improvements
**Page:** Sustainability and Recycling
**Date:** January 26, 2026
**URL:** `/sustainability-recycling`

---

## Page Structure Overview

```
┌─────────────────────────────────────────┐
│         EXISTING SITE HEADER            │
└─────────────────────────────────────────┘
┌─────────────────────────────────────────┐
│  SECTION 1: HERO                        │
│  • H1: Recycling You Can Prove          │
│  • Intro copy                           │
│  • 2 CTAs (internal anchor + contact)   │
└─────────────────────────────────────────┘
┌─────────────────────────────────────────┐
│  SECTION 2: SUSTAINABILITY              │
│  • H2: Sustainability You Can Stand...  │
│  • Body copy                            │
│  • 4 bullet points                      │
│  • CTA (contact)                        │
└─────────────────────────────────────────┘
┌─────────────────────────────────────────┐
│  SECTION 3: BROAD RUN RECYCLING         │
│  • H2: Meet Broad Run Recycling         │
│  • Body copy + materials link           │
│  • ACCORDION: Why Broad Run             │
│  • TAB: Why Quality Matters             │
│  • CTA BAND (full width)                │
└─────────────────────────────────────────┘
┌─────────────────────────────────────────┐
│  SECTION 4: ACCURATE REPORTING          │
│  • H2: Why Accurate Reporting Matters   │
│  • Body copy                            │
│  • 5 bullet points (risks)              │
│  • CTA (contact)                        │
│  • ACCORDION: Comparison table          │
└─────────────────────────────────────────┘
┌─────────────────────────────────────────┐
│  SECTION 5: FINAL CTA                   │
│  • H2: Let's simplify recycling...      │
│  • Primary button (contact)             │
│  • Text link (Broad Run)                │
└─────────────────────────────────────────┘
┌─────────────────────────────────────────┐
│         EXISTING SITE FOOTER            │
└─────────────────────────────────────────┘
```

---

## Design System

### Colors

| Element | Color | Hex Code |
|---------|-------|----------|
| Primary Brand Green | IDS Green | `#145a3a` |
| Primary Green (Hover) | Darker Green | `#0e3d26` |
| Text Primary | Charcoal | `#171717` |
| Text Secondary | Gray | `#333` |
| Text Muted | Light Gray | `#555` |
| Background Light | Off-white | `#f9f9f9` |
| Background Dark | Dark Gray | `#171717` |
| Error/Shortcut | Red | `#d9534f` |
| Border | Light Gray | `#ddd` |

### Typography

**Font Family:** Roboto (Sans-serif)

| Element | Size | Weight | Line Height |
|---------|------|--------|-------------|
| H1 | 48px (3rem) | 700 | 1.3 |
| H2 | 32px (2rem) | 700 | 1.3 |
| H3 | 24px (1.5rem) | 700 | 1.3 |
| H4 | 20px (1.25rem) | 600 | 1.3 |
| Body | 16px (1rem) | 400 | 1.6 |
| Large Body | 18px (1.125rem) | 400 | 1.7-1.8 |
| Button | 16px (1rem) | 500 | - |

### Spacing

- **Section Padding:** 60px vertical (desktop), 40px (mobile)
- **Container Max Width:** 1200px
- **Container Padding:** 20px horizontal (15px on mobile)
- **Element Margin Bottom:** 16px (1rem) standard
- **Large Gaps:** 24-40px (1.5-2.5rem)

### Buttons

#### Primary Button
- Background: `#145a3a` (IDS Green)
- Text: White
- Padding: 14px 28px
- Border Radius: 4px
- Hover: Darker green `#0e3d26`

#### Secondary Button
- Background: Transparent
- Text: `#145a3a` (IDS Green)
- Border: 2px solid `#145a3a`
- Hover: Filled with green, white text

#### Text Link Button
- Background: Transparent
- Text: `#145a3a` (IDS Green)
- No border
- Hover: Underline + darker color

#### Large Button
- Padding: 18px 36px
- Font Size: 18px (1.125rem)

---

## Responsive Breakpoints

### Desktop (992px and up)
- Full layout
- Two-column comparison grid
- Horizontal button layouts

### Tablet (768px - 991px)
- Slightly reduced font sizes
- Single column comparison grid
- Stacked button layouts (vertical)
- Max button width: 400px

### Mobile (Up to 767px)
- Reduced padding (40px section padding)
- Smaller typography scale
- Full-width buttons
- Single column layouts

### Very Small Mobile (Up to 480px)
- Minimum font sizes
- 15px container padding
- Compact accordion/tab headers

---

## Interactive Components

### Accordion Component

**Structure:**
```
┌────────────────────────────────────┐
│  [+] Accordion Title               │  ← Click to expand
├────────────────────────────────────┤
│  Hidden content area               │  ← Expands smoothly
│  • Bullet points                   │
│  • Links                           │
└────────────────────────────────────┘
```

**Behavior:**
- Click header to expand/collapse
- Icon changes from `+` to `−`
- Smooth max-height transition
- Aria attributes for accessibility

**Styling:**
- Border: 1px solid `#ddd`
- Background: White
- Hover: Light gray `#f5f5f5`
- Padding: 1.25rem (header), 1.5rem (body)

### Tab Component

**Structure:**
```
┌────────────────────────────────────┐
│  [Tab 1 (Active)] │ Tab 2 │ Tab 3 │  ← Tab headers
├────────────────────────────────────┤
│  Tab 1 Content (visible)           │  ← Content area
│  • Bullet points                   │
│  • Body text                       │
└────────────────────────────────────┘
```

**Behavior:**
- Click tab header to switch content
- Only one tab visible at a time
- Active tab highlighted with bottom border
- Aria attributes for accessibility

**Styling:**
- Header Background: Light gray `#f5f5f5`
- Active Background: White
- Active Border Bottom: 3px solid `#145a3a`
- Content Padding: 2rem

---

## Content Hierarchy

### Emphasized Text

1. **Hero Highlight:** Bold or colored text in hero section
   - "We are built for heavy waste and committed to a lighter impact"
   - Color: `#145a3a` or Bold

2. **Underlined/Italicized:**
   - Use `<em>` for "assumed" in comparison
   - Use `<strong>` for key terms in IDS Approach

3. **Links:**
   - External: Open in new tab (`target="_blank" rel="noopener noreferrer"`)
   - Internal: Regular navigation
   - Anchor: Smooth scroll behavior

---

## External Links Reference

| Link Text | Destination | Type |
|-----------|-------------|------|
| Broad Run Recycling | https://www.broadrunrecycling.com/ | External |
| View materials accepted | https://www.broadrunrecycling.com/materials | External |
| Contact IDS | /contact | Internal |
| See How IDS Supports... | #section-a-sustainability | Anchor |

---

## CTA Placement Strategy

**Total CTAs:** 7

1. **Hero Section (2 CTAs):**
   - Primary: "See How IDS Supports Sustainability" (anchor link)
   - Secondary: "Talk to IDS About Recycling..." (contact)

2. **Section A (1 CTA):**
   - "Contact IDS to Get Started" (contact)

3. **Section B CTA Band (1 CTA):**
   - "Contact IDS to Get Started" (contact)

4. **Section C (1 CTA):**
   - "Mitigate Risk. Get Accurate Reporting" (contact)

5. **Final Section (2 CTAs):**
   - Primary: "Talk to IDS" (contact)
   - Secondary: "Explore Broad Run Recycling" (external link)

---

## Accessibility Features

✅ Semantic HTML5 elements
✅ Proper heading hierarchy (H1 → H2 → H3)
✅ ARIA attributes for accordions and tabs
✅ Keyboard navigation support
✅ Focus states for interactive elements
✅ Alt text support for images (if added)
✅ Color contrast meets WCAG AA standards
✅ External links open in new tabs with proper rel attributes

---

## SEO Considerations

**Title Tag:** "Sustainability and Recycling | IDS Waste"

**Meta Description:** "IDS delivers reliable waste service with documented recycling and LEED-ready diversion reporting through our partnership with Broad Run Recycling."

**Keywords:**
- Construction waste recycling
- LEED diversion reporting
- Sustainability compliance
- C&D recycling
- Broad Run Recycling
- Washington DC waste management

**Schema Markup Recommendations:**
- Organization schema for IDS
- Service schema for waste services
- LocalBusiness schema if applicable

---

## Performance Checklist

- [ ] Minify CSS for production
- [ ] Optimize images (if added) - use WebP format
- [ ] Lazy load images below the fold
- [ ] Enable browser caching
- [ ] Enable Joomla page caching
- [ ] Test page load speed (target < 3 seconds)
- [ ] Test Core Web Vitals (LCP, FID, CLS)

---

## Browser Compatibility

**Minimum Support:**
- Chrome/Edge (Chromium): Last 2 versions
- Firefox: Last 2 versions
- Safari: Last 2 versions
- Mobile Safari (iOS): Last 2 versions
- Chrome Mobile (Android): Last 2 versions

**JavaScript Features Used:**
- addEventListener
- querySelector/querySelectorAll
- classList
- getAttribute/setAttribute
- Arrow functions (ES6)
- Template literals (ES6)

All features are widely supported. For older browser support, consider adding polyfills.

---

## Testing Scenarios

### Functional Testing
1. Click all CTAs → Verify correct navigation
2. Expand/collapse all accordions → Verify smooth animation
3. Switch between tabs → Verify content displays correctly
4. Click anchor links → Verify smooth scroll to section
5. Click external links → Verify new tab opens

### Visual Testing
1. Check responsive layout at all breakpoints
2. Verify font rendering matches design system
3. Check button hover states
4. Verify color consistency with brand guidelines
5. Test in light/dark mode (if applicable)

### Performance Testing
1. Run Lighthouse audit (target score > 90)
2. Test page load on 3G connection
3. Verify no layout shifts (CLS < 0.1)
4. Check JavaScript console for errors

---

## Implementation Priority

**Phase 1: Core Structure** ✅
- HTML structure
- CSS styling
- Basic JavaScript functionality

**Phase 2: Integration**
- Integrate with Joomla template
- Replace header/footer placeholders
- Update internal links
- Add to site navigation

**Phase 3: Testing**
- Cross-browser testing
- Responsive testing
- Accessibility audit
- Performance optimization

**Phase 4: Launch**
- Final QA
- Analytics setup
- Update sitemap
- Deploy to production

---

## Notes for Developers

1. **Joomla Template:** This page is designed to work with Shaper HelixUltimate but uses minimal template-specific code for maximum portability.

2. **JavaScript:** All JavaScript is vanilla (no dependencies). If jQuery is preferred, the code can be easily converted.

3. **CSS Methodology:** CSS uses a simple class-based approach with clear naming conventions. Can be adapted to BEM or other methodologies if needed.

4. **Content Updates:** All content is in the HTML file for easy editing by content managers.

5. **Scalability:** The accordion and tab components can handle multiple items if needed in future updates.

---

## Change Log

| Date | Version | Changes |
|------|---------|---------|
| 2026-01-26 | 1.0 | Initial design package created |

---

**Questions?** Refer to README.md or IMPLEMENTATION-NOTES.md for additional details.
