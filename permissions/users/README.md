# Users

* https://www.geeksforgeeks.org/linux-unix/users-in-linux-system-administration/





# Sudo
## Installing sudo

Unlike other distributions such as Ubuntu, Debian does not require sudo to be installed at all.

To install sudo you need to become root using, for example, the su command, install the sudo package, add your user to the sudo group and then log out and then log in again.

If a root password was not set during your Debian installation, the normal user account that was created at installation will be able to run 'sudo' with no password: log in as that account and run sudo passwd to set a root password before continuing.

```bash
$ su --login
Password: 
## (enter here the password of the root user that you specified during your Debian installation, and press Enter)
# apt install sudo
# adduser jhon-smith sudo
```

(Obviously replace "jhon-smith" with your personal username)

Then log out and log back in again.

## Configuring sudo

The main sudo configuration file is /etc/sudoers. This file is read-only, even for root: there is a visudo command which allows root to edit the file but it is better to put local configuration in a new file in /etc/sudoers.d. Using /etc/sudoers.d/ will ensure local changes remain in effect, even if the Debian package maintainer changes /etc/sudoers in a new version of the [sudo](https://tracker.debian.org/sudo "DebianPts") package.

The example below sets up a clean environment, including a secure path; allows the root user to run any command; allows any members of the sudo group to run any command as root; allows the user deb to run the piuparts command; and loads other configuration from the files in /etc/sudoers.d.

```bash
Defaults        env_reset
Defaults        mail_badpass
Defaults        secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
Defaults        use_pty
root    ALL=(ALL:ALL) ALL
%sudo   ALL=(ALL:ALL) ALL
deb     ALL=/usr/sbin/piuparts
@includedir /etc/sudoers.d
```

The percent sign (%) is used to indicate a group in the configuration file (see the %sudo line below. By default Debian does not provide a wheel group, unlike other the BSD family of operating systems).

### Requiring the root password

If you want to require the root password for use of sudo, rather than the user's password, add the line:

Defaults   rootpw

to a file in /etc/sudoers.d.


### Reference
* https://wiki.debian.org/sudo/



## Grant sudo access 
### Using Terminal
```bash
sudo usermod -aG sudo <user_name>
```

### File
Open text editor
https://www.geeksforgeeks.org/linux-unix/how-to-open-a-texteditor-in-an-ubuntu-terminal/
