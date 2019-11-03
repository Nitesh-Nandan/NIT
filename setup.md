# Setup Configuration

## Setting up bashrc 

```sh

 PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u\[\033[00m\]:\[\033[01;34m\]\W\[\033[00m\]\$ '

## Custom Commands

# Nodejs
PATH="$HOME/local/lib/nodejs/bin:$PATH"

# Sublime
PATH="$HOME/local/lib/sublime3/:$PATH"

#postman
PATH="$HOME/local/lib/Postman/:$PATH"

#GO
PATH="$HOME/local/lib/go/bin/:$PATH"

#EalsticSearch
PATH="$HOME/local/lib/elasticsearch/bin/:$PATH"


#alias
alias alba="cd ~/workspace/albanero"
alias nn="cd ~/workspace/nitesh"
alias del="rm -rf"
alias graph='git log --oneline --all --decorate --graph'
alias home='cd'
alias last_commit='git log -n 1  --pretty=format:"commitedBy: %Cred%an, %Cgreen%s, %Cblue%cd"'
alias copy='cp -v -R'
alias move='mv -f -v'
alias commands='cat ~/Public/commands.json'
alias ecommands='subl ~/Public/commands.json'
alias postman='nohup postman >/dev/null 2>&1 & disown'
alias run='sh $HOME/local/lib/myScripts/runc++.sh'
alias gd='cd ~/Desktop'
alias robo='$HOME/local/lib/robo3t/bin/robo3t >/dev/null 2>&1 & disown'
alias eclipse='$HOME/local/lib/eclipse/eclipse >/dev/null 2>&1 & disown'
```

## Defining folder and File

- Home -> local -> lib
- Packages:- 
  - eclipse,
  - Postman,
  - elasticsearch,
  - NODEJS

## CommandLine Installation

1. Git
```sh
$ sudo apt-get install git
```

2. Formatting top time format
```sh
$ gsettings set org.gnome.desktop.interface clock-show-date true
```

3. Installing Terminator
```sh
$ sudo add-apt-repository ppa:gnome-terminator
$ sudo apt-get update
$ sudo apt-get install terminator
```

## vscode setup

- Download vscode from official website (.deb)
- Extensions to be installed:
   - C/C++ Microsoft
   - Cobalt2 Theme official
   - Debugger for chrome
   - Eclipse key map (Alphabot security)
   - ES7 React/Redux/ GraphQl
   - ESLint
   - Git lens
   - Live server (Ritwick Dey)
   - Markdown Pdf (yzane)
   - Github plus theme
   - Material Icon Theme
   - Noctis
   - Winter is coming Theme (John Papa)

### Keyboard shortcut
```json
// Place your key bindings in this file to override the defaultsauto[]
[
    {
        "key": "ctrl+m",
        "command": "editor.action.toggleMinimap"
    },
    {
        "key": "ctrl+shift+a",
        "command": "workbench.action.toggleActivityBarVisibility"
    },
    {
        "key": "shift+enter",
        "command": "workbench.action.selectTheme"
    },
    {
        "key": "ctrl+k ctrl+t",
        "command": "-workbench.action.selectTheme"
    },
    {
        "key": "ctrl+u",
        "command": "editor.action.addSelectionToNextFindMatch",
        "when": "editorFocus"
    },
    {
        "key": "ctrl+d",
        "command": "-editor.action.addSelectionToNextFindMatch",
        "when": "editorFocus"
    }
]
```

###  Settings
```json
{
    "emmet.includeLanguages": {
        "javascript": "javascriptreact"
    },
    "emmet.triggerExpansionOnTab": true,
    "editor.minimap.enabled": false,
    "workbench.colorTheme": "Noctis Obscuro",
    "workbench.iconTheme": "material-icon-theme",
    "workbench.activityBar.visible": true,
    "files.autoSave": "onFocusChange",
    "editor.formatOnSave": true,
    "terminal.integrated.cursorStyle": "line",
    "window.zoomLevel": 0,
    "diffEditor.ignoreTrimWhitespace": true,
    "[cpp]": {
        "editor.formatOnSave": false
    },
    "C_Cpp.clang_format_style": "",
    "diffEditor.renderSideBySide": true
}
```

## Setting up Node js Debugger

```json
"configurations": [
        {
            "type": "node",
            "request": "attach",
            "name": "Nodemon Debug",
            "port": 9229,
            "restart": true
        },
        {
            "type": "node",
            "request": "launch",
            "name": "Application Debug",
            "program": "${workspaceFolder}\\app.js",
            "serverReadyAction": {
                "pattern": "Server is up on port ([0-9]+)",
                "uriFormat": "http://localhost:%s",
                "action": "openExternally"
            }
        }
    ]
```


## C++ compile and Run Script
```sh
#!/bin/sh
inp=$1
run(){
    rm -rf a.out
    g++ $inp
    ./a.out
    echo
}
run
```

## Setting up github using ssh key

```sh
$ ssh-keygen
```

## Installing Mongodb

- link:  https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/

### Shell Commands
```sh
$ wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | sudo apt-key add -

$ sudo apt-get install gnupg

$ wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | sudo apt-key add -

$ echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.2.list


$ sudo apt-get update

$ sudo apt-get install -y mongodb-org
```