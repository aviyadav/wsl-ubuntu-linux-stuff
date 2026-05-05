# NixOS - WSL2

download latest nixos.wsl from
[https://github.com/nix-community/NixOS-WSL/releases/latest]


[install]
```
wsl --install --from-file nixos.wsl
```

[login] 
```
wsl -d NixOS
```

[Post-Install]

[set password]

```
passwd
# or
sudo passwd nixos
```

[update]
```
sudo nix-channel --update

sudo nixos-rebuild switch
```

[change default useranem from nixos]

sudo nano /etc/nixos/configuration.nix

```
# wsl.defaultUser = "nixos"
wsl.defaultUser = "avinash"
```

ctrl O -- to save
ctrl X -- to exit

```
sudo nixos-rebuild boot  -- dont use nixos-rebuild switch here
```

sudo nano /etc/nixos/configuration.nix

[Add applications in the config]
```

# /etc/nixos/configuration.nix
environment.systemPackages = with pkgs; [
  vim
  wget
  git
  uv
];
```
ctrl O -- to save
ctrl X -- to exit

sudo nixos-rebuild switch   

[Now vim is available]

sudo vi /etc/nixos/configuration.nix

add after the packages stuff

```
programs.nix-ld.enable = true;
```


sudo nixos-rebuild switch  




[installation docs]
[https://nix-community.github.io/NixOS-WSL/install.html]






[rebuild CMD]
```
flake.nix to rebuild
```
