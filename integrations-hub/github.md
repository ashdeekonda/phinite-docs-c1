---
title: "GitHub"
description: "Repositories and issues management via GitHub API."
icon: "github"
---

## Overview

Phinite's GitHub integration allows workspace assistants to interact with GitHub repositories, manage issues, pull requests, and collaborate on code projects.

This document explains what credentials are required, how to obtain them from GitHub, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Create and manage issues
- Handle pull requests
- Access repository information
- Manage branches and commits
- Add comments and reviews
- Automate repository workflows

This integration is bidirectional and uses GitHub's official REST API.

## Required credentials

Phinite uses 1 credential provided by GitHub:

- Personal Access Token (required)

These credentials are generated through GitHub's developer settings. Phinite does not modify or replace GitHub's authentication model.

## Setup steps

### Step 1: Create GitHub Personal Access Token

1. Go to GitHub.com and sign in
2. Click your profile picture (top right)
3. Go to Settings → Developer settings → Personal access tokens
4. Click "Tokens (classic)" or "Fine-grained tokens"
5. Click "Generate new token"
6. Give it a descriptive name (e.g., "Phinite Integration")
7. Select appropriate scopes:
   - repo (full repository access)
   - user (user information)
   - project (project management)
8. Set expiration if desired
9. Click "Generate token"

### Step 2: Copy Token

1. Immediately copy the generated token
2. Store it securely (you won't see it again)
3. Token format: ghp_xxxxxxxxxxxxxxxxxxxx

### Step 3: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select GitHub
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: GitHub Integration
   - Personal Access Token: Paste your token
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for GitHub:

- Create Issue: Open new repository issues
- Update Issue: Modify existing issues
- Close Issue: Mark issues as resolved
- Get Issue: Retrieve issue details
- List Issues: Query repository issues
- Create Pull Request: Submit code changes
- Update Pull Request: Modify pull requests
- Merge Pull Request: Merge approved changes
- Add Comment: Comment on issues/PRs
- Create Branch: Set up new branches
- Get Repository: Access repo information
- List Commits: View commit history
- Search Code: Find code across repositories
- Create Release: Tag and release versions
- Get User: Retrieve user profiles
- List Repositories: Access user's repos
- Create Repository: Set up new repositories
- Fork Repository: Create repo forks
- Star Repository: Add stars to repos
- Watch Repository: Follow repositories

## Documentation & resources

- Official GitHub Documentation: `https://docs.github.com/en/rest`
- GitHub REST API Reference: `https://docs.github.com/en/rest/reference`
- GitHub Developer Portal: `https://github.com/settings/developers`

## Notes

- Personal access tokens have repository-specific permissions
- GitHub has rate limits (5000 requests/hour for authenticated users)
- Some operations require repository admin access
- Tokens can be scoped to specific repositories
- Monitor token usage and rotate regularly for security
