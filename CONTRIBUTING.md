# Contributing to WhatsApp Desktop UWP Archive

Thank you for your interest in contributing to this archive project! This repository serves as documentation and preservation of the original WhatsApp Desktop UWP application.

## Types of Contributions

We welcome the following types of contributions:

### 📝 Documentation
- Improve existing documentation
- Add new guides or tutorials
- Fix typos and grammar
- Translate documentation to other languages
- Add screenshots or diagrams

### 🐛 Issue Reports
- Report bugs or problems with the archived app
- Document workarounds for known issues
- Share compatibility information
- Report security vulnerabilities (see Security Policy below)

### 💡 Feature Documentation
- Document undocumented features
- Add usage tips and tricks
- Share configuration best practices
- Write comparison guides

### ❌ What We Don't Accept
- Source code modifications (we don't have the source)
- Binary patches or modifications
- Requests for new features (app is archived)
- License violations or piracy
- Malicious content or exploits

## How to Contribute

### Reporting Issues

1. **Search first**: Check if the issue already exists
2. **Use templates**: Fill out the issue template completely
3. **Be specific**: Include Windows version, app version, steps to reproduce
4. **Add screenshots**: Visual aids help tremendously

### Suggesting Documentation Improvements

1. **Open an issue**: Describe what documentation is missing or unclear
2. **Propose changes**: If you have specific text, share it
3. **Link references**: Include any relevant links or sources

### Submitting Pull Requests

1. **Fork the repository**
2. **Create a branch**: `git checkout -b docs/improve-installation-guide`
3. **Make your changes**: Edit documentation files
4. **Test your changes**: Ensure formatting is correct
5. **Commit with clear messages**: `git commit -m "docs: Add Windows 11 installation steps"`
6. **Push to your fork**: `git push origin docs/improve-installation-guide`
7. **Open a Pull Request**: Describe your changes clearly

#### Pull Request Guidelines

- **One topic per PR**: Don't mix unrelated changes
- **Clear descriptions**: Explain what and why
- **Follow existing style**: Match the tone and format
- **Link related issues**: Reference relevant issue numbers
- **Be patient**: Reviews may take time

#### Commit Message Format

Follow this format for commit messages:

```
<type>: <short description>

[optional longer description]

[optional footer]
```

Types:
- `docs`: Documentation changes
- `fix`: Bug fixes in documentation
- `feat`: New documentation sections
- `refactor`: Reorganizing documentation
- `style`: Formatting, typos, etc.

Examples:
```
docs: Add troubleshooting section for Windows 11

fix: Correct PowerShell command in installation guide

feat: Add technical architecture diagrams
```

### Documentation Style Guide

#### Markdown Formatting

- Use ATX-style headers (`#` for h1, `##` for h2, etc.)
- Use fenced code blocks with language tags
- Use tables for comparisons
- Use task lists for checklists
- Add blank lines around blocks for readability

#### Writing Style

- **Be clear and concise**: Get to the point
- **Use active voice**: "Click Install" not "Install should be clicked"
- **Be specific**: Include version numbers and exact steps
- **Be inclusive**: Use "we" and "you" appropriately
- **Be respectful**: Assume good faith from readers

#### Technical Content

- **Test commands**: Verify all commands work
- **Include output**: Show expected results
- **Warn about risks**: Use ⚠️ for warnings
- **Provide alternatives**: Offer multiple methods when possible
- **Link to sources**: Reference official documentation

#### Code Examples

```powershell
# Good: Include comments and expected output
Get-AppxPackage -Name "*WhatsApp*"

# Output:
# Name              : WhatsApp.Desktop
# Version           : 2.2148.8.0
```

```powershell
# Bad: No context or explanation
Get-AppxPackage
```

### Translations

We welcome translations of documentation:

1. Create a new directory: `docs/[language-code]/`
2. Translate documentation files
3. Maintain the same structure as English docs
4. Keep technical terms in English (e.g., "UWP", "XAML")
5. Update links to point to translated versions

Supported languages welcome:
- Spanish (es)
- French (fr)
- German (de)
- Portuguese (pt)
- Italian (it)
- Russian (ru)
- Chinese (zh)
- Japanese (ja)
- Arabic (ar)
- Hindi (hi)

## Security Policy

### Reporting Security Vulnerabilities

⚠️ **Do not open public issues for security vulnerabilities**

If you discover a security issue:

1. **Email the maintainer** with details (see GitHub profile)
2. Include:
   - Description of the vulnerability
   - Steps to reproduce
   - Potential impact
   - Suggested fix (if any)
3. **Allow time for response**: We'll try to respond within 7 days
4. **Coordinate disclosure**: We'll work with you on timing

### Security Considerations

Remember:
- This is an **archived app** with no official security updates
- Document security issues for user awareness
- Don't share exploits publicly without coordination
- Prioritize user safety in all contributions

## Code of Conduct

### Our Standards

**Be respectful:**
- Use welcoming and inclusive language
- Respect differing viewpoints and experiences
- Accept constructive criticism gracefully
- Focus on what's best for the community

**Be collaborative:**
- Offer help to newcomers
- Share knowledge freely
- Give credit where it's due
- Be open to feedback

**Be responsible:**
- Don't share personal information
- Don't promote piracy or illegal activity
- Don't harass or discriminate
- Follow GitHub's Terms of Service

### Enforcement

Violations of the Code of Conduct may result in:
1. Warning from maintainers
2. Temporary ban from contributing
3. Permanent ban from the project

Report issues to project maintainers.

## Development Setup

This is a documentation-only repository, so no complex development setup is needed.

### Prerequisites

- Git for version control
- Text editor or IDE (VS Code recommended)
- Markdown preview tool
- Basic knowledge of Markdown syntax

### Recommended Tools

- **VS Code** with extensions:
  - Markdown All in One
  - Markdown Preview Enhanced
  - Code Spell Checker
  - markdownlint

### Local Preview

```bash
# Clone your fork
git clone https://github.com/YOUR-USERNAME/WhatsApp-Desktop-UWP.git
cd WhatsApp-Desktop-UWP

# Create a branch
git checkout -b docs/my-improvement

# Edit files with your preferred editor
code .

# Preview Markdown (in VS Code)
# Ctrl+Shift+V or Cmd+Shift+V
```

## Testing Documentation Changes

Before submitting:

- [ ] Check all links work
- [ ] Verify code blocks are properly formatted
- [ ] Test any commands or scripts
- [ ] Check spelling and grammar
- [ ] Ensure images load correctly
- [ ] Verify markdown renders properly
- [ ] Read through as a new user would

## Review Process

1. **Automatic checks**: GitHub Actions may run linters
2. **Maintainer review**: A maintainer will review your PR
3. **Feedback**: You may receive change requests
4. **Iteration**: Make requested changes
5. **Approval**: Once approved, PR will be merged
6. **Credit**: You'll be listed as a contributor

### Review Criteria

- Accuracy of information
- Clarity of writing
- Proper formatting
- No broken links
- Follows style guide
- Adds value to project

## Questions?

If you have questions about contributing:

1. Check existing [Issues](../../issues) and [Discussions](../../discussions)
2. Review this guide again
3. Open a new issue with the "question" label
4. Be specific about what you need help with

## Recognition

Contributors are recognized in several ways:

- Listed in GitHub contributors
- Mentioned in release notes (for significant contributions)
- Credit in relevant documentation sections
- Appreciation and thanks from the community!

## License

By contributing, you agree that your contributions will be included in this documentation repository under the same terms as existing content.

The WhatsApp application itself remains property of WhatsApp LLC / Meta Platforms, Inc. We only document and archive information about the application.

## Getting Started Checklist

Ready to contribute? Here's a quick checklist:

- [ ] Read this entire guide
- [ ] Fork the repository
- [ ] Set up your local environment
- [ ] Look for issues labeled "good first issue" or "documentation"
- [ ] Make your changes
- [ ] Test your changes
- [ ] Submit a pull request
- [ ] Respond to feedback

## Additional Resources

- [GitHub Docs - Contributing to Projects](https://docs.github.com/en/get-started/quickstart/contributing-to-projects)
- [Markdown Guide](https://www.markdownguide.org/)
- [Writing Good Commit Messages](https://chris.beams.io/posts/git-commit/)
- [Open Source Guides](https://opensource.guide/)

---

Thank you for helping preserve and document this piece of software history! 🙏
