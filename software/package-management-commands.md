# Package Management Commands

Package management commands are used to install, update, upgrade, and remove software packages. They ensure proper dependency handling and keep the system up to date.

* apt
* apt-get
* aptitude



## Install Software

**Command line**

```cmd
sudo apt install snap
```



**See the installed Software**

```cmd
dpkg --list
```

or

```cmd
apt list --installed
```



### APP images

https://www.howtogeek.com/827849/how-to-use-appimages-on-linux/
Example 1

```bash
chmod +x FreeCAD-0.20.0-Linux-x86_64.AppImage
```

Example 2

```bash
$ chmod a+x Subsurface*.AppImage
$ ./Subsurface*.AppImage
```



### RPM Packages

```bash
sudo rpm -i "path_to_RPM_Package"
sudo rpm -i anytype-0.45.0.x86_64.rpm
```



### DEB Packages

#### dpkg

In general, if you are using the dpkg command you can use the following command format:

```bash
sudo dpkg -i "path_to_Debian_Package"
sudo dpkg -i anytype_0.45.0_amd64.deb
```

Where you need to replace the “path_to_Debian_Package” with the path of your Debian package. Therefore, for example, to install ASC Music Debian package you would use a command like the below one:

```bash
sudo dpkg -i Downloads/asc-music_1.3-4_all.deb
```

https://www.fosslinux.com/41461/how-to-install-deb-packages-on-ubuntu-linux-mint.htm



### Homebrew

**The Missing Package Manager for macOS (or Linux)**

* Website: https://brew.sh/
* Documentation: https://docs.brew.sh/Manpage


Install

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```bash
==> Next steps:
- Run these two commands in your terminal to add Homebrew to your PATH:
    (echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/rlz-98/.bashrc
    eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
- Install Homebrew's dependencies if you have sudo access:
    sudo apt-get install build-essential
  For more information, see:
    https://docs.brew.sh/Homebrew-on-Linux
- We recommend that you install GCC:
    brew install gcc
- Run brew help to get started
- Further documentation:
    https://docs.brew.sh

```



Add Homebrew to the PATH:

```bash
~$ test -d ~/.linuxbrew && eval "$(~/.linuxbrew/bin/brew shellenv)"
~$ test -d /home/linuxbrew/.linuxbrew && eval$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
echo "eval \"\$($(brew --prefix)/bin/brew shellenv)\"" >> ~/.bashrc

```



## Update & Upgrade Software

```cmd
sudo apt update && sudo apt upgrade
```



## Uninstall Software

### Command Line

**Remove**

```bash
sudo apt remove docker-desktop
```


**Purge**

```bash
sudo apt purge gimp
sudo apt-get purge azuredatastudio
```

**dpkg**

```bash
sudo dpkg -r gifski
```

# 