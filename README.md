# ai-learning

Experimenting with agentic coding workflows.

## Setup notes (4 février 2026)

This repository was created locally under a parent folder named `github-repo` so it can be excluded from Dropbox sync (per the `dropbox.ignore` rule on folder names).

### GitHub CLI installation and authentication

- Installed GitHub CLI on macOS using Homebrew.
- Logged in via `gh auth login` using the web browser flow.
- Authenticated to the GitHub account `YaganHazard`.

### Repository creation

- Initialized git in this directory.
- Added a minimal `README.md` and `.gitignore`.
- Created the remote GitHub repository `YaganHazard/ai-learning`.
- Added the `origin` remote and pushed the initial commit to `main`.

## Environment setup notes (5 février 2026)

### Homebrew permissions fix

- `brew` installs initially failed because Homebrew directories were not writable.
- Fixed by updating ownership and permissions for `/opt/homebrew` and `~/Library/Caches/Homebrew`.

### CLI and terminal tools installed

- Installed Node.js (via Homebrew).
- Installed Bun (via Homebrew).
- Installed GitHub Copilot CLI (via Homebrew).
- Installed OpenAI Codex CLI (via Homebrew).
- Installed Ghostty terminal (via Homebrew cask).

### Codex authentication and plugins

- Logged into Codex with ChatGPT auth (`codex login`).
- Installed the Every/Compound Engineering plugin for Codex using:
  `bunx @every-env/compound-plugin install compound-engineering --to codex`

### Copilot CLI status

- Copilot CLI login succeeded.
- Running commands later showed `Failed to list models`, likely due to institutional network restrictions.
