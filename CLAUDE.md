# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static HTML documentation site for Android applications. The repository contains privacy policy pages for three apps:

- **Root**: `index.html` - xFlange privacy policy
- **CapacitySuite**: `CapacitySuite/index.html` - Capacity Suite privacy policy
- **FittingsSuite**: `FittingsSuite/index.html` - Fittings Suite privacy policy

All files are self-contained HTML documents with embedded CSS. The site is hosted on GitHub Pages at `https://canitbeing.github.io/privacy/`.

## Key Architecture

Each HTML file follows a consistent structure:

1. **Head section**: Meta tags for SEO, Open Graph, Twitter Cards, responsive viewport, and theme configuration
2. **Inline styles**: All CSS is embedded in `<style>` tags (no external stylesheets)
3. **Semantic HTML**: Sections use `<section>` elements with consistent CSS classes
4. **Responsive design**: Mobile-first approach with media queries for screens ≤768px
5. **No JavaScript**: Static content with no interactive features or external scripts

### CSS Classes Used

- `.container` - Main content wrapper (max-width: 900px)
- `.section` - Wrapper for each policy section
- `.section-title` - Numbered headings (e.g., "1. OVERVIEW")
- `.content-box` - Bordered container for section content
- `.content-text` - Paragraph text
- `.list-item` - Bulleted list items with left margin
- `.bold-text` - Emphasized text (font-weight: 600)
- `.last-updated` - Footer timestamp text
- `.page-title`, `.subtitle` - Header styling
- `header`, `footer` - Semantic containers for page header/footer

## Styling Guidelines

- **Typography**: Uses 'Outfit' font from Google Fonts with fallbacks
- **Colors**: Minimalist approach - black text (#000000) on white background (#ffffff)
- **Links**: Bright blue (#1E90FF) with underline on hover
- **Spacing**: Uses rem-based units (16px base) for consistent sizing
- **Responsive**: Breaks at 768px with adjusted font sizes and padding

## Common Development Tasks

### Updating Privacy Policy Content

Edit the appropriate `index.html` file and modify the `<section>` elements containing policy content. Maintain the consistent structure:

```html
<section class="section">
    <h2 class="section-title">SECTION_NUMBER. SECTION_TITLE</h2>
    <div class="content-box">
        <p class="content-text">Content here...</p>
        <p class="list-item">• Bullet point</p>
    </div>
</section>
```

### Updating Metadata

- **Canonical URL**: Update `<link rel="canonical" href="...">` if domain changes
- **Author/Developer**: Update author meta tag and footer copyright
- **SEO Description**: Modify `<meta name="description">` and og:description
- **Social Media Tags**: Update Open Graph and Twitter Card meta tags

### Testing Changes

Since there are no build tools or tests:

1. Open the HTML file in a browser to visually verify changes
2. Test responsive design by resizing browser window or using mobile device
3. Verify all links work correctly
4. Check consistency with other policy pages (CapacitySuite and FittingsSuite)

## Git Workflow

Current branch: `main` - This is both the development and production branch (pages are deployed directly from here).

Recent commit patterns show simple descriptive messages like "Update footer copyright text" and "capacity suite add".

## File Consistency

The CapacitySuite and FittingsSuite files are nearly identical to the root `index.html` (550 lines each, identical structure). When making updates to policies:

1. Update the relevant section(s) in the appropriate file
2. Ensure other files maintain consistency if the change applies to all apps
3. Update timestamps in the "EFFECTIVE DATE" section (Section 16) when policy content changes

## Dependencies

- No external dependencies or build tools
- No package.json or build configuration
- Google Fonts (Outfit) loaded from CDN for typography
- Static hosting only (no server-side processing)

## Notes for Working on This Repository

- All changes are immediately visible in Git diff
- Privacy policy content directly affects app store compliance (GDPR, CCPA, COPPA, Google Play Families Policy)
- Pay close attention to accuracy when discussing data collection, third-party services, and user rights
- The "Last Updated" timestamp should be kept current when content changes
