# Gigabyte Alchemy Website

## Project Overview
This is the official website for Gigabyte Alchemy (gigabytealchemy.ai), a company focused on edge AI applications and tooling. The website is built with Astro and uses Tailwind CSS v4 for styling.

## Tech Stack
- **Framework**: Astro (v5.13.8)
- **Styling**: Tailwind CSS v4 (using @tailwindcss/vite)
- **Build Tool**: Vite (integrated with Astro)
- **Language**: JavaScript/TypeScript

## Project Structure
```
ga-website/
├── src/
│   ├── pages/
│   │   └── index.astro      # Main landing page
│   ├── content/
│   │   └── site.json        # Site content configuration
│   └── styles/
│       └── global.css       # Global styles (imports Tailwind)
├── public/
│   └── images/              # Static images
├── astro.config.mjs         # Astro configuration
└── package.json             # Dependencies
```

## Key Features

### Content Management
The site uses a JSON-based content management system (`src/content/site.json`) that contains:
- Brand name and contact information
- Hero section content (headlines, tagline, background image)
- Capabilities/services list
- Mission statement
- Contact endpoint and email

### Page Sections
The main landing page (`index.astro`) includes:
1. **Header**: Sticky navigation with brand name
2. **Hero Section**: Dynamic background image with gradient overlay, headlines pulled from JSON
3. **Capabilities**: Grid layout showcasing services (Edge app prototyping, Quantization & deploy, Docs & developer UX)
4. **Mission Statement**: Company mission in a styled card
5. **Contact Form**: Integration with external API endpoint and Cloudflare Turnstile for spam protection

### Security Features
- Cloudflare Turnstile integration for form protection (requires `PUBLIC_TURNSTILE_SITE_KEY` environment variable)
- Contact form posts to external API endpoint: `https://api.gigabytefoundry.ai/contact`

## Development Commands

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Environment Variables
- `PUBLIC_TURNSTILE_SITE_KEY`: Cloudflare Turnstile site key for contact form protection

## Content Updates
To update site content, modify `src/content/site.json`. The following can be changed without touching code:
- Company branding
- Hero section text and background image
- Capabilities/services descriptions
- Mission statement
- Contact email and API endpoint

## Styling
The site uses Tailwind CSS v4 with Vite integration. Global styles are imported in `src/styles/global.css`. The design features:
- Clean, modern aesthetic with subtle gradients
- Responsive grid layouts
- Hover effects on interactive elements
- Sticky header with backdrop blur
- Gradient text effects for emphasis

## Deployment Notes
- Static assets should be placed in the `public/` directory
- The hero background image is currently at `/images/alchemie-labor-antik-fantasie.jpg`
- The site appears to be configured for deployment on a domain ending in `.ai`

## Contact Integration
The contact form submits to an external API endpoint. Ensure the endpoint at `https://api.gigabytefoundry.ai/contact` is configured to handle POST requests with form data.

## Future Considerations
- Blog functionality (mentioned in initial requirements but not yet implemented)
- Additional pages beyond the landing page
- SEO optimizations (meta tags, Open Graph, etc.)
- Analytics integration
- Performance optimizations (image optimization, lazy loading)