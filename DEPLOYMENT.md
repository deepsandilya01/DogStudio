# 🚀 Deployment Guide

This guide covers various deployment options for the Dogstudio Clone project.

## 🌐 Live Demo
**Current deployment**: [https://dog-studio-flame.vercel.app](https://dog-studio-flame.vercel.app)

## 📋 Pre-deployment Checklist

- [ ] All assets are optimized
- [ ] Build completes without errors
- [ ] Performance targets met (391KB gzipped)
- [ ] Cross-browser testing complete
- [ ] Mobile responsiveness verified

## 🌐 Deployment Platforms

### Vercel (Recommended)
Perfect for React applications with automatic deployments.

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel

# Production deployment
vercel --prod
```

**Vercel Configuration** (`vercel.json`):
```json
{
  "buildCommand": "npm run build",
  "outputDirectory": "dist",
  "framework": "vite",
  "rewrites": [
    {
      "source": "/(.*)",
      "destination": "/index.html"
    }
  ]
}
```

### Netlify
Great for static sites with form handling.

```bash
# Install Netlify CLI
npm install -g netlify-cli

# Build and deploy
npm run build
netlify deploy --prod --dir=dist
```

**Netlify Configuration** (`netlify.toml`):
```toml
[build]
  command = "npm run build"
  publish = "dist"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

### GitHub Pages
Free hosting for public repositories.

```bash
# Install gh-pages
npm install --save-dev gh-pages

# Add to package.json scripts
"deploy": "gh-pages -d dist"

# Deploy
npm run build
npm run deploy
```

### Firebase Hosting
Google's hosting platform with CDN.

```bash
# Install Firebase CLI
npm install -g firebase-tools

# Initialize
firebase init hosting

# Deploy
npm run build
firebase deploy
```

## ⚙️ Server Configuration

### MIME Types
Ensure your server serves these MIME types correctly:

```nginx
# Nginx configuration
location ~* \.(glb|gltf)$ {
    add_header Content-Type application/octet-stream;
}

location ~* \.(jpg|jpeg|png|webp)$ {
    add_header Content-Type image/jpeg;
    expires 1y;
    add_header Cache-Control "public, immutable";
}
```

### Compression
Enable gzip compression for better performance:

```nginx
# Nginx gzip configuration
gzip on;
gzip_types
    text/css
    text/javascript
    application/javascript
    application/json
    image/svg+xml;
```

### Headers
Add security and performance headers:

```nginx
# Security headers
add_header X-Frame-Options "SAMEORIGIN";
add_header X-Content-Type-Options "nosniff";
add_header X-XSS-Protection "1; mode=block";

# Performance headers
add_header Cache-Control "public, max-age=31536000" always;
```

## 🔧 Environment Variables

Create `.env` files for different environments:

**.env.production**:
```env
VITE_API_URL=https://api.yoursite.com
VITE_ANALYTICS_ID=your-analytics-id
```

**.env.development**:
```env
VITE_API_URL=http://localhost:3001
VITE_DEBUG=true
```

## 📊 Performance Optimization

### Bundle Analysis
```bash
# Analyze bundle size
npm run build -- --analyze

# Use webpack-bundle-analyzer
npx webpack-bundle-analyzer dist/assets/*.js
```

### Asset Optimization
```bash
# Optimize images
npm install -g imagemin-cli
imagemin public/images/* --out-dir=public/images/optimized

# Compress 3D models
# Use Draco compression in Blender or online tools
```

### CDN Setup
Upload static assets to CDN:

```javascript
// Update asset paths in production
const assetPath = process.env.NODE_ENV === 'production' 
  ? 'https://cdn.yoursite.com/assets/'
  : '/';
```

## 🔍 Monitoring

### Performance Monitoring
```javascript
// Add to main.jsx
if (process.env.NODE_ENV === 'production') {
  // Web Vitals
  import('web-vitals').then(({ getCLS, getFID, getFCP, getLCP, getTTFB }) => {
    getCLS(console.log);
    getFID(console.log);
    getFCP(console.log);
    getLCP(console.log);
    getTTFB(console.log);
  });
}
```

### Error Tracking
```javascript
// Add error boundary with reporting
window.addEventListener('error', (event) => {
  // Send to error tracking service
  console.error('Global error:', event.error);
});
```

## 🚨 Troubleshooting

### Common Deployment Issues

**Assets Not Loading**
```bash
# Check asset paths
# Ensure assets are in public/ directory
# Verify MIME types on server
```

**3D Model Not Rendering**
```bash
# Check WebGL support
# Verify model file integrity
# Test on different devices
```

**Performance Issues**
```bash
# Enable compression
# Optimize textures
# Use CDN for assets
# Implement lazy loading
```

### Health Checks
Create a health check endpoint:

```javascript
// Add to your server
app.get('/health', (req, res) => {
  res.json({
    status: 'healthy',
    timestamp: new Date().toISOString(),
    version: process.env.npm_package_version
  });
});
```

## 📈 Analytics

### Google Analytics 4
```javascript
// Add to index.html
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### Custom Events
```javascript
// Track 3D interactions
const trackInteraction = (action, element) => {
  gtag('event', action, {
    event_category: '3D_Interaction',
    event_label: element
  });
};
```

## 🔄 CI/CD Pipeline

### GitHub Actions
Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to Production

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v3
    
    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'
        cache: 'npm'
    
    - name: Install dependencies
      run: npm ci
    
    - name: Build
      run: npm run build
    
    - name: Deploy to Vercel
      uses: amondnet/vercel-action@v20
      with:
        vercel-token: ${{ secrets.VERCEL_TOKEN }}
        vercel-org-id: ${{ secrets.ORG_ID }}
        vercel-project-id: ${{ secrets.PROJECT_ID }}
        vercel-args: '--prod'
```

---

## 🎉 Go Live!

Your Dogstudio clone is now ready for production! 🚀

**Live Example**: [https://dog-studio-flame.vercel.app](https://dog-studio-flame.vercel.app)

For support, create an issue on [GitHub](https://github.com/deepsandilya01/DogStudio/issues) or contact the maintainers.