VERSION CONTROL:
- allows for the ability to compare files to previous and current versions
- allows for the ability to rollback or forward to any desired version of code

Git && GitHub
1. navigate to desired directory in Git Bash terminal
2. `git init`: initialize local repository
    - Expected Output: Initialized empty Git repository in <directory> ...
    - this is now the working directory
3. Set Repository-Specific Identity
    - To use a specific profile for a local repository if you have multiple GitHub accounts, you must set a local configuration (omit the --global flag)
        - `git config user.name "ExampleUsername"`
        - `git config user.email "email@example.com"`
        - confirm changes by entering the above commands without the quoted details
            - Local settings are stored in `.git/config`
            - Global settings are stored in `~/.gitconfig`
            - Local settings will override global settings for that specific repository
4. Working Directory Workflow:
    - files in the working directory are picked into the Staging Area where we decide which files to commit
    - `git status`: shows all files in the working directory
        - red files appear when they are not in the Staging Area
        - green files appear when they are in the Staging Area
    - `git add <FileName>`: adds file to the Staging Area
    - `git add -A` OR `git add .`: adds all files with changes to the Staging Area
    - `git status`: confirm files to commit
    - `git commit -m"<commit message>"`: commits code in Staging Area to the local repositroy with a meaninful message to describe the changes made
    - `git log`: shows the commit history before pushing to the remote repository in GitHub
    - `git diff <FileName>`: shows the difference between current version and most recent checkpoint of the local repository
    - `git checkout <FileName> OR <BranchName>`: rollsback and checks out the most recent version of that isntance in the local repository

GitHub and Remote Repositories:
1. Navigate to GitHub
2. Click New Repository > Enter Repository Name > Click Create Repository
3. Copy address of a repository > Navigate to Git Bash terminal
4. `git remote add origin <GitHub Repository URL>`: creates an association for our local repository to the remote repository
5. `git push -u <RemoteName> <BranchName>`: pushes local repository changes to the remote repository

MAIN (MASTER) BRANCH: 
- main branch is sequential where main progress is committed and tracked which serves as a checkpoint

GITIGNORE:
- `.gitignore`: define what should not be pushed up to GitHub repositories (security)
    - these files typically include local settings, preferences, API KEYS, configs, etc
- add specific file names with the exact matching casing of the file in the source tree
- Official .gitignore Documentation: 
    - NODE: https://github.com/github/gitignore/blob/main/Node.gitignore
    - PYTHON: https://github.com/github/gitignore/blob/main/Python.gitignore
    - RUST: https://github.com/github/gitignore/blob/main/Rust.gitignore
    - C#: https://github.com/github/gitignore/blob/main/C.gitignore

CLONING: 
- `git clone <URL>`: pull down all files and versions of a particular remote repository and create a local repository into a working directory
- allows us to build on that code, extend its functionality, fix bugs, etc.
- open source: improve your own version, read other's code, contribute to open source code

BRANCHING && MERGING:
- Feature Development with Branches
    1. `git branch <NameOfBranch>`: create branch from current branch for feature/bug
    2. `git checkout <NameOfBranch>`: checkout a created/existing branch
    2. ... code ...
    4. ... commit code ...
    5. ... checkout branch we want to merge into ... 
    6. `git merge <NameofBranch>`: merge branch into our checked out branch

FORKING && PULL REQUESTS:
- Forking:
    1. copying a remote repository so that it can be cloned locally 
    2. ... code ... > push changes to the remote repository that was copied
    3. make a Pull Request to the original source of the copied remote repository
    4. Code gets approved and merged