#command to make the prompt short:

$ cp .bashrc .bashrc-backup
$ gedit .bashrc
then in gedit,
if [ "$color_prompt" = yes ]; then    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '    
else
    #PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
    PS1="[${debian_chroot:+($debian_chroot)}\u \W]\$ "

#Writing to an SD Card
#(To format card use Gparted, or Disks)
sudo apt-get install gddrescue xz-utils
unxz ubuntu-mate-15.10.3-desktop-armhf-raspberry-pi-2.img.xz
sudo ddrescue -D --force ubuntu-mate-15.10.3-desktop-armhf-raspberry-pi-2.img /dev/sdx

#Adding a desktop entry
#the categories
Accessories --> Utility;
Edutainment --> Education;
Games --> Game;
Graphics --> Graphics;
Internet --> Network;
Office --> Office;
Programming --> Development;
Sound & Video -->AudioVideo;
System Tools --> System;
Others --> Other;

[Desktop Entry]
Version=x.y
Name=ProgramName
Comment=This is my comment
Exec=/home/alex/Documents/exec.sh
Icon=/home/alex/Pictures/icon.png
Terminal=false
Type=Application
Categories=Utility;Application;

#Check running processors
ps -ef

#Processors - check running processors by user
pgrep -l -u user
#or
ps -ef | grep user

#Processors - Select all processes except session leaders
ps - a

#pulse audio volume change
/home/(user)/.config/pulse/default.pa and scroll to the bottom to set-sink-volume and change the value to 0

#restart gnome shell without closing applications
killall -3 gnome-shell
gnome-shell --replace

#adding git branch name to show in the terminal
#goto bashrc and
# uncomment for a colored prompt, if the terminal has the capability; turned
# off by default to not distract the user: the focus in a terminal window
# should be on the output of commands, not on the prompt
#force_color_prompt=yes
#then do
# Add git branch if its present to PS1
parse_git_branch() {
 git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
if [ "$color_prompt" = yes ]; then
 PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[01;31m\]$(parse_git_branch)\[\033[00m\]\$ '
else
 PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w$(parse_git_branch)\$ '
fi
unset color_prompt force_color_prompt
