# Deployment Guide

## Vercel + GitHub Integration

This repository is configured for automated deployment to Vercel via GitHub Actions and native Vercel integration.

### Prerequisites

1. **Vercel Account**: Create an account at [vercel.com](https://vercel.com)
2. **Vercel Project**: Link this repository to a Vercel project
3. **GitHub Secrets**: Configure required secrets in repository settings

### Required Secrets

Configure the following secrets in GitHub repository settings (Settings → Secrets and variables → Actions):

#### Vercel Integration
- `VERCEL_TOKEN`: Personal Access Token from Vercel account settings
- `VERCEL_ORG_ID`: Organization ID from Vercel project settings
- `VERCEL_PROJECT_ID`: Project ID from Vercel project settings

#### AI Features
- `OPENAI_API_KEY`: OpenAI API key for AI-powered PR bot

#### Rewards System (Pilot/Test)
- `REWARDS_PRIVATE_KEY`: Test private key for rewards contract interaction
- `REWARDS_API_KEY`: API key for rewards service
- `REWARDS_CONTRACT_ADDRESS`: Smart contract address for rewards
- `ALCHEMY_MUMBAI_URL`: Alchemy RPC URL for Mumbai testnet
- `PILOT_TEST_WALLET`: Test wallet address for pilot program

#### Repository Synchronization
- `GITHUB_PAT`: Personal Access Token with repo scope for cross-repo sync

### Deployment Workflow

#### Automatic Deployments

- **Production**: Commits to `main` branch trigger production deployment
- **Preview**: Pull requests trigger preview deployments
- **Manual**: Workflow can be manually triggered from Actions tab

#### Manual Deployment

```bash
# Install Vercel CLI
npm i -g vercel

# Login to Vercel
vercel login

# Deploy to preview
vercel

# Deploy to production
vercel --prod
```

### Environment Variables

Copy `.env.example` to `.env.local` for local development:

```bash
cp .env.example .env.local
```

Configure all required variables before running locally or deploying.

### Vercel Configuration

The `.vercel.json` file configures:
- Build settings (Node 20)
- Output directory
- GitHub integration
- Environment variables

### Troubleshooting

#### Deployment Fails
- Verify all secrets are correctly configured
- Check build logs in Vercel dashboard
- Ensure `package.json` has valid build script

#### Environment Variables Missing
- Add variables to Vercel project settings
- Redeploy to apply new environment variables

#### Preview Deployment Issues
- Ensure Vercel GitHub app has repository access
- Check workflow permissions in repository settings

### Next Steps

1. Merge this PR to enable Phase 2 automations
2. Configure all required secrets in GitHub
3. Verify Vercel project environment variables
4. Run a test deployment to confirm setup

### Support

For issues or questions:
- Check workflow logs in GitHub Actions tab
- Review Vercel deployment logs
- Contact @chaishillomnitech1 for assistance
