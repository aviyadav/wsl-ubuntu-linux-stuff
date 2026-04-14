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
```

[installation docs]
[https://nix-community.github.io/NixOS-WSL/install.html]


[rebuild CMD]
```
flake.nix to rebuild
```