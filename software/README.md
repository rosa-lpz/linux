# Content


## [Browsers](browsers.md#browsers)
  * [Brave](browsers.md#brave)

## [Email & Messaging](email&messaging/README.md#email--messaging)
  * [Telegram](email&messaging/README.md#telegram)


## [Organization and Productivity](organization-productivity/README.md)
  * [Logseq](organization-productivity/README.md#logseq)

## [Text/Diagrams](text-diagrams/README.md)
  * [Typora](text-diagrams/README.md#typora)
  * [Draw io](text-diagrams/README.md#draw-io)
  * [MasterPDF](text-diagrams/README.md#masterpdf)
  * [PDF4QT](text-diagrams/README.md#pdf4qt)
  * [Scribus](text-diagrams/README.md#scribus)


## [Programming](programming/README.md)
  * [Python](programming/python.md#python)
  * [GitHub Desktop](programming/github-desktop.md#github-desktop)
  * [PostgreSQL](programming/postgresql.md#postgresql)
  * [PostgreSQL pgAdmin](programming/postgresql.md#postgresql-pgadmin)
  * [Anaconda](programming/anaconda.md#anaconda)
  * [Java](programming/java.md#java)

## [Security](security/README.md)
  * [Clamav](#clamav)
  * [Uncomplicated Firewall (ufw)](#uncomplicated-firewall-ufw)

## [Finance](#finance)
   * [Interactive Brokers](#interactive-brokers)

## [Learning](#learning)
	* [Anki](#anki)

* [Plugins](#plugins)
	* [Flatpak](#flatpak)
 	* [Warehouse](#warehouse) 
 * [Windows Applications](#windows-applications)
 	* [Winboat](#winboat)





 



# Finance
 ## [Interactive Brokers](https://www.interactivebrokers.com/en/trading/ibkr-desktop-download.php)
 * Installation: https://www.interactivebrokers.ca/en/general/tws-offline-latest-install-inst-linux-64.php

```bash
 ./ntws-latest-standalone-linux-x64.sh
```

# Learning
## Anki
https://docs.ankiweb.net/platform/linux/installing.html

### References
* 5 Ways to Use Anki for MATH-Related Classes (Physics, Economics, Calculus, etc.): https://youtu.be/xHoe9rvX7Ao



# Plugins
## Flatpak
* Install in debian: https://flathub.org/en/setup/Debian
### 1. Install Flatpak
A flatpak package is available in Debian 10 (Buster) and newer. To install it, run the following as root:
```bash
sudo apt install flatpak
```
### 2. Install the Software Flatpak plugin
If you are running GNOME, it is also a good idea to install the Flatpak plugin for GNOME Software. To do this, run:
```bash
sudo apt install gnome-software-plugin-flatpak
```
If you are running KDE, you should instead install the Plasma Discover Flatpak backend:
```bash
sudo apt install plasma-discover-backend-flatpak
```
### 3. Add the Flathub repository
Flathub is the best place to get Flatpak apps. To enable it, download and install the Flathub repository file or run the following in a terminal:
```bash
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```
### 4. Restart
To complete setup, restart your system. Now all you have to do is install apps!

## Warehouse
* https://flathub.org/en/apps/io.github.flattool.Warehouse
```bash
flatpak install flathub io.github.flattool.Warehouse
```
Run
```bash
flatpak run io.github.flattool.Warehouse
```
# Windows Applications
## Winboat
https://winboat.app/
