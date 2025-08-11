# Ishan Vohra - Portfolio

A modern, responsive portfolio website built with Svelte and SvelteKit, showcasing my work as a Software Engineer and Mobile Developer.

## 🚀 Features

- **Modern Design**: Clean, professional design with smooth animations
- **Responsive**: Fully responsive layout that works on all devices
- **Fast**: Built with Svelte for optimal performance
- **SEO Optimized**: Proper meta tags and structured data
- **Accessible**: WCAG compliant design
- **Dark Mode Ready**: CSS variables for easy theming

## 🛠️ Tech Stack

- **Framework**: Svelte 4 + SvelteKit
- **Language**: JavaScript
- **Styling**: CSS with custom properties
- **Icons**: Lucide Svelte
- **Deployment**: GitHub Pages
- **Build Tool**: Vite

## 📋 Sections

- **Hero**: Introduction and call-to-action
- **About**: Background and education
- **Experience**: Work history with timeline
- **Projects**: Featured projects with technologies
- **Skills**: Technical skills organized by category
- **Awards**: Recognition and achievements
- **Contact**: Contact information and social links

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ 
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone https://github.com/ishanvohra2/ishanvohra2.github.io.git
cd ishanvohra2.github.io
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and navigate to `http://localhost:5173`

### Building for Production

```bash
npm run build
```

The built files will be in the `build/` directory.

## 🚀 Deployment

This portfolio is automatically deployed to GitHub Pages using GitHub Actions.

### Manual Deployment

1. Build the project:
```bash
npm run build
```

2. The `build/` directory contains the static files ready for deployment.

### GitHub Pages Setup

1. Go to your repository settings
2. Navigate to "Pages" section
3. Select "GitHub Actions" as the source
4. The workflow will automatically deploy on push to main branch

## 📝 Customization

### Personal Information

Update the profile data in `src/routes/+page.svelte`:

```javascript
const profile = {
    name: "Your Name",
    title: "Your Title",
    email: "your.email@example.com",
    location: "Your Location",
    website: "your-website.com",
    description: "Your description"
};
```

### Styling

The design uses CSS custom properties for easy theming. Update the variables in `src/app.css`:

```css
:root {
    --primary-color: #3b82f6;
    --secondary-color: #1e40af;
    --accent-color: #06b6d4;
    /* ... other variables */
}
```

### Content

- **Experience**: Update the `experience` array
- **Projects**: Modify the `projects` array
- **Skills**: Edit the `skills` array
- **Education**: Update the `education` array
- **Awards**: Modify the `awards` array

## 📱 Responsive Design

The portfolio is fully responsive with breakpoints at:
- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px

## 🔧 Development

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Lint code
- `npm run format` - Format code

### Project Structure

```
src/
├── app.css          # Global styles
├── app.html         # HTML template
└── routes/
    ├── +layout.svelte   # Layout component
    ├── +layout.js       # Layout configuration
    └── +page.svelte     # Main page component
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 📞 Contact

- **Email**: ishanvohra2@gmail.com
- **Website**: ishanvohra2.github.io
- **Location**: Delhi, India

---

Built with ❤️ using Svelte
