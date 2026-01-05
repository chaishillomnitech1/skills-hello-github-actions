# Quick Reference Guide - Universal Enhancements

This quick reference guide helps you navigate and use the new universal best-practice enhancements.

## 📋 Creating Issues

### Bug Reports
Use the **Bug Report** template when:
- Something isn't working as expected
- You encounter an error or crash
- Features behave unexpectedly

**Location**: `.github/ISSUE_TEMPLATE/bug_report.md`

**Auto-filled**: Labels, assignee (@chaishillomnitech1)

### Feature Requests
Use the **Feature Request** template when:
- Proposing new functionality
- Suggesting improvements
- Requesting enhancements

**Location**: `.github/ISSUE_TEMPLATE/feature_request.md`

**Auto-filled**: Enhancement label, assignee (@chaishillomnitech1)

### General Issues
Use the **General Issue** template for:
- Questions
- Documentation updates
- General discussions
- Tasks or TODO items

**Location**: `.github/ISSUE_TEMPLATE/general_issue.md`

## 🔄 Creating Pull Requests

All PRs automatically use the template at:
**`.github/PULL_REQUEST_TEMPLATE.md`**

### PR Checklist
- [ ] Describe your changes
- [ ] Select type of change
- [ ] Link related issues
- [ ] List changes made
- [ ] Verify tests pass
- [ ] Complete checklist
- [ ] Add screenshots (if UI changes)

### PR Assignee
Default: @chaishillomnitech1

## 🔧 CI/CD Workflows

### Automatic Triggers

| Workflow | Trigger | Purpose |
|----------|---------|---------|
| **CI - Install & Build** | Push/PR to main, develop | Install deps & build |
| **CI - Test Suite** | Push/PR to main, develop | Run all tests |
| **CD - Deploy** | Push to main, releases | Deploy to production |

### Manual Triggers

All workflows support `workflow_dispatch` for manual runs:
1. Go to **Actions** tab
2. Select workflow
3. Click **Run workflow**

### Viewing Results

- **Workflow runs**: Actions tab
- **PR comments**: Automated status comments on PRs
- **Artifacts**: Download from workflow run page

## 🛡️ Security

### Reporting Vulnerabilities

**DO NOT** use public issues for security vulnerabilities.

**DO**:
1. Use GitHub Security Advisory
2. Or email @chaishillomnitech1 privately

**Reference**: `SECURITY.md`

### Security Features
- Dependabot enabled
- CodeQL scanning (if configured)
- Branch protection recommended
- Required code reviews

## 👥 Code Ownership

All files are owned by **@chaishillomnitech1**

### CODEOWNERS Coverage
- All files by default
- GitHub configurations
- Workflows
- Templates
- Documentation
- Security files

**Reference**: `CODEOWNERS`

## 📚 Documentation Files

### For New Contributors
📖 **Start here**: `ONBOARDING.md`

Covers:
- Quick start
- Repository structure
- Development workflow
- Testing procedures
- Getting help

### For Repository Admins
🔒 **Branch Protection**: `BRANCH_PROTECTION.md`

Covers:
- Protection rules for main/develop
- Step-by-step setup
- Required status checks
- Code review requirements

### For Security Team
🛡️ **Security Policy**: `SECURITY.md`

Covers:
- Vulnerability reporting
- Security best practices
- Supported versions
- Disclosure policy

### For DAO Integration
🌐 **DAO Automation**: `DAO_AUTOMATION.md`

Covers:
- Contribution rewards
- Governance proposals
- Scoring system
- NFT badges
- Smart contract integration

### Complete Summary
📊 **Enhancement Summary**: `ENHANCEMENT_SUMMARY.md`

Comprehensive overview of all enhancements.

## 🚀 Workflow Commands

### Run Build Locally
```bash
npm ci
npm run build
```

### Run Tests Locally
```bash
npm test
npm run test:integration
npm run test:e2e
```

### Check Linting
```bash
npm run lint
```

### Deploy
Handled automatically by CD workflow on push to main.

## 🎯 Quick Tips

### For Contributors
1. Read `ONBOARDING.md` first
2. Use issue templates
3. Follow PR template
4. Wait for CI checks
5. Address review comments

### For Reviewers
1. Check CI status
2. Review code quality
3. Verify tests included
4. Check security implications
5. Use CODEOWNERS as guide

### For Maintainers
1. Configure branch protection (`BRANCH_PROTECTION.md`)
2. Enable security features (`SECURITY.md`)
3. Set up DAO integration (`DAO_AUTOMATION.md`)
4. Monitor workflow runs
5. Update templates as needed

## 🔍 Finding Information

| What you need | Where to look |
|---------------|---------------|
| Getting started | `ONBOARDING.md` |
| How to contribute | `CONTRIBUTING.md` |
| Security policy | `SECURITY.md` |
| Branch protection | `BRANCH_PROTECTION.md` |
| DAO features | `DAO_AUTOMATION.md` |
| Enhancement details | `ENHANCEMENT_SUMMARY.md` |
| Issue templates | `.github/ISSUE_TEMPLATE/` |
| PR template | `.github/PULL_REQUEST_TEMPLATE.md` |
| Workflows | `.github/workflows/` |
| Code ownership | `CODEOWNERS` |

## 📞 Getting Help

### Questions?
- Create a **General Issue**
- Check `ONBOARDING.md`
- Review existing documentation

### Security Issues?
- Follow `SECURITY.md` process
- Contact @chaishillomnitech1 privately

### Feature Ideas?
- Create a **Feature Request**
- Include details and benefits
- Discuss with community

### Bugs?
- Create a **Bug Report**
- Include reproduction steps
- Provide environment details

## 🎨 Philosophy

Every interaction aligns with:

**ALL IS LOVE. ALL IS LAW. ALL IS FLUID. KUN FAYAKŪN! 🕋♾️✨**

- **ALL IS LOVE**: Collaborative, respectful community
- **ALL IS LAW**: Structured processes and governance
- **ALL IS FLUID**: Adaptable, evolving systems
- **KUN FAYAKŪN**: Manifestation through divine will

## ✅ Next Steps

1. ✅ Read this guide
2. ✅ Review `ONBOARDING.md`
3. ✅ Explore templates
4. ✅ Try creating an issue
5. ✅ Submit your first PR
6. ✅ Join the community

---

**Maintained by**: @chaishillomnitech1

**Last Updated**: 2026-01-05

**ALL IS LOVE. ALL IS LAW. ALL IS FLUID. KUN FAYAKŪN! 🕋♾️✨**
