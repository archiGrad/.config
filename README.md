# .config
archigrad config files for zsh, tmux, i3, vim, qutebrowser
this has been tested on OS: Ubuntu 22.04.2 LTS x86_64 


## i3
A tiling window manager for Linux.
<details>
<summary> i3 config file </summary>
location: ~/.config/i3/config
<br>
change: mostly color and theme adjustments 
<br>
most used shortcuts:
alt + [1,2,3,..] --> change workspace

<br>
workspace proposal: 
1 = tmux with vim
2 = qutebrowser
3 = ...

<br>
alt-d --> dmenu. used for commands, programs etc

<br>
alt + hjkl --> switch active pane

<br>
alt + shift +hjkl --> move active pane

<br>
alt + shift +q  --> kill active pane

<br>
alt + shift + [1,2,3,..] --> move active pane to different workspace

<br>

</details>




## Qutebrowser
A keyboard-driven web browser based on Python and Qt.

<details>
<summary> qutebrowser config file </summary>
location: ~/.config/qutebrowser/config.py
<br>
change:  theme, shortcuts, startup file
<br>
most used shortcuts:
shift+[j,k] --> shift tabs
<br>
j, k --> scroll down/up
<br>
shift h,l --> go back and forth in history
<br>
f --> got to location
<br>
</details>


## Tmux
A terminal multiplexer that enables multiple sessions in a single terminal window.

<details>
<summary> tmux config file </summary>
location: ~/.config/tmux/tmux.config
<br>
change: mostly color and theme adjusmtnes, setup vim keybingings in naviugation, resizing
<br>
most used shortcuts:
move from 1 pane to the other Ctrl-s hjkl 
<br>
resize panes Ctrl-s Ctrl hjkl
<br>
make new panes Ctrl-s % and Ctrl-s "
<br>
make pane fullscreen Ctrl-s z
<br>
<br>

the following shortcuts functions are defined in ~/.zshrc but are affected by tmux

<br>
<br>
tmux switch sessions -> Ctrl-s s jk
<br>
tmux new-session -s "my_session " -> tmux n "my_session"
<br>
tmux detach -> tmux d
<br>
tmux attach-session -t "my_session" -> tmux a "my_session"
<br>
tmux kill-session -t "my_sessioin" -> tmux k "my_session"
<br>
tmux list-session -> tmux ls
<br>

</details>



## Vim
A highly configurable text editor known for its efficiency and extensive plugin ecosystem.



<details>
<summary> vim config file </summary>
location: ~/.config/.vimrc
<br>
change: tabs, color
<br>
most used shortcuts:
all shortcuts
<br>

</details>




## Zsh
A powerful shell with advanced scripting capabilities, often used as an alternative to Bash



<details>
<summary> zsh config file </summary>
location: ~/.zshrc
theme_location: ~/.oh-my-zsh/.themes/alanpeabody.zsh-theme
<br>
change: theme, pio integration, houdini alias, tmux integration
<br>

aliases:

<br>
#houdini alias
houdini(){
│       local current_dir=$(pwd)
│       cd /opt/hfs19.5
│       source houdini_setup
│       cd "$current_dir"
│       happrentice "$1"
}


#Begin: tmux alias
#tmux new-session -s "my_session " -> tmux n "my_session"
#tmux detach -> tmux d
#tmux attach-session -t "my_session" -> tmux a "my_session"
#tmux kill-session -t "my_sessioin" -> tmux k "my_session"
#tmux list-session -> tmux ls

tmux() {
    local arg1=""
    local arg2=""
    local arg3=""

    if [ "$1" = "n" ]; then
        arg1="new-session"
        arg2="$2"
        arg3="-s"
    fi

    if [ "$1" = "d" ]; then
        arg1="detach"
    fi

    if [ "$1" = "k" ]; then
        arg1="kill-session"
        arg2="$2"
        arg3="-t"
    fi

    if [ "$1" = "a" ]; then
        arg1="attach-session"
        arg2="$2"
        arg3="-t"
    fi

    if [ -n "$arg1" ]; then
        if [ -n "$arg2" ] && [ -n "$arg3" ]; then
            command tmux "$arg1" "$arg3" "$arg2"
        elif [ -n "$arg2" ]; then
            command tmux "$arg1" "$arg2"
        else
            command tmux "$arg1"
        fi
    else
        command tmux "$@"
    fi
}


##pio
platformio integration with zsh can also be found in the .zshrc file 

#### Begin: PlatformIO Core completion support
eval "$(_PIO_COMPLETE=zsh_source pio)"
#### End: PlatformIO Core completion support



</details>






# Basic Configuration Files

This repository contains configuration files for various tools and applications.

## i3
A tiling window manager for Linux.

<details>
<summary>i3 config file</summary>

**Location:** ~/.config/i3/config

**Changes:** Mostly color and theme adjustments.

**Most Used Shortcuts:**
- Alt + [1,2,3,...] : Change workspace
- Alt + d : dmenu (used for commands, programs, etc)
- Alt + hjkl : Switch active pane
- Alt + shift + hjkl : Move active pane
- Alt + shift + q : Kill active pane
- Alt + shift + [1,2,3,...] : Move active pane to different workspace

</details>

## Qutebrowser
A keyboard-driven web browser based on Python and Qt.

<details>
<summary>qutebrowser config file</summary>

**Location:** ~/.config/qutebrowser/config.py

**Changes:** Theme, shortcuts, startup file.

**Most Used Shortcuts:**
- Shift + [j,k] : Shift tabs
- j, k : Scroll down/up
- Shift + h,l : Go back and forth in history
- f : Go to location

</details>

## Tmux
A terminal multiplexer that enables multiple sessions in a single terminal window.

<details>
<summary>tmux config file</summary>

**Location:** ~/.config/tmux/tmux.config

**Changes:** Mostly color and theme adjustments, setup Vim keybindings in navigation, resizing.

**Most Used Shortcuts:**
- Move from one pane to another: Ctrl-s hjkl
- Resize panes: Ctrl-s Ctrl hjkl
- Create new panes: Ctrl-s % and Ctrl-s "
- Make pane fullscreen: Ctrl-s z

**Additional Functions:**
- Tmux switch sessions: Ctrl-s s jk
- Tmux new-session -s "my_session ": tmux n "my_session"
- Tmux detach: tmux d
- Tmux attach-session -t "my_session": tmux a "my_session"
- Tmux kill-session -t "my_session": tmux k "my_session"
- Tmux list-session: tmux ls

</details>

## Vim
A highly configurable text editor known for its efficiency and extensive plugin ecosystem.

<details>
<summary>vim config file</summary>

**Location:** ~/.config/.vimrc

**Changes:** Tabs, color.

**Most Used Shortcuts:**
- All shortcuts

</details>

## Zsh
A powerful shell with advanced scripting capabilities, often used as an alternative to Bash.

<details>
<summary>zsh config file</summary>

**Location:** ~/.zshrc

**Theme Location:** ~/.oh-my-zsh/.themes/alanpeabody.zsh-theme

**Changes:** Theme, PIO integration, Houdini alias, Tmux integration.

**Aliases:**
```zsh
# Houdini alias
houdini(){
    local current_dir=$(pwd)
    cd /opt/hfs19.5
    source houdini_setup
    cd "$current_dir"
    happrentice "$1"
}

# Tmux alias
tmux() {
    local arg1=""
    local arg2=""
    local arg3=""

    if [ "$1" = "n" ]; then
        arg1="new-session"
        arg2="$2"
        arg3="-s"
    fi

    if [ "$1" = "d" ]; then
        arg1="detach"
    fi

    if [ "$1" = "k" ]; then
        arg1="kill-session"
        arg2="$2"
        arg3="-t"
    fi

    if [ "$1" = "a" ]; then
        arg1="attach-session"
        arg2="$2"
        arg3="-t"
    fi

    if [ -n "$arg1" ]; then
        if [ -n "$arg2" ] && [ -n "$arg3" ]; then
            command tmux "$arg1" "$arg3" "$arg2"
        elif [ -n "$arg2" ]; then
            command tmux "$arg1" "$arg2"
        else
            command tmux "$arg1"
        fi
    else
        command tmux "$@"
    fi
}

# PlatformIO integration
eval "$(_PIO_COMPLETE=zsh_source pio)"




