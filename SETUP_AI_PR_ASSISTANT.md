# AI-Powered PR Assistant Setup Guide

This guide will help you configure and activate the AI-Powered PR Assistant workflow in your repository.

## 🚀 Quick Start

### Step 1: Get an OpenAI API Key

1. Visit [OpenAI Platform](https://platform.openai.com/)
2. Sign up or log in to your account
3. Navigate to **API Keys** section
4. Click **Create new secret key**
5. Copy the generated key (it starts with `sk-`)
6. **Important**: Save this key securely - you won't be able to see it again!

### Step 2: Add the API Key to GitHub Secrets

1. Go to your repository on GitHub
2. Click **Settings** (top menu bar)
3. In the left sidebar, expand **Secrets and variables** → Click **Actions**
4. Click the **New repository secret** button
5. Fill in the details:
   - **Name**: `OPENAI_API_KEY`
   - **Secret**: Paste your OpenAI API key
6. Click **Add secret**

### Step 3: Verify Workflow Files

Ensure these files exist in your repository:
- `.github/workflows/pr-assistant.yml` - The main workflow file
- `.github/workflows/PR_ASSISTANT_README.md` - Detailed documentation

### Step 4: Test the Workflow

1. Create a new branch:
   ```bash
   git checkout -b test-pr-assistant
   ```

2. Make a small change to any file:
   ```bash
   echo "# Test" >> test.md
   git add test.md
   git commit -m "Test PR assistant workflow"
   git push origin test-pr-assistant
   ```

3. Create a pull request on GitHub

4. Wait a few seconds - the AI PR Assistant will automatically:
   - Analyze your PR
   - Generate a summary
   - Suggest labels
   - Create a changelog entry
   - Post a comment with all this information

## ✅ Verification Checklist

- [ ] OpenAI API key obtained
- [ ] API key added to GitHub Secrets as `OPENAI_API_KEY`
- [ ] Workflow file exists at `.github/workflows/pr-assistant.yml`
- [ ] Test PR created
- [ ] AI comment appears on the test PR

## 🔧 Configuration Options

### Change AI Model

Edit `.github/workflows/pr-assistant.yml` and modify the model parameter:

```javascript
model: 'gpt-4',  // Options: gpt-4, gpt-4-turbo, gpt-3.5-turbo
```

**Cost comparison**:
- `gpt-3.5-turbo`: Fastest, cheapest (~$0.002 per PR)
- `gpt-4`: Most accurate (~$0.03 per PR)
- `gpt-4-turbo`: Balanced (~$0.01 per PR)

### Customize AI Prompts

Modify the prompt in the workflow to match your team's needs:

```javascript
const prompt = `You are a helpful PR assistant. Analyze this pull request and provide:
1. A concise summary (2-3 sentences)
2. Suggested labels (comma-separated list)
3. A changelog entry in markdown format
...`;
```

### Adjust Trigger Events

Edit the workflow triggers to control when it runs:

```yaml
on:
  pull_request:
    types: [opened, synchronize, reopened]
    # Add more types: edited, labeled, etc.
```

## 🔒 Security Best Practices

1. **Never commit API keys** to your repository
2. Use **GitHub Secrets** for all sensitive data
3. **Rotate API keys** periodically (every 90 days recommended)
4. **Monitor API usage** in your OpenAI dashboard
5. **Set spending limits** in your OpenAI account
6. **Review permissions** - the workflow only needs what's specified

## 💰 Cost Management

### Estimating Costs

- Average PR analysis: 500-1000 tokens
- GPT-4 pricing: ~$0.03 per PR
- GPT-3.5-turbo pricing: ~$0.002 per PR

For 100 PRs/month:
- With GPT-4: ~$3/month
- With GPT-3.5-turbo: ~$0.20/month

### Setting Limits

1. Go to [OpenAI Usage Limits](https://platform.openai.com/account/limits)
2. Set a monthly budget cap
3. Enable email notifications for usage alerts

## 🐛 Troubleshooting

### Issue: Workflow not running

**Check**:
```bash
# Verify workflow file location
ls -la .github/workflows/pr-assistant.yml

# Check GitHub Actions tab for errors
```

**Solution**: Ensure the file is in the correct location with proper YAML syntax.

### Issue: "OpenAI API key not configured" warning

**Check**:
1. Go to Settings → Secrets and variables → Actions
2. Verify `OPENAI_API_KEY` exists
3. Check the secret name is exactly `OPENAI_API_KEY` (case-sensitive)

**Solution**: Add or update the secret with your valid OpenAI API key.

### Issue: API rate limit errors

**Symptoms**: Workflow fails with 429 errors

**Solution**: 
- Upgrade your OpenAI account tier
- Reduce the number of concurrent PRs
- Add retry logic to the workflow

### Issue: Labels not applied

**Check**: Do the suggested labels exist in your repository?

**Solution**: 
```bash
# Create missing labels via GitHub CLI
gh label create "enhancement" --color "a2eeef"
gh label create "bug" --color "d73a4a"
gh label create "documentation" --color "0075ca"
```

## 📊 Monitoring Usage

### View Workflow Runs

1. Go to **Actions** tab in your repository
2. Select **AI-Powered PR Assistant** workflow
3. View run history and logs

### Check OpenAI Usage

1. Visit [OpenAI Usage Dashboard](https://platform.openai.com/usage)
2. Monitor daily/monthly token usage
3. Review cost breakdown

## 🎯 Best Practices

1. **Start with a test**: Create a test PR to verify everything works
2. **Review AI suggestions**: Don't blindly trust - verify the analysis
3. **Customize prompts**: Tailor the AI behavior to your team's workflow
4. **Monitor costs**: Keep an eye on API usage, especially with GPT-4
5. **Iterate**: Improve the workflow based on team feedback
6. **Document changes**: Update this guide if you modify the workflow

## 🔄 Updating the Workflow

To update the AI PR Assistant:

```bash
# Pull latest changes
git pull origin main

# Edit the workflow
vim .github/workflows/pr-assistant.yml

# Test locally (syntax check)
python3 -c "import yaml; yaml.safe_load(open('.github/workflows/pr-assistant.yml'))"

# Commit and push
git add .github/workflows/pr-assistant.yml
git commit -m "Update PR assistant workflow"
git push
```

## 📚 Additional Resources

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [OpenAI API Documentation](https://platform.openai.com/docs)
- [OpenAI Pricing](https://openai.com/pricing)
- [GitHub Secrets Documentation](https://docs.github.com/en/actions/security-guides/encrypted-secrets)
- [Workflow Syntax Reference](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)

## 🆘 Getting Help

If you encounter issues:

1. **Check workflow logs**: Actions tab → Select failed run → View logs
2. **Review this guide**: Most common issues are covered here
3. **Check GitHub status**: [githubstatus.com](https://www.githubstatus.com/)
4. **Check OpenAI status**: [status.openai.com](https://status.openai.com/)
5. **Open an issue**: Describe the problem with relevant logs

## ✨ Feature Ideas

Want to enhance the workflow? Consider adding:

- Code quality scoring
- Security vulnerability detection
- Breaking change identification
- Test coverage analysis
- PR size recommendations
- Similar PR detection
- Auto-assignment based on file changes
- Slack/Discord notifications

---

**Ready to go?** Create a PR and watch the AI assistant in action! 🚀

For detailed technical documentation, see [PR_ASSISTANT_README.md](.github/workflows/PR_ASSISTANT_README.md).
