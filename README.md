# Lab 2: Git Branching, Merging, and Tagging

This README documents the requirements and step-by-step solutions for Lab 2.

## Part 1: Repository & Branching

### 1. Create a new project on your local machine, then push it to your remote repo
```cmd
# Create a new directory and move into it
mkdir iti-git-lab2
cd iti-git-lab2

# Initialize local repository
git init

# Create a README file and make the first commit
echo > README.md
git add README.md
git commit -m "Initial commit"

# Link to the remote repository and push
git remote add origin git@github.com:OmarAlaaEl-Din/iti-git-lab2.git
git branch -M main
git push -u origin main
```

### 2. Create two branches (dev & test), create one file on each, and push
```cmd
# Create and switch to the 'dev' branch
git checkout -b dev
echo > dev_file.txt
git add dev_file.txt
git commit -m "Add dev file"
git push -u origin dev

# Switch back to main, then create and switch to 'test'
git checkout main
git checkout -b test
echo > test_file.txt
git add test_file.txt
git commit -m "Add test file"
git push -u origin test
```

### 3. Merge these changes on Main branch and push to remote
```cmd
# Switch to main
git checkout main

# Merge the branches
git merge dev
git merge test

# Push the merged main branch to the remote repository
git push origin main
```

### 4. Remove the branches locally and remotely
```cmd
# Delete branches locally
git branch -d dev
git branch -d test

# Delete branches remotely
git push origin --delete dev
git push origin --delete test
```

### 5. Checkout another branch without committing changes
To safely switch branches without losing uncommitted work, use git stash to temporarily shelf your changes.
```cmd
# Shelf uncommitted changes
git stash

# Safely switch branches
git checkout <another-branch-name>

# (To restore the changes later, return to the branch and run: git stash pop)
```

## Part 2: Tagging & Documentation

### 1. Create an annotated tag with tagname (v1.7)
```cmd
git tag -a v1.7 -m "Release version 1.7"
```

### 2. Push the tag to the remote repository
```cmd
git push origin v1.7
```

### 3. List tags
```cmd
git tag
```

### 4. Delete tag locally and remotely
```cmd
# Delete locally
git tag -d v1.7

# Delete remotely
git push origin --delete v1.7
```

### 5. Add an image in the README.md file
Below is an example of an image added to this README file:
![Cat](image_1.jfif)
