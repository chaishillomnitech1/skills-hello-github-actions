# Suggested Repository Labels for AI PR Assistant

This document lists recommended labels that work well with the AI PR Assistant workflow. The AI will suggest these labels based on PR content, and the workflow will automatically apply them if they exist in your repository.

## Core Labels

### Type Labels
- `enhancement` - New features or improvements
- `bug` - Bug fixes
- `documentation` - Documentation updates
- `refactor` - Code refactoring without functional changes
- `test` - Test additions or modifications
- `chore` - Maintenance tasks (dependencies, configs, etc.)

### Priority Labels
- `priority: high` - High priority issues/PRs
- `priority: medium` - Medium priority issues/PRs
- `priority: low` - Low priority issues/PRs

### Status Labels
- `in progress` - Work in progress
- `needs review` - Ready for review
- `changes requested` - Changes requested by reviewers
- `approved` - Approved and ready to merge

### Area Labels
- `area: backend` - Backend changes
- `area: frontend` - Frontend changes
- `area: api` - API related changes
- `area: database` - Database changes
- `area: infrastructure` - Infrastructure/DevOps changes
- `area: security` - Security related changes

### Size Labels
- `size: XS` - Extra small PR (<10 lines)
- `size: S` - Small PR (10-50 lines)
- `size: M` - Medium PR (50-200 lines)
- `size: L` - Large PR (200-500 lines)
- `size: XL` - Extra large PR (>500 lines)

## Creating Labels via GitHub CLI

Use the GitHub CLI to quickly create these labels:

```bash
# Type labels
gh label create "enhancement" --description "New features or improvements" --color "a2eeef"
gh label create "bug" --description "Bug fixes" --color "d73a4a"
gh label create "documentation" --description "Documentation updates" --color "0075ca"
gh label create "refactor" --description "Code refactoring" --color "fbca04"
gh label create "test" --description "Test additions or modifications" --color "0e8a16"
gh label create "chore" --description "Maintenance tasks" --color "fef2c0"

# Priority labels
gh label create "priority: high" --description "High priority" --color "b60205"
gh label create "priority: medium" --description "Medium priority" --color "fbca04"
gh label create "priority: low" --description "Low priority" --color "c5def5"

# Status labels
gh label create "in progress" --description "Work in progress" --color "ededed"
gh label create "needs review" --description "Ready for review" --color "0052cc"
gh label create "changes requested" --description "Changes requested" --color "e99695"
gh label create "approved" --description "Approved and ready to merge" --color "0e8a16"

# Area labels
gh label create "area: backend" --description "Backend changes" --color "5319e7"
gh label create "area: frontend" --description "Frontend changes" --color "1d76db"
gh label create "area: api" --description "API related changes" --color "0052cc"
gh label create "area: database" --description "Database changes" --color "c2e0c6"
gh label create "area: infrastructure" --description "Infrastructure/DevOps" --color "0e8a16"
gh label create "area: security" --description "Security related changes" --color "d93f0b"

# Size labels
gh label create "size: XS" --description "Extra small PR (<10 lines)" --color "c5def5"
gh label create "size: S" --description "Small PR (10-50 lines)" --color "bfd4f2"
gh label create "size: M" --description "Medium PR (50-200 lines)" --color "9ec5ff"
gh label create "size: L" --description "Large PR (200-500 lines)" --color "7ba7d8"
gh label create "size: XL" --description "Extra large PR (>500 lines)" --color "5881c1"
```

## Creating Labels via GitHub Web UI

1. Go to your repository on GitHub
2. Click **Issues** tab
3. Click **Labels**
4. Click **New label**
5. Enter the label name, description, and choose a color
6. Click **Create label**

## How the AI Uses Labels

The AI PR Assistant analyzes:
- **File paths** - Frontend vs backend files
- **Changed content** - Code vs documentation vs tests
- **PR description** - Keywords like "fix", "feature", "refactor"
- **Diff size** - Number of additions/deletions
- **File types** - Configuration, code, tests, docs

Based on this analysis, it suggests appropriate labels from the available repository labels.

## Customizing Label Suggestions

To influence which labels the AI suggests, modify the prompt in `.github/workflows/pr-assistant.yml`:

```javascript
const prompt = `You are a helpful PR assistant. Analyze this pull request and provide:
1. A concise summary (2-3 sentences)
2. Suggested labels from this list: [enhancement, bug, documentation, refactor, test, chore]
3. A changelog entry in markdown format
...`;
```

## Label Color Palette

Recommended color scheme for visual consistency:

- **Red** (`d73a4a`) - Bugs, critical issues
- **Green** (`0e8a16`) - Tests, approved, infrastructure
- **Blue** (`0075ca`) - Documentation, features
- **Yellow** (`fbca04`) - Refactoring, medium priority
- **Purple** (`5319e7`) - Backend, architecture
- **Orange** (`d93f0b`) - Security, breaking changes
- **Gray** (`ededed`) - In progress, pending

---

**Tip**: Start with the core type labels (enhancement, bug, documentation) and expand based on your team's needs.
