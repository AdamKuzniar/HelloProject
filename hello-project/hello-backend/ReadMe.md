# To Do
## Short Term
- [x] Create GitHub Repo
- [x] Move local work to GitHub to unlock tracking changes and get experience with Git
- [x] Get back to GoLang Docs and find requirements for local work in containers
  - Go is needed and included in my base docker file golang:alpine
- [x] Organize local setup
  - [] Check if current setup makes it easy to commmit to GitHub
## Long Term 
- [x] Decide if work on 
  - [ ] Windows + Desktop stack 
  - [x] WSL2 + CLI stack  

# How to tips
1. Use WSL for container management
2. rundocker.sh is a simple shell script/command that allows to run contaniner in interactive mode.
 - my issues were with lack of naming docker container at the end
## GitHub Tips
### Cloning repository  
**Assumptions:** Work on Windows Desktop and use WSL for more smooth container management  
**Prerequisites:** Installed WSL, Created GitHub account, Existing repository  
- Launch WSL and update your WSL system 
  - `sudo apt update && upgrade`
- do basic GitHub setup (set your name and email)
  ```
  git config --global user.name "Your Name"
  git config --global user.email "yourEmail"
  ```
- create SSH Key
  - `ssh-keygen -t ed25519 -C yourEmail"`
- copy contents of SSH public key (its default key directory and name, might need adjustments)
  - `cat ~/.ssh/id_ed25519.pub`

### Commiting code in "dirty way" - directly to main branch  
**Assumptions:** sufficient privelages to the repository  
**Prerequisites:** valid SSH authenthication to repository, changes in files  
- add your changes to "local staging" and commit changes locally  
  ```
  git add .
  git commit -m "description of changes
  ``` 
- push changes to GitHub - main is the default branch name
  - `git push origin main`
### Commiting code in "cleaner way" - directly to main branch  
**Assumptions:** sufficient privelages to the repository  
**Prerequisites:** valid SSH authenthication to repository, changes in files  
- create new branch and switch to it
  ```
  git branch branch-name
  git checkout branch-name
  ``` 
- add your changes to "local staging" and commit changes locally  
  ```
  git add .
  git commit -m "description of changes
  ``` 
- push changes to GitHub 
  - `git push origin branch-name`
- Use UI on GitHub to Create Pull Request, select your new branch
- Merge PR after it's created  

## Docker
### Installing docker on WSL
1. Install docker engine 
`sudo apt-get install -y docker.io`
2. Install buildx, create catalog for plugins and download proper binary
```
mkdir -p ~/.docker/cli-plugins 
curl -SL https://github.com/docker/buildx/releases/latest/download/buildx-v0.18.0.linux-amd64 -o ~/.docker/cli-plugins/docker-buildx
```
3. Turn on BuildKit (not sure if necessary) by setting environment variable
` export DOCKER_BUILDKIT=1`

### Command to run containers with mounted volumes  
`docker run -v hostpath:containerpath -it container-name`


