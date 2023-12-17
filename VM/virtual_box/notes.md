DEBIAN12 ::

- https://www.youtube.com/watch?v=MxIAyAELqu4
- https://forums.virtualbox.org/viewtopic.php?t=106069
- https://www.youtube.com/watch?v=h8opVWdDPXM
- https://linuxhint.com/how-to-fix-debian-sudo-command-not-found/
- https://linuxize.com/post/how-to-list-users-in-linux/
- https://www.youtube.com/watch?v=77-tuFE_pGc // window manager i3 set ups
- https://i3wm.org/docs/userguide.html
- https://github.com/tmux/tmux/wiki/Installing
- https://github.com/owl-birds/tmux-config/blob/main/.tmux.conf

# SETTING UP WINDOW MANAGER --- i3wm

## links

1. https://i3wm.org/docs/userguide.html
2. https://wiki.debian.org/GrubTransition
3. https://www.youtube.com/watch?v=77-tuFE_pGc // setting up i3
4. https://itsfoss.com/file-managers-linux/
5. https://wiki.archlinux.org/title/KDE#KF5.2FQt5_applications_don.27t_display_icons_in_i3.2Ffvwm.2Fawesome
6. https://installati.one/install-breeze-icon-theme-ubuntu-20-04/?expand_article=1
7. https://www.vpsserver.com/check-linux-cpu-usage/
8. https://wiki.archlinux.org/title/tmux
9. https://github.com/rothgar/awesome-tmux#themes
10. https://www.howtogeek.com/124622/how-to-enlarge-a-virtual-machines-disk-in-virtualbox-or-vmware/
11. https://github.com/yshui/picom
12. https://wiki.archlinux.org/title/Picom
13. https://www.youtube.com/watch?v=aEt5FKD87uc
14. https://github.com/yshui/picom/blob/next/picom.sample.conf
15. https://linux-packages.com/manjaro-linux/package/xorg-xprop
16. https://command-not-found.com/xprop
17. https://support.huaweicloud.com/intl/en-us/codehub_faq/codehub_faq_1007.html
18. https://ravicpoon.medium.com/how-to-fix-github-007-error-1056a1a41213
19. https://askubuntu.com/questions/527410/what-is-the-advantage-of-using-sudo-apt-get-autoremove-over-a-cleaner-app
20. https://reqbin.com/req/c-egazzayq/curl-download-file
21. https://www.baeldung.com/linux/install-multiple-fonts

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
6. https://forum.manjaro.org/t/wallpaper-goes-blank-after-reboot/60864
    ; exec --no-startup-id nitrogen --restore; sleep 1; compton -b # add this to i3 config file
// list of window manager

// changing terminal font size (etc terminal related)
1. https://raspberrytips.com/increase-font-size-in-linux-terminal/
2. /etc/default/console-setup

// TMUX PORBLEMS
1. https://github.com/tmux/tmux/issues/2377
2. https://github.com/tmux-plugins/tmux-continuum/issues/48 ; Not sure what exactly caused it but for me the culprit was https://github.com/jimeh/tmux-themepack.
When sourcing my plugins with tpm I had to make sure to add the themepack before continuum

// BACKUP ; SNAPSHOTS ; RESTORE
1. sudo apt install timeshift
3. sudo timeshift-launcher
2. https://www.linuxbuzz.com/how-to-install-use-timeshift-on-debian/

// ENHANCING VBOX EXPERIENCE
1. insalling virtualbox guest additions : https://itslinuxfoss.com/install-virtualbox-guest-additions-debian-12/
2. https://kifarunix.com/install-virtualbox-guest-additions-on-debian-11/?expand_article=1
3. https://stackoverflow.com/questions/22165929/install-linux-headers-on-debian-unable-to-locate-package

// INSTALL ETC
1. sudo apt-get install libevent ncurses libevent-dev ncurses-dev build-essential bison pkg-config

// all random commands
1. sudo fdisk -l
2. df -h :::  report how much space is used, available, percentage used, and the mount point of every disk attached to your system
3. apt list --installed
4. sudo reboot
5. sudo apt install gnupg curl git vim
6. sudo shutdown -h now
7. top ; like task manager ; (https://www.javatpoint.com/linux-task-manager#:~:text=We%20can%20apply%20it%20in,usage%2C%20CPU%20usage%2C%20etc.)
8. TMUX ; tmux list-sessions ; tmux new -s session_name ; tmux kill-session -t session_name ; tmux attach -t session_name ; tmux kill-session -a ; tmux a
 ->> https://debugpointer.com/linux/tmux-cheatsheet
9. dpkg -s package-name : to find out wehter the package is installed or not
10. rm -r dir_name
11. sudo find / -iname filename/dir_name
12. xprop : to find window informations/details : to install it on debian12 : sudo apt install x11-utils
13. git commit --amend --reset-author --no-edit
14. curl -o filename.txt https://reqbin.com/echo
15. cp ~/Downloads/{*.ttf,*.otf} ~/.local/share/fonts
16. fc-cache -f -v
17. curl -L -O links
18. removing any files with specific extensions : for file in $(find /path/to/dir -name "*.extension"); do rm -f "$file"; done
19. unzip file.zip -d destination_folder
20. cp ~/Downloads/{*.ttf,*.otf} ~/.local/share/fonts
21. sudo dpkg -i DEB_PACKAGE ; INSTALL
22. sudo dpkg -r PACKAGE_NAME ; REMOVE A PACKAGE
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
