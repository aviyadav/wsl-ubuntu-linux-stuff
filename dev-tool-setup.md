### install uv
~~~
curl -LsSf https://astral.sh/uv/install.sh | sh
~~~

#### uv clean init
```
uv init <project-name> --bare

or [inside folder]

uv init . --bare
```

#### uv upgrade
```
uv self update
```

#### Add .python-version
```
uv python pin 3.13
```

#### duckdb
~~~
curl https://install.duckdb.org | sh
~~~



#### Essential build tools - development tools and libraries

[Fedora]

```
sudo dnf group install "Development Tools" "C Development Tools and Libraries"
sudo dnf install gcc gcc-c++ make automake kernel-devel
sudo dnf upgrade --refresh
```

[openSUSE]

```
sudo zypper install -t pattern devel_basis
sudo zypper install -t pattern devel_basis devel_C_C++
```

[archlinux]

```
sudo pacman -S base-devel
```

[Ubuntu]

```
sudo apt update && sudo apt install build-essential
```




```
