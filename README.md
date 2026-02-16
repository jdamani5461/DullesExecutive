# Dulles Executive Care Staffing - Website Documentation

## Project Overview
Premium ID/DD staffing website for Northern Virginia group homes. DBHDS-compliant, bilingual (EN/FR), healthcare-focused design.

## Technology Stack
- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Design System**: Custom CSS variables, mobile-first responsive
- **Typography**: Inter (body), Poppins (headings)
- **Images**: Unsplash placeholders (replace with professional photography)

## File Structure
```
dulles-executive-website/
├── index.html              # Homepage
├── services.html           # Services page (DSP, Med Tech, Managers)
├── for-group-homes.html    # For Group Homes (to be created)
├── process.html            # Process page (to be created)
├── about.html              # About page (to be created)
├── careers.html            # Careers page with application form
├── contact.html            # Contact page with multiple forms
├── compliance.html         # Compliance page (to be created)
├── blog.html               # Blog listing (to be created)
├── assets/
│   ├── css/
│   │   └── main.css        # Complete design system & components
│   ├── js/
│   │   └── main.js         # Interactive functionality
│   └── images/
│       └── (add logos, photos, badges)
├── template-parts/         # Reusable components (for WordPress)
└── README.md              # This file
```

## Pages Completed
✅ **Homepage (index.html)** - Hero, value props, services preview, testimonials, process, CTA
✅ **Services (services.html)** - Detailed service descriptions with imagery
✅ **Careers (careers.html)** - Job listings, benefits, application form
✅ **Contact (contact.html)** - Multiple contact methods, staff request form

## Pages To Create
⏳ For Group Homes page
⏳ Process page
⏳ About page
⏳ Compliance page
⏳ Blog pages

## Design System

### Color Palette
- Primary Blue: `#0A4C7A` (Trust, healthcare)
- Primary Teal: `#008B8B` (Calm, professionalism)
- Accent Gold: `#D4AF37` (Premium, excellence)
- Success Green: `#10B981` (Compliance badges)
- Warning Orange: `#F59E0B` (Emergency/urgent)

### Typography
- **Headings**: Poppins (600, 700)
- **Body**: Inter (400, 500, 600, 700)
- **Fluid sizing**: clamp() for responsive typography

### Spacing Scale
Based on 8px grid: 8px, 16px, 24px, 32px, 40px, 48px, 64px, 80px, 96px

## Key Features

### Responsive Design
- Mobile-first approach
- Breakpoints: 640px, 768px, 1024px, 1280px
- Touch-friendly buttons and forms
- Hamburger menu for mobile

### Accessibility
- Semantic HTML5
- ARIA labels on interactive elements
- Keyboard navigation support
- Color contrast ratios meet WCAG 2.1 AA

### Forms
1. **Staff Request Form** (Contact page)
   - Facility details, position type, urgency level
   - Auto-response within 2 hours
   
2. **Consultation Form** (Homepage)
   - Quick facility inquiry
   
3. **General Inquiry Form** (Contact page)
   - Generic contact form
   
4. **Application Form** (Careers page)
   - Job application with resume upload
   - Certification checkboxes
   - Background check consent

### SEO Optimization
- Semantic HTML structure
- Meta descriptions on all pages
- H1-H6 hierarchy maintained
- Schema.org markup ready (add JSON-LD)
- Descriptive alt text for images

## Setup Instructions

### 1. Local Development
```bash
# Clone or download the files
cd dulles-executive-website

# Open in browser
open index.html
# Or use a local server (recommended)
python3 -m http.server 8000
# Then visit: http://localhost:8000
```

### 2. Replace Placeholder Content
- **Images**: Replace Unsplash URLs with professional photos
  - Hero image: Professional caregiver with resident
  - Service images: DSP, Med Tech, Manager in action
  - Blog images: Industry-related photography
  
- **Logo**: Replace SVG text with actual logo
  - Main logo: `assets/images/logo.svg`
  - Footer logo: `assets/images/logo-white.svg`
  
- **Contact Information**: Update all instances of:
  - Phone: (703) 555-1234 → Real number
  - Email: info@dullesexecutivecare.com → Real email
  - Address: 123 Main Street, Fairfax, VA 22030 → Real address

### 3. Form Integration
Forms currently use `action="#"` placeholders. Integrate with:
- **Option 1**: Backend API (recommended)
  - Create REST endpoints for each form
  - Add AJAX submission with JavaScript
  
- **Option 2**: Third-party service
  - FormSpree, Basin, or similar
  - Update form action URLs
  
- **Option 3**: Email gateway
  - PHPMailer or similar
  - Configure SMTP settings

### 4. Google Maps Integration
Replace map placeholder in `contact.html`:
```html
<iframe 
  src="https://www.google.com/maps/embed?pb=YOUR_EMBED_CODE"
  width="100%" 
  height="400" 
  style="border:0;" 
  allowfullscreen="" 
  loading="lazy">
</iframe>
```

### 5. Analytics & Tracking
Add to `<head>` before `</head>`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## WordPress Migration (Optional)

### Theme Files Needed
1. `style.css` - Theme header with metadata
2. `functions.php` - Enqueue assets, register menus
3. `header.php` - Site header
4. `footer.php` - Site footer
5. `front-page.php` - Homepage template
6. `page-services.php` - Services template
7. `page-careers.php` - Careers template
8. `page-contact.php` - Contact template
9. Template parts in `/template-parts/`

### Recommended Plugins
- Yoast SEO or Rank Math
- Contact Form 7 or WPForms
- WPML or Polylang (bilingual EN/FR)
- WP Rocket (performance)
- Wordfence Security

## Bilingual (EN/FR) Implementation

### Static Method (Current)
Create duplicate pages:
- `index.html` → `index-fr.html`
- Update language toggle links
- Translate all content

### Dynamic Method (Recommended for WordPress)
- Install WPML or Polylang
- Add translation strings to theme
- Use language switcher widget

## Performance Optimization

### Images
- Compress all images (TinyPNG, ImageOptim)
- Use WebP format with JPG fallback
- Implement lazy loading: `loading="lazy"`
- Max width: 1920px for hero images

### CSS/JS
- Minify CSS and JS for production
- Combine files where possible
- Use CDN for fonts (already implemented)

### Caching
- Set browser cache headers
- Enable gzip compression
- Use CDN for static assets (optional)

## Browser Support
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile iOS Safari 14+
- Mobile Chrome 90+

## Maintenance Checklist

### Weekly
- [ ] Test all forms
- [ ] Check for broken links
- [ ] Monitor site uptime
- [ ] Review form submissions

### Monthly
- [ ] Update testimonials
- [ ] Refresh blog content
- [ ] Check analytics
- [ ] Test mobile responsiveness
- [ ] Update job postings

### Quarterly
- [ ] Review and update copy
- [ ] Refresh images
- [ ] SEO audit
- [ ] Speed test (GTmetrix, PageSpeed Insights)
- [ ] Security scan

## Contact & Support
For technical support or questions about this website:
- Developer: Intellia Web Architect
- Documentation: This README file
- Issue tracking: [Add your system]

## License
© 2026 Dulles Executive Care Staffing. All rights reserved.

---

**Last Updated**: February 12, 2026
**Version**: 1.0.0
**Status**: Production-Ready (pending content finalization)
