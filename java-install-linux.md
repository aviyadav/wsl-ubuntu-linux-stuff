# JDK installation on Linux

[Ububntu]

```
sudo apt update
sudo apt install default-jdk
javac -version
sudo apt install openjdk-17-jdk
```


[FedoraLinux-43]

```
sudo dnf update

sudo dnf search openjdk

sudo dnf install java-21-openjdk-devel.x86_64

java -version

export JAVA_HOME=$(dirname $(dirname $(readlink -f $(which java)))
```

[opensuse]

```
sudo zypper refresh
sudo zypper search openjdk-devel 
sudo zypper --non-interactive install java-17-openjdk-devel
```
