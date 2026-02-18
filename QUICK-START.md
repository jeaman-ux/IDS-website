# 🚀 Quick Start - Joomla Implementation

## 3 Simple Steps (15 minutes)

### ✅ Step 1: Create Article
1. Login to Joomla admin
2. Content → Articles → New
3. Title: **Sustainability and Recycling**
4. Alias: **sustainability-recycling**

### ✅ Step 2: Add HTML
1. Switch to **Code** view (click `<>` button)
2. Open file: **joomla-content.html**
3. Copy ALL content
4. Paste into article
5. Click **Save**

### ✅ Step 3: Add CSS
1. Extensions → Templates → Your Template
2. Find **Custom CSS** field
3. Open file: **assets/css/sustainability-recycling.css**
4. Copy ALL CSS
5. Paste at bottom
6. Click **Save**

---

## 📋 Files You Need

| File | Purpose | Action |
|------|---------|--------|
| `joomla-content.html` | Page content | Copy → Paste into Joomla article |
| `assets/css/sustainability-recycling.css` | Styling | Copy → Paste into template Custom CSS |
| `assets/images/hero-dumpster.png` | Hero image | Upload to Joomla Media Manager |

---

## 🎨 Quick Customization

### Change Brand Color
Open CSS file, find line ~14:
```css
--ids-green: #145a3a;  /* Change this to your color */
```

### Update Contact Link
In HTML, find and replace:
- Find: `href="/contact"`
- Replace: `href="/your-contact-page"`

### Change Image
1. Upload your image to Joomla
2. In HTML, find: `src="assets/images/hero-dumpster.png"`
3. Replace with your image path

---

## ✅ Test Checklist

After implementation, verify:
- [ ] All text displays correctly
- [ ] Buttons work and link correctly
- [ ] Page is responsive on mobile
- [ ] Colors match your brand
- [ ] No JavaScript errors (press F12 → Console)
- [ ] Smooth scroll works on internal links

---

## 🐛 Troubleshooting

**Problem:** No styling, page looks broken
- Clear Joomla cache: System → Clear Cache
- Hard refresh browser: Ctrl+F5 (Windows) or Cmd+Shift+R (Mac)

**Problem:** Images don't show
- Upload images to Joomla Media Manager
- Update image paths in HTML

**Problem:** Links don't work
- Check URL paths match your Joomla setup
- Verify `/contact` page exists

---

## 📖 Full Documentation

For detailed instructions, see:
- **JOOMLA-IMPLEMENTATION-GUIDE.md** - Complete guide
- **IMPLEMENTATION-NOTES.md** - Technical details
- **README.md** - Project overview

---

## 🎉 Done!

Your page will be live at:
**https://idswaste.com/sustainability-recycling**

Need help? Check the full implementation guide!
