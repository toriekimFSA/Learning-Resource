# Common Git Commands and Workflows

**Version Control** is a system that records changes to a file or a set of files over time so that you can recall specific versions later. For devs, this is a valuable and powerful tool!

**_Note_**: Replace where there are angle brackets (`<content>`) in code examples with your value.

## Basic Commands

- Configuration to set global username and email for Git (locally):

  ```
  git config --global user.name "<your_username>"
  git config --global user.email "<your_email>"
  ```

- Initialize an empty Git repository in your current directory:

  ```
  git init
  ```

- A way to check if git has been initialized in a project:

  ```shell
  ls -a  # List all files, including hidden
  # If .git is listed, this is already a git repo
  ```

- To log git commit history:

  ```
  git log
  ```

- To check the status of your Git repository:

  ```
  git status
  ```

- Clone an existing Git repository into your current directory:

  ```
  git clone <repo_url>
  ```

## Creating a repository

- First, create a new (remote) repository on Github without any files. This will be where you'll be "pushing" and "pulling" from. Then...

### Create a new (local) repository on the command line

- If you haven't already, open the terminal to create a new directory/folder to hold your project files and `cd` into it:

  ```shell
  mkdir <project_name>
  cd <project_name>
  ```

- Then, do the following:

  ```shell
  echo "# <project_name>" >> README.md # Create a README file with the project name as Heading 1
  git init # Initializes git
  git add README.md # Stage the README file
  git commit -m "first commit" # Make the first commit
  git branch -M main # Rename the default branch to "main"
  git remote add origin <github_repo_url> # Add the (remote) Github repo as "origin"
  git push -u origin main # Push local changes to remote Github repo "main" branch
  ```

### ...Or push an existing repository from the command line

- Make sure you are in the correct folder/directory.
  - To check your current directory/location, use the `pwd` command in the terminal.
- Then, do the following:

  ```shell
  git remote add origin <github_repo_url>
  git branch -M main
  git push -u origin main
  ```

## Branches

- List all branches in your working directory:

  ```
  git branch
  ```

- Switch to another branch:

  ```
  git checkout <branch_name>
  ```

- Create a new local branch & switch to it:

  ```
  git checkout -b <branch_name>
  ```

- Push local branch to remote\*:

  ```
  git push -u origin <branch_name>
  ```

  \*`-u`= set_upstream

- To update local branches and sync with remote repo:

  ```
  git fetch origin
  ```

- To checkout remote branch:

  ```
  git checkout -b <branch_name> origin/<branch_name>
  ```

- To remove a branch:
  ```
  git branch -d <branch_name>
  ```

## Remote repositories

- To list all linked remote repositories:

  ```
  git remote -v
  ```

- To add a remote origin:

  ```
  git remote add origin <remote_repo_url>
  ```

- To add another remote not origin:

  ```
  git remote add <remote_name> <remote_repo_url>
  ```

- To change a remote's URL:

  ```
  git remote set-url <remote_name> <new_remote_url>
  ```

- To remove a remote repository:
  ```
  git remote rm <remote_name>
  ```

## Basic workflow to commit changes

- First, add changed or new/untracked files to stage:

  ```shell
  git add <filename>  # Individual files
  git add .  # All files
  ```

- Then, commit all the staged files:

  ```shell
  git commit -m "<your_commit_messsage>"
  ```

- If pushing changes to a remote repository, also do:

  ```shell
  git push origin main  # Push to remote `origin` on its `main` branch
  git push <remote_name> <branch_name>  # Or to a different remote
  ```

## Workflow tips

### When working on `main`

- Before commiting, **always pull**!

  - This way, your collaborators can merge using fast-forward

  ```
  git pull origin main
  ```

- If you commit your changes before you pull, git will merge the 2 main branches (remote & local) using the recursive strategy

### When working on your own branch

- If you need to put your branch up to date with the `main` branch, you can:

  ```
  git rebase main
  ```

- This will add all commits from `main` to your branch before the commits in your branch

## Other Resources

- [Git Docs](https://git-scm.com/docs) - The source — barebone tech docs!
- [Github Docs](https://docs.github.com/en/get-started/start-your-journey/about-github-and-git) - Very thorough and easy to follow
- [Git Cheat Sheet w/ links to Github docs](https://gist.github.com/dbarowy/dd84c4f9f5314da7ab7ddad73f51ba4f) - For those who like to gain a deeper understanding
- [Git Commands](https://gist.github.com/vimal-verma/6fe59f3b7f886d2210bca28634b3a7fe) - Descriptions and commands listed neatly in tables
