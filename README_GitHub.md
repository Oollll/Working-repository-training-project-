# Git 

## Requirements
If you want to create pull requests through the terminal instead of the GUI, I recommend running the following commands :

### Step 1: Install the GitHub CLI

#### For Windows:
```
winget install --id GitHub.cli
```
#### For MacOS:
```
brew install gh
```
### Step 2: Log in to GitHub
```
gh auth login
```

# Tasks: 
#### 1. Create your own repository with a filled file(s).
  - Push your repository to GitHub.

##### Go to GitHub, click on the + icon, and select New repository.
##### Fill in the repository details (name, description, public/private).
##### Click Create repository.
```
git clone "URL"
cd "your repository"
echo "massages" > test.txt
git push
```
#### 2. Create a master branch and protect it.
```
git checout -b master
```
##### Go to your repository 
##### Settings 
##### Branches
##### Add branch ruleset
##### Add target 
- Select "Include by pattern"
- Write the name of the branch 
- Add inclusion pattern 
##### Rules 
- Require a pull request before merging
##### Create 

- Create your work branch. 
```
git checkout -b work
```
- Add any files and edit some records in existing files. 
```
echo "Hello" > test.txt
git add README.md
git commit -m "Update README.md (Linux tasks)"
git add test.txt
git commit -m "Created a new test file"
```

#### 3. Add your changes from the work branch to the master branch. 
```
git checkout master
git pull origin master
git merge work
git push origin master
```
- (Make a merge-request/pull-request from your branch and close it after Denis Tuzhilin approve. Cope with conflicts if there are.) (Don't forgot to answer conversations)

```
gh pr create --base master --head work --title "work -> master" --body "I've made changes to the file in the work branch and pushed these changes to the master branch"
```

#### 4. Back repository to someone's old commit.
```
git log 
git reset --hard "hashcommit"
git push origin main
```
