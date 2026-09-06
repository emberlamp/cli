<p align="center">
  <img src="https://raw.githubusercontent.com/Coccinella-Labs/cli/main/.github/assets/thumbnail.png" alt="cli" width="100%">
</p>

# emberlamp

Master CLI to control all Emberlamp repositories.

## Dynamic Repository Management

The CLI fetches the list of repositories dynamically from [emberlamp/config](https://github.com/emberlamp/config) → `repos.json`. This means you don't need to update the CLI when adding new repos - just update the JSON file!

### To add new repos:
1. Update [repos.json](https://github.com/emberlamp/config/blob/main/repos.json) in the config repo
2. All emberlamp CLI commands will automatically use the updated list

## Installation

```bash
gh extension install emberlamp/cli
```

Or add to PATH:
```bash
cp emberlamp /usr/local/bin/
```

## Usage

```bash
# List all repositories
emberlamp list

# Clone all repos
emberlamp clone ~/emberlamp

# Pull all repos
emberlamp pull

# Push all repos
emberlamp push

# Show status
emberlamp status

# Create new repo
emberlamp create new-repo "Description"

# Execute command in all repos (tested with real example)
emberlamp exec "echo 'test' > test.txt"
emberlamp exec "git add -A && git commit -m 'chore: add test file' && git push"
```

## Examples - Tested Workflow

```bash
# 1. Clone all repos
emberlamp clone ~/emberlamp

# 2. Change to the cloned directory
cd ~/emberlamp

# 3. Add a file to all repos
emberlamp exec "echo 'test' > test.txt"

# 4. Commit and push to all repos (successfully pushed to all 11 repos!)
emberlamp exec "git add -A && git commit -m 'chore: add test file' && git push"
```

## Commands

| Command | Description |
|---------|-------------|
| `list` | List all Emberlamp repos |
| `clone [dir]` | Clone all repos to directory |
| `pull` | Pull all cloned repos |
| `push` | Push all cloned repos |
| `status` | Show status of all repos |
| `create <name> [desc]` | Create new repository |
| `exec <command>` | Execute command in all repos |

## Repositories Managed

Managed dynamically from `repos.json` in [emberlamp/config](https://github.com/emberlamp/config).

## Future: Automation with GitHub Bot

A GitHub bot can be created to:
- Automatically sync repos list from config to all extensions
- Trigger updates when `repos.json` changes
- Run scheduled tasks across all repos

To implement, you would need:
1. Create a GitHub App or use existing token
2. Add repository dispatch webhook
3. Create a workflow that listens for config changes

Would you like to create a bot for this automation?