[Debian]

```
su -
```

You will be prompted to enter the root password.

```
usermod -aG sudo <username>

# or

adduser <username> sudo

```

[verify]

```
groups <username>
# or
getent group sudo

```
