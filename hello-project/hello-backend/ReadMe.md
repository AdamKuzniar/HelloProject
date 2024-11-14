# To Do
## Short Term
- [x] Create GitHub Repo
- [x] Move local work to GitHub to unlock tracking changes and get experience with Git
- [ ] Get back to GoLang Docs and find requirements for local work in containers
- [ ] Organize local setup
  - [ ] Check if current setup makes it easy to commmit to GitHub
## Long Term 
- [ ] Decide if work on 
  - [ ] Windows + Desktop stack 
  - [ ] WSL2 + CLI stack  

# How to tips
1. Use WSL for container management
2. rundocker.sh is a simple shell script/command that allows to run contaniner in interactive mode.
 - my issues were with lack of naming docker container at the end
## GitHub Tips
1. Cloning repository  
**Assumptions:** Work on Windows Desktop and use WSL for more smooth container management  
**Prerequisites:** Installed WSL, Created GitHub account, Existing repository  
- Launch WSL and update your WSL system 
  - `sudo apt update && upgrade`
- do basic GitHub setup (set your name and email)
  - `git config --global user.name "Your Name"`
  - `git config --global user.email "yourEmail"`
- create SSH Key
  - `ssh-keygen -t ed25519 -C yourEmail"`
- copy contents of SSH public key (its default key directory and name, might need adjustments)
  - `cat ~/.ssh/id_ed25519.pub`

2. Commiting code in dirty way  
**Assumptions:** sufficient privelages to the repository  
**Prerequisites:** valid SSH authenthication to repository, changes in files  
- add your changes to "local staging" 
  - `git add .`
- commit changes
  - `git commit -m "description of changes"`
- push changes 
  - `git push origin main`
