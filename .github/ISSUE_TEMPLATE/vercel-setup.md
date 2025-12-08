---
name: Vercel Setup
about: Guide for setting up Vercel deployment integration
title: '[Setup] Configure Vercel Deployment'
labels: ['setup', 'vercel', 'deployment']
assignees: ['chaishillomnitech1']
---

## Vercel Deployment Setup

This issue tracks the setup and configuration of Vercel deployment integration for this repository.

### Prerequisites

- [ ] Vercel account created
- [ ] Repository connected to Vercel
- [ ] Vercel project created

### Configuration Steps

#### 1. Vercel Project Setup

- [ ] Create new project in Vercel dashboard
- [ ] Link to this GitHub repository
- [ ] Configure build settings:
  - Framework: (specify if applicable)
  - Build Command: `npm run build`
  - Output Directory: `dist`
  - Install Command: `npm install`
  - Node Version: 20

#### 2. GitHub Secrets Configuration

Configure the following secrets in repository settings (`Settings → Secrets and variables → Actions`):

- [ ] `VERCEL_TOKEN` - Personal Access Token from Vercel
  - Get from: https://vercel.com/account/tokens
  - Scope: Full access
  
- [ ] `VERCEL_ORG_ID` - Organization ID
  - Get from: Vercel project settings → General
  
- [ ] `VERCEL_PROJECT_ID` - Project ID
  - Get from: Vercel project settings → General

#### 3. Vercel Environment Variables

Configure in Vercel project settings (`Settings → Environment Variables`):

- [ ] `NODE_ENV` = `production`
- [ ] Any other required environment variables from `.env.example`

#### 4. GitHub Integration

- [ ] Enable Vercel GitHub app
- [ ] Grant repository access
- [ ] Configure automatic deployments:
  - [ ] Production branch: `main`
  - [ ] Deploy on push: Enabled
  - [ ] Deploy previews: Enabled

### Verification

- [ ] Test workflow by triggering manual deployment
- [ ] Verify preview deployment on test PR
- [ ] Verify production deployment on merge to main
- [ ] Check deployment URLs are accessible

### Testing

```bash
# Trigger manual workflow
gh workflow run vercel-deploy.yml

# Or use GitHub Actions UI
```

### Resources

- [Vercel Documentation](https://vercel.com/docs)
- [GitHub Actions Integration](https://vercel.com/docs/concepts/git/vercel-for-github)
- [DEPLOYMENT.md](../DEPLOYMENT.md)

### Notes

<!-- Add any additional notes or context here -->

### Support

For issues or questions, contact @chaishillomnitech1
