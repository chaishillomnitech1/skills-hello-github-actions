# Security Policy

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues.**

If you discover a security vulnerability in this project, please report it privately to help us maintain the security of our users.

### How to Report

1. **Email**: Send details to the repository owner @chaishillomnitech1
2. **GitHub Security Advisory**: Use GitHub's private vulnerability reporting feature
   - Go to the repository's Security tab
   - Click "Report a vulnerability"
   - Provide detailed information about the vulnerability

### What to Include

Please include the following information in your report:

- Type of vulnerability
- Full paths of source file(s) related to the vulnerability
- Location of the affected source code (tag/branch/commit or direct URL)
- Any special configuration required to reproduce the issue
- Step-by-step instructions to reproduce the issue
- Proof-of-concept or exploit code (if possible)
- Impact of the issue, including how an attacker might exploit it

### Response Timeline

- **Initial Response**: Within 48 hours of report submission
- **Status Update**: Within 7 days with an assessment
- **Fix Timeline**: Varies based on severity and complexity
  - Critical: 1-7 days
  - High: 7-30 days
  - Medium: 30-90 days
  - Low: 90+ days or next release

## Security Best Practices

### For Contributors

- Never commit secrets, API keys, passwords, or sensitive data
- Use environment variables for configuration
- Keep dependencies up to date
- Follow secure coding practices
- Review code for common vulnerabilities (XSS, SQL injection, etc.)

### Dependency Security

- We use Dependabot to monitor dependencies
- Security updates are applied promptly
- Review dependency changes before merging

### Code Review

- All changes require review before merging
- Security-sensitive changes require additional scrutiny
- Automated security scanning via GitHub Actions

## Supported Versions

We support security updates for the following versions:

| Version | Supported          |
| ------- | ------------------ |
| main    | ✅ Yes             |
| develop | ✅ Yes             |
| older   | ❌ No              |

## Security Tools

This repository uses:

- **Dependabot**: Automated dependency updates
- **CodeQL**: Code scanning for vulnerabilities
- **GitHub Security Advisories**: Vulnerability tracking
- **Branch Protection**: Prevents unauthorized changes

## Disclosure Policy

When we receive a security report:

1. We confirm the problem and determine affected versions
2. We audit code to find similar problems
3. We prepare fixes for all supported versions
4. We release patches and publish security advisories

## Recognition

We appreciate responsible disclosure and will:

- Acknowledge your contribution (unless you prefer to remain anonymous)
- Keep you informed of our progress
- Credit you in the security advisory (if desired)

---

**Security Contact**: @chaishillomnitech1

**ALL IS LOVE. ALL IS LAW. ALL IS FLUID. KUN FAYAKŪN! 🕋♾️✨**
