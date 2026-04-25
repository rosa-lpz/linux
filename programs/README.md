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
  * [Anaconda](#anaconda)
* [Security](#security)
  * [Uncomplicated Firewall (ufw)](#uncomplicated-firewall-ufw)
* [Finance](#finance)
   * [Interactive Brokers](#interactive-brokers)
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
[Go Back](#content)

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
postgres=# alter user postgres with password 'add_password';
ALTER ROLE
postgres=# quit
```

### References
* How to Install Postgres and Pgadmin on Ubuntu 24.04 LTS Linux:https://youtu.be/cD32EHVWRXY

## Anaconda

### Installation

* https://docs.anaconda.com/anaconda/install/
* https://www.anaconda.com/docs/getting-started/anaconda/install/linux-install
* Repo archive: https://repo.anaconda.com/archive/
* Installation video: https://www.youtube.com/watch?v=sU2mXjOB-fA

#### Download the installation file
```bash
wget https://repo.anaconda.com/archive/Anaconda3-2025.12-2-Linux-x86_64.sh
```

#### Check integrity of the file
```bash
shasum -a 256 ~/<INSTALLER-FILENAME>
shasum -a 256 Anaconda3-2024.10-1-Linux-x86_64.sh

```
	* Compare it with https://repo.anaconda.com/archive/

#### Normal Installation
```bash
bash ~/Anaconda3-2025.12-2-Linux-x86_64.sh
```

```bash
bash /Downloads/Anaconda-latest-Linux-x86_64.sh
```
	
#### Install in another directory
```bash
sudo bash Anaconda3-2024.10-1-Linux-x86_64.sh -f -b -p /Programs/anaconda3
```

#### Refresh terminal
```bash
source ~/.bashrc
```

#### List of packages installed with anaconda
```bash
conda list
```


### Anaconda commands

```bash
--Create--
conda create -name ENV_NAME python=python_version
conda create -n ENV_NAME python=python_version

--ActivateEnvironments--
conda activate

--See-list-libraries
conda list

--Activate-Specific-Environment--
conda activate <env_name>

---List-all-the-environments--
conda env list

--Deactivate-environment--
conda deactivate

---Update---
conda update -n base -c defaults conda

--Delete-environment--
conda remove --name ENV_NAME --all

--Delete-environment with libraries--
conda remove --n ENV_NAME --all
```


### Environments
#### Create environments

```bash
conda create --name <my-env>
```

With an specific Python version
```bash
conda create -n myenv python=3.8
```
#### Delete environment
```bash
conda remove --name ENV_NAME --all
```

`ENV_NAME` denotes the name of the environment to be removed/deleted. Make sure you deactivate an environment before removing it by running the `conda deactivate` command.

The `--all` flag removes all the packages installed in that environment.

Here's a summary of the steps involved in deleting an environment in Conda:

- Deactivate the environment using the `conda deactivate` command.
- Delete the environment using the `conda remove --name ENV_NAME --all` command.

**References**
* https://www.freecodecamp.org/news/how-to-delete-an-environment-in-conda/


#### Examples
```bash
Examples:  
  
Remove the package 'scipy' from the currently-active environment::  
  
   conda remove scipy  
  
Remove a list of packages from an environment 'myenv'::  
  
   conda remove -n myenv scipy curl wheel  
  
Remove all packages from environment `myenv` and the environment itself::  
  
   conda remove -n myenv --all  
  
Remove all packages from the environment `myenv` but retain the environment::  
  
   conda remove -n myenv --all --keep-env
```


# Security

## Uncomplicated Firewall (ufw)

### Install

```bash
sudo apt install ufw
```
**Check status of ufw**
```bash
sudo ufw status
```
or
```bash
systemctl status ufw
```




### Configure ufw
**Default outgoing policy**

We change the the default outgoing policy to 'Allow'. If the server/pc is trying to reach something on the internet, basically it's outgoing from the server/pc to the internet, then you'll want to be able to reach whatever it's trying to reach.
```bash
sudo ufw default allow outgoing
```
**Default policy for incoming**
```bash
sudo ufw default deny incoming
```
Next, it is recommended to verify that the firewall is enabled by typing:
```bash
sudo ufw status verbose
```
Note: With this command you will also be able to see all of the defaults and rules which you have applied.

#### Rules
**Allow ssh connections**
By default ufw denies all of the incoming connections, which will make it a problem if you are using SSH. Therefore, you must create a rule which allows SSH connections, by typing:
```bash
sudo ufw allow ssh
sudo ufw enable
sudo ufw  status
```
**Allow http/tcp connections**
```bash
sudo ufw allow http/tcp
```
**Port Ranges**
```bash
sudo ufw allow 1000:2000/tcp
```
for udp
```bash
sudo ufw allow 1000:2000/udp
```
**IP Address**
```bash
sudo ufw allow from 111.222.333.444
```
**IP PostgreSQL**
```bash
sudo ufw allow from 203.0.113.103 to any port 5432
sudo ufw allow from 127.0.0.1 to any port 5432
```
**Status numbered**
```bash
sudo ufw status numbered
```
Output
```bash
     To                         Action      From
     --                         ------      ----
[ 1] 80/tcp                     ALLOW IN    Anywhere                  
[ 2] Anywhere                   ALLOW IN    IP_number            
[ 3] 80/tcp (v6)                ALLOW IN    Anywhere (v6) 
```

**Status numbered - delete**
```bash
sudo ufw deleted 3
```

### Graphical Interface
```bash
sudo apt-get install gufw
```

### References
* Akami Developer - Linux Firewall Tutorial | How to Configure Firewall Rules with UFW: https://youtu.be/XtRXm4FFK7Q
* Debian - Uncomplicated Firewall (ufw): https://wiki.debian.org/Uncomplicated%20Firewall%20%28ufw%29
* https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands
* UFW | Uncomplicated Firewall: https://youtu.be/fcxirBuDnXY

# Finance
 ## [Interactive Brokers](https://www.interactivebrokers.com/en/trading/ibkr-desktop-download.php)
 * Installation: https://www.interactivebrokers.ca/en/general/tws-offline-latest-install-inst-linux-64.php

```bash
 ./ntws-latest-standalone-linux-x64.sh
```
