# Security
## Clamav
### Installing ClamAV
* https://docs.clamav.net/manual/Installing.html

**DEB packages (for Debian, Ubuntu, etc.)**
```bash
sudo apt install ~/Downloads/clamav-1.4.0.linux.x86_64.deb
```
You can verify that the package was installed using:
```bash
sudo apt info clamav
```
And uninstall the package with:
```bash
sudo apt remove clamav
```

#### **Updating Signature Databases FreshClam**

* https://docs.clamav.net/manual/Usage/SignatureManagement.html

Before you can start the ClamAV scanning engine (using either clamd or clamscan), you must first have ClamAV Virus Database (.cvd) file(s) installed in the appropriate location on your system.

The tool freshclam is used to download and update ClamAV’s official virus signature databases. While easy to use in its base configuration, freshclam does require a working freshclam.conf configuration file to run (the location of which can be passed in via command line if the default search location does not fit your needs).

Once you have a valid configuration file, you can invoke FreshClam with the following command:
```bash
sudo freshclam
```


### ClamTk (Graphical Interface)
**Debian**
* Install ClamTk using "Discover" in Debian.

## Karspersky
### Free virus removal tool (Linux)
* https://latam.kaspersky.com/downloads/free-virus-removal-tool

Download kvrt.run file
Open "Download" folder in terminal and give permissions to kvrt.run file:
```bash
chmod +x kvrt.run
```
Execute kvrt.run
```bash
./kvrt.run
```
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
