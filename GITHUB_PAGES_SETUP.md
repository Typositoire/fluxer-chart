# GitHub Pages Setup Instructions

This document explains how to enable GitHub Pages for this Helm chart repository.

## 📋 Prerequisites

- Repository must be public (or GitHub Pro/Team/Enterprise for private repos)
- Admin access to the repository

## 🚀 Enabling GitHub Pages

### Step 1: Merge to Main Branch

The GitHub Actions workflow will automatically run when changes are pushed to the `main` or `master` branch. Merge this pull request to trigger the deployment.

### Step 2: Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/Typositoire/fluxer-chart`
2. Click on **Settings** (top right)
3. Scroll down to the **Pages** section in the left sidebar
4. Under **Source**, select:
   - **Branch**: `gh-pages`
   - **Folder**: `/ (root)`
5. Click **Save**

### Step 3: Wait for Deployment

- The first deployment may take a few minutes
- GitHub will show a blue banner with your site URL once it's deployed
- Your site will be available at: `https://typositoire.github.io/fluxer-chart/`

## 🔄 Automatic Updates

Once set up, the workflow will automatically:

1. Trigger on every push to the main/master branch
2. Package the Helm chart
3. Generate the repository index
4. Deploy to GitHub Pages

## 🧪 Testing the Helm Repository

After GitHub Pages is live, test the repository:

```bash
# Add the repository
helm repo add fluxer-chart https://typositoire.github.io/fluxer-chart/

# Update repositories
helm repo update

# Search for charts
helm search repo fluxer-chart

# Show chart details
helm show chart fluxer-chart/fluxer-chart
helm show values fluxer-chart/fluxer-chart
```

## 📁 Repository Structure

```
.
├── .github/
│   └── workflows/
│       └── release.yml          # GitHub Actions workflow
├── docs/                        # GitHub Pages content
│   ├── index.html              # Main page
│   ├── index.yaml              # Helm repository index
│   └── fluxer-chart-0.1.0.tgz  # Chart package
├── templates/                   # Helm chart templates
├── Chart.yaml                   # Chart metadata
├── values.yaml                  # Default values
└── README.md                    # Documentation
```

## 🔍 Troubleshooting

### GitHub Pages not showing

- Ensure the `gh-pages` branch exists
- Check that GitHub Pages is configured to use the `gh-pages` branch
- Verify the workflow ran successfully in the **Actions** tab

### Chart not found

- Wait 5-10 minutes after enabling GitHub Pages
- Verify the URL is accessible: `https://typositoire.github.io/fluxer-chart/index.yaml`
- Check that the workflow completed successfully

### Workflow failed

- Check the **Actions** tab for error messages
- Ensure the repository has write permissions for workflows
- Verify the workflow file syntax

## 📞 Support

If you encounter issues:
1. Check the [GitHub Actions logs](https://github.com/Typositoire/fluxer-chart/actions)
2. Verify [GitHub Pages status](https://www.githubstatus.com/)
3. Review [GitHub Pages documentation](https://docs.github.com/en/pages)

## 🎉 Success!

Once complete, your Helm chart repository will be available to anyone who wants to install your chart!

Visit your site at: **https://typositoire.github.io/fluxer-chart/**
