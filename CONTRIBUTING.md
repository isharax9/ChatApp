# Contributing to ChatApp

Thank you for your interest in contributing to ChatApp! This document provides detailed guidelines for contributing to the project.

## 🚀 Quick Start

1. Fork the repository
2. Clone your fork: `git clone https://github.com/yourusername/ChatApp.git`
3. Create a feature branch: `git checkout -b feature/your-feature-name`
4. Make your changes
5. Test thoroughly
6. Commit your changes: `git commit -m "feat: add new feature"`
7. Push to your fork: `git push origin feature/your-feature-name`
8. Create a Pull Request

## 📋 Development Setup

### Prerequisites
- Node.js 18+
- Yarn package manager
- Expo CLI
- MongoDB Atlas account
- Git

### Local Setup
```bash
# Clone the repository
git clone https://github.com/isharax9/ChatApp.git
cd ChatApp

# Install frontend dependencies
yarn install

# Install backend dependencies
cd api
yarn install

# Set up environment variables
cp .env.example .env
# Edit .env with your MongoDB connection string

# Start backend server
yarn start

# In another terminal, start frontend
cd ..
npx expo start
```

## 🔧 Code Standards

### JavaScript/React Native
- Use ESLint rules (if configured)
- Follow React best practices
- Use functional components with hooks
- Implement proper error handling
- Add meaningful comments for complex logic

### File Naming Conventions
- Components: PascalCase (e.g., `UserProfile.js`)
- Utilities: camelCase (e.g., `apiHelpers.js`)
- Constants: UPPER_SNAKE_CASE (e.g., `API_ENDPOINTS.js`)

### Git Commit Messages
Use conventional commit format:
- `feat:` - New features
- `fix:` - Bug fixes
- `docs:` - Documentation changes
- `style:` - Code style changes (formatting, etc.)
- `refactor:` - Code refactoring
- `test:` - Adding or updating tests
- `chore:` - Maintenance tasks

Examples:
```
feat: add message reaction functionality
fix: resolve login authentication issue
docs: update API documentation
style: format code according to prettier rules
```

## 🐛 Bug Reports

When reporting bugs, please include:

### Required Information
- **Bug Description**: Clear and concise description
- **Steps to Reproduce**: Numbered steps to reproduce the issue
- **Expected Behavior**: What you expected to happen
- **Actual Behavior**: What actually happened
- **Screenshots**: If applicable
- **Environment**: Device, OS, app version, Node version

### Bug Report Template
```markdown
**Bug Description**
A clear and concise description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior:
1. Go to '...'
2. Click on '....'
3. Scroll down to '....'
4. See error

**Expected behavior**
A clear and concise description of what you expected to happen.

**Screenshots**
If applicable, add screenshots to help explain your problem.

**Environment (please complete the following information):**
- Device: [e.g. iPhone 12, Samsung Galaxy S21]
- OS: [e.g. iOS 15.0, Android 11]
- App Version: [e.g. 1.0.0]
- Node Version: [e.g. 18.0.0]

**Additional context**
Add any other context about the problem here.
```

## 💡 Feature Requests

### Before Requesting
- Check if the feature already exists
- Search existing issues and PRs
- Consider if it fits the project scope

### Feature Request Template
```markdown
**Is your feature request related to a problem? Please describe.**
A clear and concise description of what the problem is.

**Describe the solution you'd like**
A clear and concise description of what you want to happen.

**Describe alternatives you've considered**
A clear and concise description of any alternative solutions or features you've considered.

**Additional context**
Add any other context or screenshots about the feature request here.
```

## 🔍 Pull Request Guidelines

### Before Submitting
- Test your changes on both iOS and Android
- Ensure existing functionality still works
- Update documentation if needed
- Add comments for complex code
- Follow code style guidelines

### PR Description Template
```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update

## Testing
- [ ] Tested on iOS
- [ ] Tested on Android
- [ ] Tested with backend API
- [ ] No existing functionality broken

## Screenshots
If applicable, add screenshots of your changes

## Checklist
- [ ] My code follows the style guidelines
- [ ] I have performed a self-review of my code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
```

## 🧪 Testing

### Manual Testing
Test the following areas:
- **Authentication**: Login, registration, token handling
- **Friend System**: Send/accept/decline friend requests
- **Messaging**: Send text, images, emojis
- **Navigation**: All screen transitions
- **Error Handling**: Network errors, invalid inputs

### Platform Testing
- Test on iOS (simulator and/or device)
- Test on Android (emulator and/or device)
- Test different screen sizes
- Test network conditions (offline, slow)

## 📝 Documentation

### Code Documentation
- Add JSDoc comments for functions
- Document complex algorithms
- Include usage examples
- Document API endpoints

### README Updates
- Update features list for new functionality
- Add new screenshots if UI changes
- Update installation steps if needed
- Keep troubleshooting section current

## 🏷️ Labels

We use these labels to categorize issues and PRs:

### Type Labels
- `bug` - Something isn't working
- `enhancement` - New feature or request
- `documentation` - Improvements or additions to documentation
- `good first issue` - Good for newcomers
- `help wanted` - Extra attention is needed

### Priority Labels
- `priority: high` - Urgent issues
- `priority: medium` - Normal priority
- `priority: low` - Nice to have

### Status Labels
- `status: needs review` - Awaiting review
- `status: in progress` - Currently being worked on
- `status: blocked` - Blocked by other issues

## 🤝 Community Guidelines

### Be Respectful
- Use welcoming and inclusive language
- Be respectful of differing viewpoints
- Accept constructive criticism gracefully
- Focus on what is best for the community

### Be Collaborative
- Help others with their contributions
- Share knowledge and experience
- Provide constructive feedback
- Celebrate others' successes

### Communication
- Be clear and concise in communication
- Ask questions if you're unsure
- Provide context for your contributions
- Follow up on your contributions

## 🎯 Areas for Contribution

### High Priority
- Bug fixes for reported issues
- Performance improvements
- Security enhancements
- Test coverage improvements

### Medium Priority
- New features from roadmap
- UI/UX improvements
- Documentation improvements
- Code refactoring

### Good First Issues
- Documentation updates
- Small bug fixes
- Code formatting
- Adding comments
- Simple feature additions

## 📞 Getting Help

If you need help:
1. Check the README.md for setup instructions
2. Search existing issues
3. Create a new issue with the "help wanted" label
4. Join our community discussions (when available)

## 🙏 Recognition

Contributors will be:
- Listed in the README.md
- Mentioned in release notes for significant contributions
- Invited to join our contributor community
- Given credit in the project documentation

Thank you for contributing to ChatApp! 🎉