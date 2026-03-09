# Groups

https://wiki.debian.org/SystemGroups/

## List of folders and permissions

```bash
ls -ls
```

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


## Add a group

```bash
sudo groupadd <group_name> 
```

To see the group

```bash
cat /etc/group
```

## Deleted a group

```bash
sudo groupdel <group_name> 
```

## Assign an user to that group

```bash
sudo usermod -a -G
sudo usermod -aG <group_name> <user_name>
```

# References

* Learn Linux TV
  * Linux Crash Course - Managing Groups:https://youtu.be/GnlgAD8-GhE
  * Linux Crash Course - Understanding File & Directory Permissions: https://youtu.be/4e669hSjaX8
