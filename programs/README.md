# Content
* [Browsers](#browsers)
  * [Brave](#brave)
 
* [Messaging](#messagin)
  * [Telegram](#telegram)
* [Organization and Productivity](#organization-and-productivity)
  * [Logseq](#logseq)
* [Text/Diagrams](#text)
  * [Typora](#typora)
  * [Draw io](#draw-io)
* [Programming](#programming)
  * [GitHub Desktop](#github-desktop)
  * [PostgreSQL](#postgresql)
  * [PostgreSQL pgAdmin](#postgresql-pgadmin)
* [Security](#security)
  * [Uncomplicated Firewall (ufw)](#uncomplicated-firewall-ufw)

# Browsers

## [Brave](https://brave.com/linux)

```bash
# Download and run the installer
curl -fsSL https://raw.githubusercontent.com/logseq/logseq/master/scripts/install-linux.sh | bash

# Or install a specific version
curl -fsSL https://raw.githubusercontent.com/logseq/logseq/master/scripts/install-linux.sh | bash -s -- 0.10.14

# For user-specific installation (no root required)
curl -fsSL https://raw.githubusercontent.com/logseq/logseq/master/scripts/install-linux.sh | bash -s -- --user

```
# Messaging
## [Telegram Desktop](https://desktop.telegram.org/)
 * https://desktop.telegram.org/

# Organization and Productivity
## Logseq
* GitHub Repository: https://github.com/logseq/logseq

```bash
# Download and run the installer
curl -fsSL https://raw.githubusercontent.com/logseq/logseq/master/scripts/install-linux.sh | bash

# Or install a specific version
curl -fsSL https://raw.githubusercontent.com/logseq/logseq/master/scripts/install-linux.sh | bash -s -- 0.10.14

# For user-specific installation (no root required)
curl -fsSL https://raw.githubusercontent.com/logseq/logseq/master/scripts/install-linux.sh | bash -s -- --user
```
# Text
## [Typora](https://typora.io/)
* Releases: https://typora.io/releases/all
```bash
# add Typora's key
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://downloads.typora.io/typora.gpg | sudo tee /etc/apt/keyrings/typora.gpg > /dev/null
# add Typora's repository securely
echo "deb [signed-by=/etc/apt/keyrings/typora.gpg] https://downloads.typora.io/linux ./" | sudo tee /etc/apt/sources.list.d/typora.list
sudo apt update
# install typora
sudo apt install typora
```
## Draw io

* Repository: https://github.com/jgraph/drawio-desktop/
* Releases: https://github.com/jgraph/drawio-desktop/releases
* Deb file: https://github.com/jgraph/drawio-desktop/releases/download/v29.6.6/drawio-amd64-29.6.6.deb

# Programming

## GitHub Desktop

* Repository: https://github.com/shiftkey/desktop
* Releases: https://github.com/shiftkey/desktop/releases

### What is this repository for?

This repository contains specific patches on top of the upstream
`desktop/desktop` repository to support Linux usage.

It also publishes [releases](https://github.com/shiftkey/desktop/releases) for various Linux distributions:

 - AppImage (`.AppImage`)
 - Debian (`.deb`)
 - RPM (`.rpm`)

### Installation via package manager

You can use your operating system's package manager to install `github-desktop` and
keep it up to date on Debian and RPM-based distributions.

### Debian/Ubuntu

There are two APT package feeds available, both hosted in the US. You only need
to add one or the other here, as both of these are generated based on the
releases from this repository.

#### [@shiftkey](https://github.com/shiftkey) package feed

```bash
wget -qO - https://apt.packages.shiftkey.dev/gpg.key | gpg --dearmor | sudo tee /usr/share/keyrings/shiftkey-packages.gpg > /dev/null
sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/shiftkey-packages.gpg] https://apt.packages.shiftkey.dev/ubuntu/ any main" > /etc/apt/sources.list.d/shiftkey-packages.list'
```

#### [@mwt](https://github.com/mwt) package feed

```bash
wget -qO - https://mirror.mwt.me/shiftkey-desktop/gpgkey | gpg --dearmor | sudo tee /usr/share/keyrings/mwt-desktop.gpg > /dev/null
sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/mwt-desktop.gpg] https://mirror.mwt.me/shiftkey-desktop/deb/ any main" > /etc/apt/sources.list.d/mwt-desktop.list'
```

#### Installation

Once you have a feed configured, run this command to install the application:

```bash
sudo apt update && sudo apt install github-desktop
```
## PostgreSQL
* https://www.postgresql.org/download/linux/debian/

PostgreSQL is available in all Debian versions by default. However, Debian "snapshots" a specific version of PostgreSQL that is then supported throughout the lifetime of that Debian version. The PostgreSQL project maintains an Apt repository with all supported of PostgreSQL available.
 
### Included in Distribution

Debian includes PostgreSQL by default. To install PostgreSQL on Debian, use the apt (or other apt-driving) command:
```bash
apt install postgresql
```
### PostgreSQL Apt Repository

If the version included in your version of Debian is not the one you want, you can use the PostgreSQL Apt Repository. This repository will integrate with your normal systems and patch management, and provide automatic updates for all supported versions of PostgreSQL throughout the support lifetime of PostgreSQL.

The PostgreSQL Apt repository supports the current versions of Debian:

    trixie (13.x)
    bookworm (12.x)
    bullseye (11.x)
    forky (testing)
    sid (unstable)

on the following architectures:

    amd64
    arm64
    ppc64el

Automated repository configuration: 
```bash
sudo apt install -y postgresql-common
sudo /usr/share/postgresql-common/pgdg/apt.postgresql.org.sh
```
To manually configure the Apt repository, follow these steps: 
```bash
# Import the repository signing key:
sudo apt install curl ca-certificates
sudo install -d /usr/share/postgresql-common/pgdg
sudo curl -o /usr/share/postgresql-common/pgdg/apt.postgresql.org.asc --fail https://www.postgresql.org/media/keys/ACCC4CF8.asc

# Create the repository configuration file:
. /etc/os-release
sudo sh -c "echo 'deb [signed-by=/usr/share/postgresql-common/pgdg/apt.postgresql.org.asc] https://apt.postgresql.org/pub/repos/apt $VERSION_CODENAME-pgdg main' > /etc/apt/sources.list.d/pgdg.list"

# Update the package lists:
sudo apt update
```

Install PostgreSQL: (replace "18" by the version you want) 
```bash
sudo apt install postgresql-18
```

## PostgreSQL pgAdmin
* https://www.pgadmin.org/download/pgadmin-4-apt/
* 
```bash
# Setup the repository
#

# Install the public key for the repository (if not done previously):
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg

# Create the repository configuration file:
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'

#
# Install pgAdmin
#

# Install for both desktop and web modes:
sudo apt install pgadmin4

# Install for desktop mode only:
sudo apt install pgadmin4-desktop

# Install for web mode only: 
sudo apt install pgadmin4-web 

# Configure the webserver, if you installed pgadmin4-web:
sudo /usr/pgadmin4/bin/setup-web.sh
```

### Change password
Execute
```bash
sudo -u postgres psql
```
output
```bash
postgres=#
```
Then type:
```bash
postgres=# alter user postgres with password 'add_password'
ALTER ROLE
postgres=# quit
```

### References
* How to Install Postgres and Pgadmin on Ubuntu 24.04 LTS Linux:https://youtu.be/cD32EHVWRXY

# Security

## Uncomplicated Firewall (ufw)

### Install

```bash
sudo apt install ufw
```
**Check status of ufw**
```bash
systemctl status ufw
```
### Configure ufw
**Default outgoing policy**

We change the the default outgoing policy to 'Allow'. If the server/pc is trying to reach something on the internet, basically it's outgoing from the server/pc to the interenet, then you'll want to be able to reach whatever it's trying to reach.
```bash
ufw default allow outgoing
```
**Default policy for incoming**
```bash
ufw default deny incoming
```

### References
* Akami Developer - Linux Firewall Tutorial | How to Configure Firewall Rules with UFW: https://youtu.be/XtRXm4FFK7Q
* Debian - Uncomplicated Firewall (ufw): https://wiki.debian.org/Uncomplicated%20Firewall%20%28ufw%29
