[windows]
```
wsl --install archlinux
```

[archlinux - as root]

```
pacman -Syu
useradd -m avinash
passwd avinash # set password

pacman -S vim
pacman -S sudo
pacman -S less

vim /etc/sudoers

# [add] USER_NAME   ALL=(ALL:ALL) ALL
```

[windows]
```
wsl --manage archlinux --set-default-user avinash

wsl -u root -d archlinux
```

[archlinux - as avinash]

[edit .bashrc]
```
# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'

    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi

# some more ls aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
alias cls='clear'
alias md='mkdir'
alias vi='vim'
```


[from command line - outside .bashrc]

```
sudo pacman -Sy python
sudo pacman -Sy wget
sudo pacman -Sy curl
sudo pacman -Sy git
sudo pacman -Sy nodejs npm

sudo npm i -g npm

sudo pacman -S fish
```
