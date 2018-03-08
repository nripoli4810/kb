# Git Tips

A collection of various git tips and tricks.

## Learning Git

Start with this website / game. It will introduce you to git.

https://learngitbranching.js.org

And then use the following for more information:

https://try.github.io/levels/1/challenges/1
https://about.gitlab.com/2015/02/19/8-tips-to-help-you-work-better-with-git/

## Git Clients

Windows:

| GUI Clients | Bash Clients | Diff Tools |
| :---: | :---: | :---: |
| Sourcetree | GitBash for Windows | BeyoundCompare (Licensed!)|
| GitKraken (Licensed!) | | |

Mac:

| GUI Clients | Bash Clients | Diff Tools |
| :---: | :---: | :---: |
| Sourcetree for Mac | Terminal | BeyoundCompare (Licensed!) |
| Gitkraken (Licensed!) | iTerm+ZSH | Xcode FileMerge |

## Aliases

I have a list of general shortcuts that I use every day. Feel free to pick and choose which ones you want. To add these to your terminal, find your profile and add the alias/command as such: `alias key="command to run"`

On Windows and Mac, you find these profile files in your home directory:

* Bash: `.bash_profile`
* zsh: `.zshrc`

Here is a [link to all of my shortcuts](https://github.com/nripoli4810/bashconfig)

Here are several of my favorites:

### Pretty Git Log

The `git log` command is only somewhat useful. Here are two additional log graph aliases that will help you understand the state of your local repository.

### lg1

This log graph command shows you your commit graph with the hash, date, and author, as well as all branches.

`alias lg1="git log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"`

### lg2

This log graph command does the same as the above log command, but separates the commit message and author by putting them on their own line.

`alias lg2="git log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all"`

----

## Tips & Tricks

Feel free to open a PR with suggestions for tips!

### Change the author of the last commit

Run: `git commit --amend --reset-author`

This will bring up a vim session and allow you to change the commit text if you want. When you're ready, quit vim (`:wq`) and force push your branch.

### Show only the files changed

Run: `git status -s`

This will show you a list of the files changed. (Hint: alias to `gss`)
