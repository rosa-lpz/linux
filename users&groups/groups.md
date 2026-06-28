# Groups





## List groups

```bash
groups
groups <user_name>
cat /etc/passwd
```

Listing of all user accounts in the system

```bash
cat /etc/passwd
```

Listing of all groups in the system

```bash
cat /etc/group
```


## Add/Create a group

```bash
sudo groupadd <group_name> 
sudo addgroup <group_name> 
```


To see the group

```bash
cat /etc/group
```

## Delete a group

```bash
sudo groupdel <group_name> 
```

## Assign an user to a group

```bash
sudo usermod -a -G
sudo usermod -aG <group_name> <user_name>
```

## Check user group
```bash
groups <user_name>
```

### Assign group ownership of a directory

```bash
sudo chown :sharedgroup /srv/shared
sudo chown -R :sharedgroup /srv/shared
```

**chown** - changes ownership of a file. Can be used recursively. Usage may be restricted to root, or even disabled, for security reasons. usage: **chown** userid files or: **chown** -R userid files
 Use chown -R user:group directory/ for recursive ownership changes.chmod +rwx filename – Adds read, write, and execute permissions.





# References
- https://wiki.debian.org/PrincipalCommands?highlight=(chown)
- https://www.geeksforgeeks.org/linux-unix/chown-command-in-linux-with-examples/
* https://wiki.debian.org/SystemGroups/
* Learn Linux TV
  * Linux Crash Course - Managing Groups:https://youtu.be/GnlgAD8-GhE
  * Linux Crash Course - Understanding File & Directory Permissions: https://youtu.be/4e669hSjaX8
