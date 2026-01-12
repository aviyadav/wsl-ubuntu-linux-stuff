# opensuse on WSL/2
```
wsl --install -d openSUSE-Leap-16.0

wsl --install -d openSUSE-Tumbleweed
```

[After installation]

```
sudo zypper refresh
sudo zypper update

sudo zypper install curl
sudo zypper install tar
sudo zypper install git
sudo zypper install python3

-- install uv
sudo zypper addrepo --refresh https://download.opensuse.org/repositories/system:/snappy/openSUSE_Leap_16.0/ snappy
sudo zypper --gpg-auto-import-keys refresh
sudo zypper dup --from snappy
sudo zypper install snapd
sudo systemctl enable --now snapd
sudo systemctl enable --now snapd.apparmor

sudo snap install astral-uv --classic

-- install zsh and oh-my-zsh
sudo zypper addrepo https://download.opensuse.org/repositories/shells/16.0/shells.repo
sudo zypper refresh
sudo zypper install zsh

sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

--install vscode (not for WSL)

sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc   
sudo zypper addrepo https://packages.microsoft.com/yumrepos/vscode vscode   
sudo zypper refresh
sudo zypper install code   
```
