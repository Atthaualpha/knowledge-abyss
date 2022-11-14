# Customization

*[:arrow_left: Go back to Git](./GIT.md)*

Git has many customization settings to play around, to check which are available please refer to [git config documentation](https://git-scm.com/docs/git-config)

## Prompt style on windows.

To configure git in windows and if you are using a bash as your terminal configuration, follow the next steps:

1. Open .git-prompt.sh that is in your git installation folder, in your program-files folder. Then in etc/profile.d folder
2. Modify the git-prompt-sh file where you see some likely configuration as below.

```
if test -f ~/.config/git/git-prompt.sh
then
        . ~/.config/git/git-prompt.sh
else
        PS1='\[\033]0;Console:$PWD\007\]' # set window title
        PS1="$PS1"'\n'                 # new line
        PS1="$PS1"'\[\033[32m\]'       # change to green
        PS1="$PS1"'Attha '             # user@host<space>
        PS1="$PS1"'\[\033[35m\]'       # change to purple
        PS1="$PS1"'□^y□ '          # show MSYSTEM
        PS1="$PS1"'\[\033[33m\]'       # change to brownish yellow
        PS1="$PS1"'\w'                 # current working directory

```

## Dirty git state on windows.

If you want that git mark you current branch with the changes that are at any state, you can activate this by just adding the following line to your .bashrc file (Normally located at in your home folder): 

`export GIT_PS1_SHOWDIRTYSTATE=1`

## Prompt style on debian.

If you have debian OS installed, you can follow this instructions: [Basic Prompt Style](https://github.com/Atthaualpha/wiki-tools/blob/main/debian_tools/BASIC_PROMT_STYLE.md)

