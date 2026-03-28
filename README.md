# Personal Portfolio - Apple Minimalist Style

A personal portfolio website built with Vue 3 + Vite, inspired by Apple's minimalist design philosophy. Designed for a University of Melbourne computer science student with interests in fitness, cars, and basketball.

## Features

- **Apple-inspired minimalism**: Clean layout, generous whitespace, subtle shadows, and refined typography
- **Fully responsive**: Optimized for desktop, tablet, and mobile devices
- **Component-based architecture**: Built with Vue 3 Composition API
- **Performance optimized**: Fast loading with Vite build tool
- **Accessibility**: Semantic HTML and proper contrast ratios

## Project Structure

```
├── public/              # Static assets
├── src/
│   ├── components/      # Vue components
│   │   ├── HeroSection.vue
│   │   ├── AboutSection.vue
│   │   ├── InterestsSection.vue
│   │   ├── InterestCard.vue
│   │   ├── ProjectsSection.vue
│   │   ├── ProjectCard.vue
│   │   └── FooterSection.vue
│   ├── App.vue          # Root component
│   └── main.js          # Application entry point
├── index.html           # HTML template
├── vite.config.js       # Vite configuration
└── package.json         # Dependencies and scripts
```

## Design Specifications

### Colors
- Primary background: `#FFFFFF`
- Secondary background: `#F5F5F7`
- Primary text: `#1D1D1F`
- Secondary text: `#86868B`
- Accent color: `#0066CC`
- Border: `#E8E8ED`

### Typography
- Font stack: `-apple-system, BlinkMacSystemFont, "SF Pro Text", "SF Pro Display", "Helvetica Neue", Helvetica, Arial, sans-serif`
- Title weight: 600-700
- Body weight: 400
- Line height: 1.4-1.6

### Spacing
- Section spacing: 120px (desktop), 80px (mobile)
- Card padding: 32px
- Element spacing: Multiples of 8px

### Components
- Card border radius: 18px
- Button border radius: 40px (capsule)
- Card shadow: `0 8px 20px rgba(0,0,0,0.02), 0 2px 6px rgba(0,0,0,0.05)`

## Getting Started

### Prerequisites
- Node.js 16+ and npm

### Installation
```bash
npm install
```

### Development
```bash
npm run dev
```
Runs the development server at `http://localhost:5173`

### Build for Production
```bash
npm run build
```
Generates optimized files in the `dist/` directory

### Preview Production Build
```bash
npm run preview
```
Serves the production build locally for testing

## Customization

### Personal Information
Update the following files with your personal details:

1. **HeroSection.vue**: Name, subtitle, tagline
2. **AboutSection.vue**: Personal introduction
3. **InterestsSection.vue**: Interests, descriptions, highlights
4. **ProjectsSection.vue**: Project details and GitHub links
5. **FooterSection.vue**: Contact information and social links

### Styling
Global CSS variables are defined in `src/App.vue`. Modify these variables to change colors, spacing, and other design tokens.

### Images and Icons
- Icons: Uses Font Awesome 6 via CDN
- Images: Add images to the `public/` directory and reference them with absolute paths

## Deployment

### GitHub Pages
1. Ensure `vite.config.js` has `base: '/'` (already configured)
2. Build the project: `npm run build`
3. Deploy the `dist/` folder to GitHub Pages:
   - Push to `gh-pages` branch, or
   - Configure GitHub Pages to serve from the `dist/` directory

### Custom Domain
1. Add a `CNAME` file in the `public/` directory with your domain
2. Update `vite.config.js` base path if needed
3. Follow your hosting provider's deployment instructions

## Performance

This project is optimized for performance:
- CSS variables for efficient theming
- Minimal dependencies
- Lazy loading for images (when added)
- Automated code splitting via Vite

## Browser Support

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## License

This project is open source and available for personal and educational use.

## Acknowledgments

- Design inspired by Apple's minimalist aesthetic
- Icons by Font Awesome
- Fonts by Google Fonts (Inter as fallback for SF Pro)
- Built with Vue.js and Vite