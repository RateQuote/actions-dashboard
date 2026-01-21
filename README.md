# RateQuote GitHub Actions Dashboard

A real-time dashboard for viewing GitHub Actions workflow runs across the entire RateQuote organization.

## 🌐 Live Dashboard

Access the dashboard at: **https://ratequote.github.io/actions-dashboard/**

## 🔑 Setup

### 1. Create a GitHub Personal Access Token

1. Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click "Generate new token (classic)"
3. Give it a name like "Actions Dashboard"
4. Select the following scopes:
   - `repo` (Full control of private repositories)
   - `workflow` (Update GitHub Action workflows)
5. Click "Generate token"
6. **Copy the token** (you won't see it again!)

### 2. Use the Dashboard

1. Open the dashboard URL
2. Paste your GitHub token in the input field (it's stored locally in your browser)
3. Click "Refresh" or select a filter

The token is stored in your browser's localStorage and will persist across sessions.

## ✨ Features

- **Real-time monitoring** of all workflow runs across the RateQuote org
- **Filter by status**: View in-progress, queued, or completed runs
- **Filter by repository**: Search for specific repos
- **Statistics**: See counts of in-progress, queued, successful, and failed runs
- **Auto-refresh**: Optional 30-second auto-refresh
- **Direct links**: Click through to view runs on GitHub

## 🔒 Security

- Your GitHub token is stored **only in your browser's localStorage**
- The token is never sent to any server (except GitHub's API directly from your browser)
- All API calls are made client-side via JavaScript
- This is a static site with no backend

## 📊 Dashboard Sections

### Stats Bar
- **In Progress**: Currently running workflows
- **Queued**: Workflows waiting to start
- **Success (24h)**: Successful runs in the last 24 hours
- **Failure (24h)**: Failed runs in the last 24 hours

### Runs Table
Shows all workflow runs with:
- Repository name
- Workflow name
- Branch
- Status
- Start time
- Commit SHA
- Direct link to the run

## 🔧 Local Development

To run locally:

```bash
# Serve the dashboard locally
python3 -m http.server 8000

# Or use any other static file server
npx serve .
```

Then open http://localhost:8000

## 🚀 Deployment

This dashboard is deployed using GitHub Pages. Any push to the `main` branch will automatically update the live site.

## 📝 Notes

- The dashboard fetches up to 10 recent runs per repository
- Repositories without Actions enabled are silently skipped
- The dashboard works entirely client-side (no backend required)
