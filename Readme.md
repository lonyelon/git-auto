# git-auto

A Simple Shell Script To Commit And Push Automatically


## Usage

Download the `git-auto` file

```sh
$ chmod +x git-auto
./git-auto
```

```sh
# Auto run on opening logseq on linux
# Modify logseq desktop entry, e.g in /usr/share/applications/logseq-desktop.desktop
Exec=/bin/sh -c "/path/to/git-auto -d /path/to/logseq -pr & bg=$!; logseq; kill $bg"
```

Default behaviour:
- The script will exit if there is already another instance is running, use `-a` to bypass this.
- If it is interrupted before the next commit/push interval, the current changes will not be committed/pushed. Use `-e` to always make a final commit/push upon exit.

More samples:

```
##  git-auto ;; use current script dir as git dir, and auto commit, not push.
##  git-auto -d /path/to/your/note's/dir   ;; set git dir
##  git-auto -i 30 -p ;; set interval seconds
##  git-auto -m "Commit from desktop" ;; set commit message for all commits
##  git-auto -b main -p ;; set git branch
##  git-auto -s origin -p ;; set remote server
##  git-auto -p ;; auto commit and push
##  git-auto -r ;; auto commit, rebase, merge, push
##  git-auto -o -p;; execute once
```

## For Windows Users

Before you proceed to use the `git-auto` file, please make sure Git installed, otherwise please download [Git](https://github.com/git-for-windows/git/releases/download/v2.30.1.windows.1/Git-2.30.1-64-bit.exe) and install it.

1. Just click 'yes' all the way down and you will find `Git Bash` icon in the `start`.

2. Open `PowerShell`

Download the target repository if you don't have it locally yet:

```
git clone [your_repo_url]
cd [your_repo_location]
```

For those who don't yet have a repository on Github, please refer to https://docs.github.com/en/github/getting-started-with-github/create-a-repo.

3. Usage

Download the `Start-GitAutoCommit.ps1` file, and run

```powershell
.\Start-GitAutoCommit.ps1
```

More samples:

```
Start-GitAutoCommit # use current script dir as git dir, and auto commit, not push.
Start-GitAutoCommit -d /path/to/your/note's/dir   # set git dir
Start-GitAutoCommit -p # auto commit and push
Start-GitAutoCommit -s origin -p # set remote server
Start-GitAutoCommit -b main -p # set git branch
Start-GitAutoCommit -i 30 -p # set interval seconds
Start-GitAutoCommit -o -p # execute once
```

## Contributors

Thanks for your work!

PowerShell Port, by [@batkiz](https://github.com/batkiz)

[Readme-CN.md](https://github.com/defclass/git-auto/blob/master/Readme-CN.md) & Git Bash docs, by [@zhanghanduo](https://github.com/zhanghanduo)

## License

Copyright © 2020 Michael Wong

Distributed under the MIT License.
