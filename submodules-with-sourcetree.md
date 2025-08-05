# Git Submodule Management with SourceTree

## Initial Setup
When cloning this repository for the first time in SourceTree:

1. **Clone with Submodules:**
   - In SourceTree, go to `File` → `Clone/New`
   - Enter the repository URL: `https://github.com/wbw383/test-base-project.git`
   - **Important:** Check the "Recurse submodules" option before cloning
   - Click "Clone"

2. **If already cloned without submodules:**
   - Open the repository in SourceTree
   - Go to `Repository` → `Submodules` → `Update Submodules`
   - Check "Initialize new submodules" and click "OK"

## Working with Submodules in SourceTree

### Viewing Submodules
- Submodules appear in the file tree with a special folder icon
- Double-click a submodule folder to open it as a separate repository
- The main repository shows submodule commit references, not the actual files

### Updating Submodules
1. **Update all submodules to latest:**
   - Go to `Repository` → `Submodules` → `Update Submodules`
   - Select "Update to remote tracking branch"
   - Click "OK"

2. **Update specific submodule:**
   - Right-click on the submodule folder in the file tree
   - Select "Update Submodule"

### Adding New Submodules
1. Go to `Repository` → `Submodules` → `Add Submodule`
2. Enter the repository URL
3. Choose the local path (folder name)
4. Click "Add Submodule"

### Committing Submodule Changes
1. **First, commit changes in the submodule:**
   - Double-click the submodule to open it
   - Make your changes and commit them
   - Push the submodule changes

2. **Then, commit the submodule reference in the parent:**
   - Return to the parent repository
   - You'll see the submodule listed as modified
   - Stage and commit the submodule reference update

### Important Notes for SourceTree Users
- Always commit and push submodule changes before committing the parent repository
- Use "Pull with rebase" to avoid merge commits when pulling submodule updates
- The parent repository only tracks specific commit references, not branches
- When switching branches, submodules may need manual updating
