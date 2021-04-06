# Github Tutorial
Tutorial for github

### How Upload project to github V1
1. git init
2. git add *
3. git status
4. git commit -m "Commit Pertama"
5. git remote add origin https://github.com/Aguzrybudy/GithubTutorial.git
6. git push origin master kalau error git pull --rebase kemudian git push origin master
7. masukkan username & password Github
8. selesai

### How Upload project to github V2
1. Create new respository in github
2. git init in your folder
3. git pull https://github.com/Aguzrybudy/GithubTutorial.git <branch_name>
4. git status
5. git add *
6. git commit -m "Keterangan Commit"
7. git remote add origin https://github.com/Aguzrybudy/GithubTutorial.git
8. git push origin <branch_name>
9. Done

### How to add/change username & email
1. git config --global user.name "John Doe" //setting username
2. git config --global user.email johndoe@example.com //settting email
3. git config --list //untuk mendapatkan list akun
4. git config user.name //untuk mendapatkan username

### How to change account github in windows
1. Open Control Panel from the Start menu
2. Select User Accounts
3. Select "Manage your credentials" in the left hand menu
4. Delete any credentials related to Git or GitHub
5. Done

### How to handle error  refusing to merge unrelated histories
1. git pull origin master --allow-unrelated-histories

### Another Function
1. git pull --ff-only

### How to handle error Updates were rejected because the tip of your current branch is behind
1. git pull https://github.com/Aguzrybudy/GithubTutorial.git master
2. git pull origin master --allow-unrelated-histories
3. git push origin master

### How to abort merge
1. git merge --abort
2. git pull (to be sure you're up-to-date)
3. git add README.md
4. git commit -m "comment"
5. git push

### How to add new branch
1. Create branch for github website in respository
2. git branch -a // to get listh branch
3. git branch development // to get new brand created
4. git checkout <branch name> // to switch brand
  
### How to delete file from commit
1. git reset --soft HEAD^ or git reset --soft HEAD~1
2. git reset HEAD path/to/unwanted_file
3. git commit -c ORIG_HEAD

### How to delete the file from your local and the remote repository, you can
1. git rm path/to/unwanted_file
2. git commit --amend
3. git rm --cached path/to/unwanted_file


### How to remove deleted files from showing up in my local git status
1. git add -u .
2. git commit -m "removing deleted files from tracking"
3. git push origin master (ignore when error)
4. git status

### How to Remove a directory from Git Repository
1. git rm -r name_directory
2. git commit -m "Removed name_directory directory"
3. git push origin master   
4. git status

### How to change the URI (URL) for a remote Git repository
1. git remote -v (View existing remotes)
2. git remote set-url origin https://github.com/Aguzrybudy/GithubTutorial.git (Change the 'origin' remote's URL)
3. git remote -v (Verify new remote URL)

### How to Clone a GitHub Repository
1. git clone <repo-url> example (https://github.com/Aguzrybudy/GithubTutorial.git)
