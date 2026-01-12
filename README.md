# 🐕 Dogstudio Clone - React Three.js Experience

A pixel-perfect recreation of the award-winning [Dogstudio](https://dogstudio.co/) website, built with React, Three.js, and GSAP. This project showcases advanced 3D web development techniques, smooth animations, and professional UI/UX design.

## 🌐 Live Demo
**[View Live Site →](https://dog-studio-flame.vercel.app)**

![Dogstudio Clone Preview](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)
![React](https://img.shields.io/badge/React-19.2.0-blue)
![Three.js](https://img.shields.io/badge/Three.js-0.182.0-orange)
![GSAP](https://img.shields.io/badge/GSAP-3.14.2-green)

## ✨ Features

### 🎨 **Visual Excellence**
- **3D Dog Model** with realistic animations and materials
- **Dynamic Material System** with 7 unique matcap textures
- **Scroll-triggered Animations** using GSAP ScrollTrigger
- **Interactive Hover Effects** with smooth color transitions
- **Professional Loading Screen** with progress indicators

### 🚀 **Performance Optimized**
- **Draco Compressed Models** for fast loading (390KB gzipped)
- **Texture Optimization** with proper color space management
- **Shader Caching** for improved rendering performance
- **Lazy Loading** with React Suspense
- **Mobile Responsive** design with optimized animations

### 🎯 **User Experience**
- **Smooth Scroll Animations** synchronized with 3D transformations
- **Audio Ambience** with user interaction unlock
- **Cross-browser Compatibility** with fallback support
- **Accessibility Features** (reduced motion, high contrast)
- **Error Boundaries** for graceful error handling

## �️ Tech S tack

| Technology | Version | Purpose |
|------------|---------|---------|
| **React** | 19.2.0 | UI Framework |
| **Three.js** | 0.182.0 | 3D Graphics |
| **React Three Fiber** | 9.5.0 | React Three.js Renderer |
| **React Three Drei** | 10.7.7 | Three.js Utilities |
| **GSAP** | 3.14.2 | Animations |
| **Vite** | 7.2.4 | Build Tool |

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ 
- npm or yarn

### Installation

```bash
# Clone the repository
git clone https://github.com/deepsandilya01/DogStudio.git
cd DogStudio

# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

### Development Server
```bash
npm run dev
# Opens http://localhost:5173
```

## 📁 Project Structure

```
src/
├── components/
│   ├── Dog.jsx              # Main 3D dog component
│   ├── Loader.jsx           # Loading screen component
│   ├── Loader.css           # Loader styles
│   └── ErrorBoundary.jsx    # Error handling
├── App.jsx                  # Main application
├── App.css                  # Global styles
└── main.jsx                 # React entry point

public/
├── models/
│   └── dog.drc.glb         # 3D dog model (Draco compressed)
├── matcap/                 # Material capture textures
│   ├── mat-2.png           # Default blue-gray
│   ├── mat-8.png           # Navy blue
│   ├── mat-9.png           # Purple
│   └── ...                 # Additional matcaps
├── textures/
│   └── dog_normals.jpg     # Normal map for dog
└── images/                 # Project portfolio images
```

## 🎮 Interactive Features

### 3D Model Interactions
- **Scroll Animation**: Dog rotates and moves based on scroll position
- **Material Switching**: Hover over project titles to change dog colors
- **Breathing Animation**: Subtle idle animations for realism

### Project Color Mappings
| Project | Color | Matcap |
|---------|-------|--------|
| Tomorrowland | Pink/Magenta | mat-19 |
| Navy Pier | Navy Blue | mat-8 |
| MSI Chicago | Purple | mat-9 |
| Louise's Phone | Bright Blue | mat-12 |
| KIKK Festival | Dark Metallic | mat-10 |
| Kennedy Center | Warm Brown | mat-13 |
| Royal Opera | Pink | mat-19 |

## 🎨 Customization

### Adding New Projects
1. Add project image to `public/images/`
2. Update `App.jsx` with new project data
3. Add color mapping in `Dog.jsx`

```javascript
// In Dog.jsx
const projectMaterials = {
  "your-project": matX,  // Add your matcap
};
```

### Changing Materials
Replace matcap textures in `public/matcap/` directory. Supported formats: PNG, JPG.

### Modifying Animations
Edit GSAP timelines in `Dog.jsx`:

```javascript
// Scroll animation
useGSAP(() => {
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: "#section-1",
      endTrigger: "#section-4",
      scrub: 1.5, // Adjust scroll sensitivity
    },
  });
  // Add your animations
});
```

## 📱 Browser Support

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 90+ | ✅ Full Support |
| Firefox | 88+ | ✅ Full Support |
| Safari | 14+ | ✅ Full Support |
| Edge | 90+ | ✅ Full Support |

### Fallback Features
- CSS `:has()` selector fallback for older browsers
- WebGL detection with graceful degradation
- Reduced motion support for accessibility

## ⚡ Performance

### Bundle Analysis
- **Total Size**: 1.33MB (391KB gzipped)
- **3D Assets**: Draco compressed for 60% size reduction
- **Textures**: Optimized with proper compression
- **Code Splitting**: Ready for implementation

### Optimization Tips
```bash
# Analyze bundle size
npm run build -- --analyze

# Enable gzip compression on server
# Add to your server config:
# gzip_types text/css application/javascript application/json
```

## 🐛 Troubleshooting

### Common Issues

**3D Model Not Loading**
```bash
# Check if model exists
ls public/models/dog.drc.glb

# Verify MIME type in server config
# .glb files should serve as application/octet-stream
```

**Animations Not Working**
```javascript
// Ensure GSAP plugins are registered
gsap.registerPlugin(ScrollTrigger);
```

**Build Errors**
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

### Development Guidelines
- Follow React best practices
- Optimize 3D assets before adding
- Test on multiple browsers
- Maintain 60fps performance

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Original Design**: [Dogstudio](https://dogstudio.co/) - Award-winning creative studio
- **3D Libraries**: Three.js community for excellent documentation
- **Animation**: GSAP for powerful animation tools
- **React Ecosystem**: React Three Fiber and Drei contributors

## 📞 Contact

**Deep Sandilya**
- GitHub: [@deepsandilya01](https://github.com/deepsandilya01)
- LinkedIn: [deepsandilya01](https://www.linkedin.com/in/deepsandilya01)
- Instagram: [@deepsandilya_01](https://www.instagram.com/deepsandilya_01)

---

<div align="center">
  <p>Built with ❤️ using React, Three.js, and GSAP</p>
  <p>© 2026 Deep Sandilya | Inspired by Dogstudio</p>
  <p><strong><a href="https://dog-studio-flame.vercel.app">🌐 View Live Demo</a></strong></p>
</div>