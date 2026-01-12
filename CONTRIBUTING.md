# Contributing to Dogstudio Clone

Thank you for your interest in contributing to this project! This document provides guidelines and information for contributors.

## 🌐 Project Links
- **Live Demo**: [https://dog-studio-flame.vercel.app](https://dog-studio-flame.vercel.app)
- **Repository**: [https://github.com/deepsandilya01/DogStudio](https://github.com/deepsandilya01/DogStudio)

## 🤝 How to Contribute

### Reporting Issues
- Use the GitHub issue tracker
- Provide detailed description of the problem
- Include steps to reproduce
- Add screenshots/videos if applicable
- Specify browser and device information

### Suggesting Features
- Open an issue with the "enhancement" label
- Describe the feature and its benefits
- Provide mockups or examples if possible

### Code Contributions

#### Prerequisites
- Node.js 18+
- Basic knowledge of React, Three.js, and GSAP
- Understanding of 3D graphics concepts

#### Development Setup
```bash
# Fork and clone the repository
git clone https://github.com/deepsandilya01/DogStudio.git
cd DogStudio

# Install dependencies
npm install

# Start development server
npm run dev
```

#### Code Style Guidelines
- Use ES6+ features
- Follow React best practices
- Use meaningful variable names
- Add comments for complex 3D logic
- Maintain consistent indentation (2 spaces)

#### 3D Asset Guidelines
- Optimize models before adding (use Draco compression)
- Keep texture sizes reasonable (max 1024x1024)
- Test performance on mobile devices
- Maintain 60fps target

#### Commit Messages
Use conventional commit format:
```
feat: add new project color mapping
fix: resolve material switching bug
docs: update README installation steps
perf: optimize shader compilation
```

#### Pull Request Process
1. Create a feature branch from `main`
2. Make your changes
3. Test thoroughly on multiple browsers
4. Update documentation if needed
5. Submit pull request with clear description

## 🧪 Testing

### Manual Testing Checklist
- [ ] 3D model loads correctly
- [ ] Animations are smooth (60fps)
- [ ] Hover effects work on all projects
- [ ] Scroll animations are synchronized
- [ ] Mobile responsiveness
- [ ] Cross-browser compatibility
- [ ] Accessibility features

### Performance Testing
```bash
# Build and analyze bundle
npm run build
# Check bundle size (should be <400KB gzipped)

# Test on slow devices
# Use Chrome DevTools throttling
```

## 📝 Documentation

### Code Documentation
- Add JSDoc comments for complex functions
- Document shader modifications
- Explain 3D transformations
- Include performance considerations

### README Updates
- Update feature list for new additions
- Add new customization options
- Update browser compatibility
- Include new troubleshooting steps

## 🎨 Design Guidelines

### Visual Consistency
- Follow original Dogstudio design language
- Maintain color palette consistency
- Use appropriate typography
- Ensure smooth transitions

### Animation Principles
- Use easing functions appropriately
- Maintain 60fps performance
- Follow 12 principles of animation
- Test on various devices

## 🚀 Release Process

### Version Numbering
- Follow semantic versioning (MAJOR.MINOR.PATCH)
- MAJOR: Breaking changes
- MINOR: New features
- PATCH: Bug fixes

### Release Checklist
- [ ] All tests pass
- [ ] Documentation updated
- [ ] Performance benchmarks met
- [ ] Cross-browser testing complete
- [ ] Mobile testing complete

## 📞 Getting Help

### Community
- GitHub Discussions for questions
- Issues for bug reports: [https://github.com/deepsandilya01/DogStudio/issues](https://github.com/deepsandilya01/DogStudio/issues)
- Pull requests for contributions

### Resources
- [Three.js Documentation](https://threejs.org/docs/)
- [React Three Fiber](https://docs.pmnd.rs/react-three-fiber)
- [GSAP Documentation](https://greensock.com/docs/)
- [Original Dogstudio](https://dogstudio.co/)

## 🏆 Recognition

Contributors will be:
- Listed in the README
- Mentioned in release notes
- Given credit in code comments

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for helping make this project better! 🎉