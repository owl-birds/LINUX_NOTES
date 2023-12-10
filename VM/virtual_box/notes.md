DEBIAN12 ::

- https://www.youtube.com/watch?v=MxIAyAELqu4
- https://forums.virtualbox.org/viewtopic.php?t=106069
- https://www.youtube.com/watch?v=h8opVWdDPXM
- https://linuxhint.com/how-to-fix-debian-sudo-command-not-found/
- https://linuxize.com/post/how-to-list-users-in-linux/
- https://www.youtube.com/watch?v=77-tuFE_pGc // window manager i3 set ups
- https://i3wm.org/docs/userguide.html

# SETTING UP WINDOW MANAGER --- i3wm

## links

1. https://i3wm.org/docs/userguide.html
2. https://wiki.debian.org/GrubTransition
3. https://www.youtube.com/watch?v=77-tuFE_pGc // setting up i3
4. https://itsfoss.com/file-managers-linux/
5. https://wiki.archlinux.org/title/KDE#KF5.2FQt5_applications_don.27t_display_icons_in_i3.2Ffvwm.2Fawesome
6. https://installati.one/install-breeze-icon-theme-ubuntu-20-04/?expand_article=1
7. https://www.vpsserver.com/check-linux-cpu-usage/

### installations

```

```

# FOOTNOTE

```
su - ::: switch user to root
su username

// how to add new user to list of sudoers
1. switch to root
2. update everything first, ; apt-get update
3. then ; usermod -aG sudo username
4. then ; id username ; (to check if the user is added to the list)

// installing oh my zsh
- https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH
- https://github.com/ohmyzsh/ohmyzsh
- https://github.com/powerline/fonts
- https://github.com/ryanoasis/nerd-fonts
- source ~/.zshrc ::: to apply the changes
- https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md

// installing git
- sudo apt install git

// check all user in the linux
1. ; cat /etc/passwd
1. or ; awk -F: '{ print $1}' /etc/passwd
1. or ; cut -d: -f1 /etc/passwd

// installing flatpak
1. sudo apt install flatpak
2. add flatpak repo ?

// installling strings command
1. https://linuxhint.com/strings-ubuntu-command-use/

// installing web browser
1. https://unix.stackexchange.com/questions/32454/is-there-a-way-to-have-a-web-browser-while-no-kde-or-gnome-is-installed
2. lynx text web browser
3. ; sudo apt install firefox xorg (Xorg (commonly referred to as simply X) is the most popular display server among Linux users.)
4  ; startx ; firefox
5. ctrl + q OR type exit ;;; to quit startx

// zsh_history corrupts
https://shapeshed.com/zsh-corrupt-history-file/
1. cd ~
2. mv .zsh_history .zsh_history_bad
3. strings .zsh_history_bad > .zsh_history
4. fc -R .zsh_history
5. rm ~/.zsh_history_bad

// changing cursor (shape, color, etc)
1. https://www.baeldung.com/linux/console-cursor-features
2. https://linuxgazette.net/137/anonymous.html

// copy from host to guest virtualBox
1. https://www.youtube.com/watch?v=VUWf-uU_1jk

// making scripts
1. https://www.geeksforgeeks.org/creating-and-running-bash-and-zsh-scripts/
2. touch scripts_name.zsh (.sh for bash)
3. chmod +x scripts_name.zsh (making it an executable)

// list of window manager
1. https://dwm.suckless.org/ ::: dynamic WM

we re installing i3 (https://i3wm.org/docs/userguide.html)
1. sudo apt install startx i3
2. startx
3. change the configuration at .config/i3
4. change the keybindings to ur liking
5. add this to the end of row in the config file
    ; exec always nitrogen --restore
    ; https://wiki.archlinux.org/title/nitrogen
    ; is a fast and lightweight (GTK2) desktop background browser and setter for X Window.
// list of window manager

// changing terminal font size (etc terminal related)
1. https://raspberrytips.com/increase-font-size-in-linux-terminal/
2. /etc/default/console-setup

// all random commands
1. sudo fdisk -l
2. df -h :::  report how much space is used, available, percentage used, and the mount point of every disk attached to your system
3. apt list --installed
4. sudo reboot
5. sudo apt install gnupg curl git vim
6. sudo shutdown -h now
7. top ; like task manager ; (https://www.javatpoint.com/linux-task-manager#:~:text=We%20can%20apply%20it%20in,usage%2C%20CPU%20usage%2C%20etc.)

```

### installing zsh (https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)

If necessary, follow these steps to install Zsh:

There are two main ways to install Zsh:

1. With the package manager of your choice, e.g. sudo apt install zsh (see below for more examples)
2. From source, following the instructions from the Zsh FAQ.
3. Verify installation by running zsh --version. Expected result: zsh 5.0.8 or more recent.

4. Make it your default shell: chsh -s $(which zsh) or use sudo lchsh $USER if you are on Fedora.

5. Note that this will not work if Zsh is not in your authorized shells list (/etc/shells) or if you don't have permission to use chsh. If that's the case you'll need to use a different procedure.
6. If you use lchsh you need to type /bin/zsh to make it your default shell.
7. Log out and log back in again to use your new default shell.

8. Test that it worked with echo $SHELL. Expected result: /bin/zsh or similar.

9. Test with $SHELL --version. Expected result: 'zsh 5.8' or similar

### VIM

Press the Esc key to go back to the normal mode. ESC.
Type u to undo the last change.
To undo the two last changes, you would type 2u .
Press Ctrl-r to redo changes which were undone. In other words, undo the undos. Typically, known as redo.