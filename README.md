# emberlamp

Master CLI to control all Emberlamp repositories.

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

# 4. Commit and push to all repos (successfully pushed to all 10 repos!)
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

- general - Main app
- react-template - React template
- swe-agent - SWE agent template
- gh-pin-repo - Pin repo extension
- config - Config extension
- license - Shared license
- warnings - Warning messages
- json-repo - JSON schemas
- gitkeep - Placeholder
- .github - Org profile