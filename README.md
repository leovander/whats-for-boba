# What's for Boba - Shopify to GitHub Pages Migration

## Project Overview

This repository contains the static HTML migration of the What's for Boba landing page from Shopify (https://whatsforboba.com/) to GitHub Pages. This is a pure static site with no e-commerce functionality, API calls, or Shopify dependencies.

---

## Content Structure

### Primary Content Sections

The page contains the following main content areas:

1. **Header/Navigation**

   - Site logo: "What's for Boba?"
   - Navigation links: "home" and "about"
   - Login/Cart elements (to be removed - Shopify-specific)

2. **About Section Content**

   - **Hero Text**: "wfb?" question
   - **Introduction**: Story about the group chat origins
   - **The Mission**: Brand purpose and supporting pickleball players
   - **The Vibe**: Brand personality and tone

3. **Footer**
   - Logo image (SVG): `https://cdn.shopify.com/s/files/1/0946/6675/2278/files/Main_Logo_-_Solid_46902403-ec54-4f65-b0b6-0ad401fa4b27.svg?v=1754108097`
   - Copyright notice: "© 2026, What's for Boba?"
   - Privacy policy link
   - Payment methods section (to be removed - Shopify-specific)
   - "Powered by Shopify" attribution (to be removed)

---

## Assets to Extract

### Images

- **Main Logo SVG**: Download from Shopify CDN
  - URL: `https://cdn.shopify.com/s/files/1/0946/6675/2278/files/Main_Logo_-_Solid_46902403-ec54-4f65-b0b6-0ad401fa4b27.svg?v=1754108097`
  - Save as: `assets/images/logo.svg`
  - Used in: Footer

### Stylesheets

- Extract all CSS from the Shopify theme
- Key areas to preserve:
  - Typography (fonts, sizes, line-heights)
  - Color scheme (background colors, text colors, accent colors)
  - Layout structure (spacing, margins, padding)
  - Responsive breakpoints
  - Button styles (if any)
  - Navigation styles

### Fonts

- Identify and extract web fonts used
- Options:
  - If using Google Fonts or other CDN: Keep CDN links
  - If custom fonts: Download and host locally in `assets/fonts/`

---

## Elements to Remove

### Shopify-Specific Features

Remove all e-commerce and Shopify-specific functionality:

1. **Cart System**

   - Cart button/link
   - "Item added to your cart" modal
   - "View cart" functionality
   - "Check out" button

2. **Account System**

   - "Log in" links
   - Account URLs (`https://shopify.com/94666752278/account`)

3. **Search Functionality**

   - Search bar (unless implementing static search)

4. **Footer Elements**

   - "Payment methods" section
   - "Powered by Shopify" attribution

5. **Scripts**
   - Shopify analytics
   - Shopify checkout scripts
   - Any Shopify-specific JavaScript

---

## Technical Considerations

### File Structure

```
repository-root/
├── index.html           # Main landing page
├── assets/
│   ├── css/
│   │   └── styles.css   # Consolidated stylesheet
│   ├── images/
│   │   └── logo.svg     # Main logo
│   ├── fonts/           # Custom fonts (if any)
│   └── js/              # Minimal JavaScript (if needed)
├── README.md            # This file
└── .gitignore
```

### HTML Modifications

1. **Meta Tags**

   - Ensure proper `<title>` tag
   - Add/update meta description for SEO
   - Add viewport meta tag for responsive design
   - Add Open Graph tags for social sharing

2. **Navigation Links**

   - Convert `/about` to `#about` (single-page design) or remove
   - Update home link to `#` or `/`

3. **Skip Links**
   - Keep `#MainContent` skip link for accessibility

### CSS Considerations

1. **Extract Inline Styles**: Convert any inline styles to external CSS
2. **Remove Shopify Classes**: Clean up Shopify-specific class names if desired
3. **Responsive Design**: Ensure mobile-first approach is preserved
4. **Critical CSS**: Consider inlining critical above-the-fold CSS

### JavaScript

- Evaluate if any JavaScript is needed
- If navigation smoothing is desired, add minimal vanilla JS
- Remove all Shopify tracking and analytics scripts

---

## GitHub Pages Configuration

### Repository Settings

1. **Repository Name Options**:

   - `whatsforboba.github.io` (user/org site - will be at root)
   - `wfb-landing` (project site - will be at `/wfb-landing`)

2. **Branch Configuration**:

   - Deploy from `main` branch
   - Deploy from root `/` directory (not `/docs`)

3. **Custom Domain** (if applicable):
   - Add `CNAME` file with domain name
   - Configure DNS settings at domain registrar

### Performance Optimization

1. **Image Optimization**

   - SVG: Minify and clean up unnecessary metadata
   - Ensure all images are web-optimized

2. **Minification**

   - Minify CSS for production
   - Minify JavaScript (if any)

3. **Caching**
   - GitHub Pages handles basic caching
   - Use cache-busting for major updates (version query strings)

---

## Content to Preserve Exactly

The following text content should be migrated verbatim:

### Intro Paragraph

> It started like all great entrepreneurial ventures do – in a group chat filled with bad jokes and even worse financial decisions.

### "wfb?" Section

> **"wfb?"**
>
> Three little letters that haunt our phones daily. **What's for Boba?** The question that simultaneously brings us together and slowly drains our bank accounts, one $7 drink at a time.
>
> We're a tight-knit crew of friends & colleagues who've somehow made boba tea our entire personality. Are we aware that we're basically drinking liquid candy? Absolutely. Do we care? Not even a little bit. Our parents immigrated here for the American Dream, and apparently, our version of that dream involves consuming alarming amounts of tapioca pearls.

### The Mission Section

> **the mission**
>
> What started as an inside joke has evolved into something bigger. We come from different backgrounds, but we all understand the hustle, the community, and the inexplicable need to document every boba run on social media.
>
> This brand exists to celebrate our obsession while supporting our friends who are chasing their dreams on the pickleball court. Every shirt you buy helps fund their tournament gear, because apparently, we've collectively decided that supporting questionable hobbies is our love language.

### The Vibe Section

> **the vibe**
>
> We're not trying to be the next big fashion brand. We just thought, "What if we could turn our daily question into wearable art?" Every piece is designed with the same energy as our group chat – a little chaotic, surprisingly thoughtful, and definitely not taking itself too seriously.
>
> So whether you're part of the _WFB_ cult or just someone who appreciates random comfy merch with a side of existential boba humor, welcome to the family.
>
> _Now, what's for boba?_

---

## Testing Checklist

Before deploying to GitHub Pages, verify:

- [ ] All images load correctly from local assets
- [ ] Typography matches original design
- [ ] Color scheme matches original
- [ ] Layout is responsive (mobile, tablet, desktop)
- [ ] All Shopify-specific elements removed
- [ ] Links work correctly (or are removed)
- [ ] Logo displays properly
- [ ] Footer content is accurate
- [ ] Page loads quickly
- [ ] HTML validates (W3C validator)
- [ ] CSS validates
- [ ] Accessibility check (WAVE or similar tool)

---

## Deployment Steps

1. **Prepare Repository**

   - Create new GitHub repository
   - Clone locally
   - Add all static files

2. **Configure GitHub Pages**

   - Go to repository Settings > Pages
   - Select `main` branch
   - Select root `/` folder
   - Save

3. **Verify Deployment**

   - Wait 1-2 minutes for build
   - Visit `https://[username].github.io/[repo-name]`
   - Test all functionality

4. **Custom Domain** (optional)
   - Add `CNAME` file with domain
   - Configure DNS at registrar
   - Enable HTTPS in GitHub Pages settings

---

## Maintenance Notes

- **Content Updates**: Edit `index.html` directly
- **Style Updates**: Modify `assets/css/styles.css`
- **Deployment**: Push to `main` branch for automatic deployment
- **Privacy Policy**: Update link or create static privacy page if needed

---

## Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [W3C HTML Validator](https://validator.w3.org/)
- [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)
- [WAVE Accessibility Tool](https://wave.webaim.org/)

---

## License

Specify your license here (if applicable)
