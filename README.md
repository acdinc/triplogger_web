# TripLogger Landing Page

Minimal, modern, SEO-optimized static landing page for TripLogger iOS app.

## Tech Stack

- **Pure HTML5** - Semantic markup for SEO
- **Tailwind CSS CDN** - No build tools required
- **Vanilla JavaScript** - Smooth scroll animations
- **GitHub Pages** - Free static hosting

## Project Structure

```
triplogger_web/
├── index.html          # Main landing page
├── privacy.html        # Privacy Policy (App Store requirement)
├── terms.html          # Terms of Service (App Store requirement)
├── images/             # App screenshots and assets
│   ├── app-icon.png        # 1024x1024px
│   ├── screenshot-1.png    # 1290x2796px (iPhone 15 Pro Max)
│   ├── screenshot-2.png    # 1290x2796px
│   ├── screenshot-3.png    # 1290x2796px
│   └── og-image.png        # 1200x630px (social sharing)
├── favicon.ico         # 512x512px
└── README.md          # This file
```

## Pages

### 1. index.html - Main Landing Page

**Sections:**
- **Hero Section**: Headline, CTA button, iPhone mockup
- **Features Section**: 3 key features (automatic detection, expense management, reports)
- **Screenshots Section**: 3 iPhone mockups showcasing app screens
- **How It Works**: 3-step guide (Download → Drive → Export)
- **Final CTA**: Download button with 3-day trial badge
- **Footer**: Links to privacy, terms, support

### 2. privacy.html - Privacy Policy

Required for App Store submission. Explains:
- Location data collection and usage
- Account information
- Motion and fitness data
- Data security measures
- User rights (access, delete, export)

### 3. terms.html - Terms of Service

Required for App Store submission. Covers:
- Account creation and responsibilities
- Subscription and payment terms
- Location services consent
- Disclaimer of warranties
- Tax compliance (not tax advice)

## SEO Optimization

### Meta Tags Included:
- Primary meta tags (title, description, keywords)
- Open Graph tags (Facebook sharing)
- Twitter Card tags
- Mobile optimization (viewport, theme-color)

### Structured Data:
- JSON-LD schema for MobileApplication
- Helps Google understand app details

### Keywords:
- mileage tracker
- trip logger
- tax deduction
- IRS mileage
- business expenses
- GPS tracker
- iOS app

## GitHub Pages Deployment

### Option 1: Separate Repository (Recommended)

1. **Create new repository**:
   ```bash
   # On GitHub, create new repo: triplogger-web
   ```

2. **Push files**:
   ```bash
   cd /Volumes/dev/pro/triplogger/triplogger_web
   git init
   git add .
   git commit -m "Initial commit: TripLogger landing page"
   git remote add origin https://github.com/YOUR_USERNAME/triplogger-web.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Go to repo Settings → Pages
   - Source: Deploy from branch
   - Branch: `main` → `/root`
   - Click Save

4. **Site will be live at**:
   ```
   https://YOUR_USERNAME.github.io/triplogger-web/
   ```

### Option 2: Use Existing Repo

If you want to deploy from your main `triplogger` repo:

1. **Push to existing repo**:
   ```bash
   cd /Volumes/dev/pro/triplogger
   git add triplogger_web/
   git commit -m "Add landing page"
   git push origin main
   ```

2. **Enable GitHub Pages**:
   - Go to repo Settings → Pages
   - Source: Deploy from branch
   - Branch: `main` → `/triplogger_web`
   - Click Save

3. **Site will be live at**:
   ```
   https://YOUR_USERNAME.github.io/triplogger/
   ```

## Custom Domain Setup (Optional)

If you have a domain like `triplogger.app`:

1. **Add CNAME file**:
   ```bash
   echo "triplogger.app" > CNAME
   git add CNAME
   git commit -m "Add custom domain"
   git push
   ```

2. **Configure DNS** (at your domain registrar):
   ```
   A Record:
   Name: @
   Value: 185.199.108.153
   Value: 185.199.109.153
   Value: 185.199.110.153
   Value: 185.199.111.153

   CNAME Record:
   Name: www
   Value: YOUR_USERNAME.github.io
   ```

3. **Enable HTTPS** in GitHub Pages settings (automatic after DNS propagation)

## Assets Needed

Before deploying, add these images to the `images/` folder:

### 1. App Icon (app-icon.png)
- **Size**: 1024x1024px
- **Format**: PNG
- **Export from**: Xcode asset catalog
- **Location**: `triplogger_mobile/triplogger/Assets.xcassets/AppIcon.appiconset/`

### 2. Screenshots (screenshot-1.png, screenshot-2.png, screenshot-3.png)
- **Size**: 1290x2796px (iPhone 15 Pro Max)
- **Format**: PNG
- **How to capture**:
  1. Open iOS Simulator (iPhone 15 Pro Max)
  2. Run TripLogger app
  3. Navigate to: Trip List, Trip Details, Expense Tracking
  4. Cmd+S to save screenshots
  5. Resize if needed

### 3. OG Image (og-image.png)
- **Size**: 1200x630px
- **Format**: PNG
- **Content**: App name + tagline + mockup
- **Tool**: Canva, Figma, or Photoshop

### 4. Favicon (favicon.ico)
- **Size**: 512x512px
- **Format**: ICO or PNG
- **Same as**: App icon (can be copy of app-icon.png)

## Screenshot Placeholders

Currently, the landing page shows placeholder boxes for:
- Hero iPhone mockup (right side)
- 3 screenshot mockups in Screenshots section

**To replace**:
1. Add actual screenshot images to `images/` folder
2. Update `index.html`:
   ```html
   <!-- Replace placeholder div with actual image -->
   <img src="images/screenshot-1.png" alt="TripLogger trip list" class="w-64 rounded-[2.5rem] shadow-xl">
   ```

## Testing Before Deploy

1. **Local Preview**:
   ```bash
   # Option 1: Python
   cd /Volumes/dev/pro/triplogger/triplogger_web
   python3 -m http.server 8080
   # Open http://localhost:8080

   # Option 2: Node.js (if installed)
   npx serve .
   ```

2. **Validate HTML**:
   - Go to https://validator.w3.org/
   - Upload `index.html`
   - Fix any errors

3. **Check Responsive Design**:
   - Open in browser
   - Use DevTools (Cmd+Option+I)
   - Test mobile, tablet, desktop sizes

4. **SEO Audit** (after deployment):
   - Google PageSpeed Insights: https://pagespeed.web.dev/
   - Lighthouse (Chrome DevTools)
   - Target: 90+ score

## Updating App Store Links

Before deploying, replace placeholder App Store URL:

1. **Get your App Store URL** (after app approval):
   ```
   https://apps.apple.com/app/idYOUR_APP_ID
   ```

2. **Update in all files**:
   - `index.html`: Search for `https://apps.apple.com/app/triplogger`
   - Replace with actual URL

## Post-Deployment Checklist

- [ ] All images uploaded to `images/` folder
- [ ] App Store URL updated
- [ ] Privacy policy reviewed
- [ ] Terms of service reviewed
- [ ] Custom domain configured (if applicable)
- [ ] HTTPS enabled
- [ ] Test all links (privacy, terms, support email)
- [ ] Test on mobile devices
- [ ] Submit sitemap to Google Search Console

## Analytics (Optional)

To track visitors, add Google Analytics:

1. **Create GA4 property** at https://analytics.google.com
2. **Add tracking code** to `<head>` in all HTML files:
   ```html
   <!-- Google Analytics -->
   <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
   <script>
     window.dataLayer = window.dataLayer || [];
     function gtag(){dataLayer.push(arguments);}
     gtag('js', new Date());
     gtag('config', 'G-XXXXXXXXXX');
   </script>
   ```

## Future Enhancements

Ideas for later:
- Add FAQ section
- Create blog for SEO content (mileage tax tips)
- Add user testimonials/reviews
- Embed demo video
- Multi-language support (Spanish, etc.)
- Dark mode toggle

## Support

For issues or questions:
- Email: support@triplogger.app
- GitHub Issues: Create issue in repository

## License

© 2025 TripLogger. All rights reserved.
