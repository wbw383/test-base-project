# Git Submodule Management with GitKraken

## Initial Setup
When cloning this repository for the first time in GitKraken:

1. **Clone with Submodules:**
   - In GitKraken, click the folder icon in the top toolbar
   - Select "Clone"
   - Enter the repository URL: `https://github.com/wbw383/test-base-project.git`
   - Choose your local destination folder
   - **Important:** Check the "Recurse Submodules" checkbox before cloning
   - Click "Clone the repo!"

2. **If already cloned without submodules:**
   - Open the repository in GitKraken
   - Go to the left sidebar and look for the "Submodules" section
   - Right-click in the Submodules area and select "Initialize Submodules"
   - Or use the command palette (Ctrl+Shift+P) and search for "Initialize Submodules"

## Working with Submodules in GitKraken

### Viewing Submodules
- Submodules appear in the left sidebar under the "Submodules" section
- Each submodule shows its current commit hash and status
- Click on a submodule name to view its commit history in the main graph
- The file tree shows submodule folders with a special icon

### Updating Submodules
1. **Update all submodules to latest:**
   - Right-click in the "Submodules" section of the left sidebar
   - Select "Update All Submodules"
   - Choose "Update to remote HEAD" to get the latest commits

2. **Update specific submodule:**
   - Right-click on the specific submodule in the sidebar
   - Select "Update Submodule"
   - Choose the update option (typically "Update to remote HEAD")

3. **Pull submodules with parent repository:**
   - When pulling changes, GitKraken will show if submodules need updating
   - You can choose to update submodules during the pull operation

### Adding New Submodules
1. Right-click in the "Submodules" section of the left sidebar
2. Select "Add Submodule"
3. Enter the repository URL
4. Choose the local path (folder name)
5. Select the branch to track (usually "main" or "master")
6. Click "Add Submodule"

### Committing Submodule Changes
1. **First, commit changes in the submodule:**
   - Click on the submodule in the sidebar to view its repository
   - GitKraken will show you're now in the submodule context
   - Make your changes and commit them as usual
   - Push the submodule changes to its remote

2. **Then, commit the submodule reference in the parent:**
   - Navigate back to the parent repository (use the repository switcher)
   - You'll see the submodule listed as modified in the staging area
   - Stage and commit the submodule reference update
   - The commit message will show the new submodule commit hash

### Managing Submodule Branches
- GitKraken shows which branch each submodule is on
- You can switch submodule branches by:
  1. Clicking on the submodule to enter its context
  2. Using the branch selector to switch branches
  3. Remember to commit the branch change in the parent repository

### Removing Submodules
1. Right-click on the submodule in the sidebar
2. Select "Remove Submodule"
3. Confirm the removal
4. Commit the changes to complete the removal

### Important Notes for GitKraken Users
- GitKraken provides visual indicators when submodules are out of sync
- The commit graph clearly shows submodule commit relationships
- Always commit and push submodule changes before committing the parent repository
- Use the repository switcher to navigate between parent and submodule repositories
- GitKraken's merge conflict resolution works within submodules as well
- The "Submodules" panel provides a quick overview of all submodule statuses
