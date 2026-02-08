# Publishing to SkillsMP (ClawHub)

This repository is ready to be published as an Agent Skill on the **SkillsMP** marketplace using the `clawdhub` CLI.

## 1. Prerequisites

You need **Node.js** installed (which you already have for this project).

## 2. Authenticate

First, install the CLI tool globally and log in:

```bash
# Install the CLI
npm install -g clawdhub

# Login to your account
clawdhub login
```

## 3. Publish Your Skill

Run this command from the root of your project to publish the `FLWR Branding Studio Kit`:

```bash
clawdhub publish . \
  --slug flwr-branding-agent \
  --name "FLWR Branding Studio Kit" \
  --version 1.0.0 \
  --changelog "Initial release of the autonomous branding strategist."
```

### Parameters Explained:
*   `.`: The current directory (where your `SKILL.md` and logic reside).
*   `--slug`: The unique URL ID for your skill (e.g., `skillsmp.com/skill/flwr-branding-agent`).
*   `--name`: The display name in the marketplace.
*   `--version`: Semantic versioning (update this for future releases).

## 4. Updates

To publish a new version later, just increment the version number:

```bash
clawdhub publish . \
  --slug flwr-branding-agent \
  --name "FLWR Branding Studio Kit" \
  --version 1.0.1 \
  --changelog "Fixed issue with X..."
```
