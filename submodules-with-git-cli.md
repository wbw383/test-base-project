# Git Submodule Management with Command Line

## Initial Setup
When cloning this repository for the first time:

### Option 1: Clone with submodules in one command
```bash
git clone --recurse-submodules https://github.com/wbw383/test-base-project.git
```

### Option 2: Clone first, then initialize submodules
```bash
git clone https://github.com/wbw383/test-base-project.git
cd test-base-project
git submodule update --init --recursive
```

## Working with Submodules

### Viewing Submodule Status
```bash
# Check status of all submodules
git submodule status

# Check status with more details
git submodule status --recursive

# Show submodule configuration
git submodule
```

### Updating Submodules
```bash
# Update all submodules to their latest commits on tracked branch
git submodule update --remote --recursive

# Update all submodules to commits specified in parent repository
git submodule update --recursive

# Update a specific submodule
git submodule update --remote test-server

# Pull latest changes including submodule updates
git pull --recurse-submodules
```

### Adding New Submodules
```bash
# Add a new submodule
git submodule add <repository-url> <local-path>

# Example:
git submodule add https://github.com/example/repo.git lib/example

# Add submodule and specify branch to track
git submodule add -b main https://github.com/example/repo.git lib/example
```

### Working in Submodules
```bash
# Navigate to submodule directory
cd test-server

# Make changes and commit in submodule
git add .
git commit -m "Update submodule"
git push origin main

# Return to parent repository
cd ..

# Stage the submodule reference update
git add test-server

# Commit the submodule reference update
git commit -m "Update test-server submodule"
git push
```

### Removing Submodules
```bash
# Remove submodule (Git 2.5+)
git submodule deinit <path>
git rm <path>
git commit -m "Removed submodule <path>"

# Example:
git submodule deinit test-server
git rm test-server
git commit -m "Removed test-server submodule"
```

### Advanced Submodule Operations

#### Execute commands across all submodules
```bash
# Run a command in each submodule
git submodule foreach '<command>'

# Examples:
git submodule foreach 'git pull origin main'
git submodule foreach 'git checkout main'
git submodule foreach 'git status'
```

#### Switch submodule to specific branch
```bash
cd test-server
git checkout main
cd ..
git add test-server
git commit -m "Switch test-server to main branch"
```

#### Reset submodules to parent repository state
```bash
# Reset all submodules to the commits specified in parent
git submodule update --init --recursive

# Force reset (discards local changes)
git submodule update --init --recursive --force
```

#### Sync submodule URLs
```bash
# Update submodule URLs from .gitmodules
git submodule sync --recursive
```

## Common Workflows

### Daily Development Workflow
```bash
# 1. Pull latest changes including submodules
git pull --recurse-submodules

# 2. Work in submodules as needed
cd test-server
# make changes...
git add .
git commit -m "Feature update"
git push

# 3. Return to parent and update reference
cd ..
git add test-server
git commit -m "Update test-server"
git push
```

### Setting up existing repository with submodules
```bash
# If you cloned without --recurse-submodules
git submodule init
git submodule update

# Or in one command
git submodule update --init --recursive
```

### Troubleshooting

#### Fix detached HEAD in submodules
```bash
cd test-server
git checkout main  # or the appropriate branch
cd ..
git add test-server
git commit -m "Fix detached HEAD in test-server"
```

#### Update submodule remote URL
```bash
# Edit .gitmodules file to change URL, then:
git submodule sync test-server
git submodule update --init test-server
```

## Important Notes

- **Always commit submodule changes before committing parent repository**
- **Submodules track specific commits, not branches by default**
- **Use `--recurse-submodules` flag with git commands when working with submodules**
- **Each submodule is a separate Git repository with its own history**
- **Be careful with `git submodule update` as it can put submodules in detached HEAD state**
- **Use `git submodule update --remote` to update to latest commits on tracked branch**
