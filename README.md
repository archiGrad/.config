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














