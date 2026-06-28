# Permissions

## Content


## Other content

* [Users](users&groups/users.md)
* [Groups](users&groups/groups.md)


# Permissions

In Debian (and other Linux systems), you can give a user permission to access a directory in several ways — depending on what kind of access you want (read, write, execute, etc.). Here’s a step-by-step guide for the main methods.
Every file in Linux has permissions defined for:

- **Owner** (user who created the file)
- **Group** (users in the same group)
- **Others** (everyone else)

**chown** - changes ownership of a file. Can be used recursively. Usage may be restricted to root, or even disabled, for security reasons. usage: **chown** userid files or: **chown** -R userid files
 Use chown -R user:group directory/ for recursive ownership changes.chmod +rwx filename – Adds read, write, and execute permissions.

## List of folders and permissions

### Example 1

```bash
ls -ls
```

**Output**

```bash
-rw-r--r-- 1 atul developers 1200 Aug 18 11:20 report.txt
```

* rw- → owner (read, write)
* r-- → group (read-only)
* r-- → others (read-only)

## Example 2

```bash
ls -ld /projects
```

**Output**

```bash
drwxr-x--- 5 root dev 4096 Jan 20 22:23 /projects
```

- `d` indicates that `/projects` is a directory
- `rwx` shows the owner has full read/write/execute access
- `r-x` means the group has read and execute permissions
- `---` means others have no access at all

So a folder with "rwx" for the owner, "r-x" for the group, and "—" for others would have a numeric notation of "750".

## Change the file / directory ownership

### File ownership

Give file ownership 'alice' user

```bash
sudo chown alice report.txt
```

Give file ownership to a group

```bash
sudo chown atul:developers report.txt
```

### Directory ownership

If you want `alice` to *own* the directory `/srv/shared`:

```bash
sudo chown alice /srv/shared
```

To also make her the owner of everything inside it:

```bash
sudo chown -R alice /srv/shared
```

------

## Change permissions

### Example 1

To let only `alice` (the owner) read/write/execute:

```bash
sudo chmod 700 /srv/shared
```

7 = read/write/execute
0 = no permissions 

That gives:

- `rwx` to the owner (read/write/execute),
- `---` no permissions for others.


## Example 2

```bash
chmod 755 script.sh
```

7 = read/write/execute
5 = read/execute only

That gives:

- `rwx` to the owner has full read/write/execute access
- `rx`  the group and others have read and execute permissions



## Shared access via group permissions

If multiple users should access the directory, create a group for them.

```bash
sudo groupadd sharedgroup # Create the sharedgroup group
sudo usermod -aG sharedgroup alice # add user to the group
sudo usermod -aG sharedgroup bob # add user to the group
```

Assign group ownership of the directory

```bash
sudo chown -R :sharedgroup /srv/shared
```


* https://wiki.debian.org/PrincipalCommands?highlight=(chown)
* https://www.geeksforgeeks.org/linux-unix/chown-command-in-linux-with-examples/



#### Set permissions for the group

Give read/write/execute to the group:

```bash
sudo chmod 770 /srv/shared
sudo chmod -R 770 "/path/to/directory" # Give permissions recursively
```



#### Optional: make new files inherit the group

```bash
sudo chmod g+s /srv/shared
sudo chmod g+s -R /srv/shared # recursevely
```

That ensures all new files and subdirectories created inside `/srv/shared` belong to the same group (`sharedgroup`).

------

### Fine-Grained Control (ACLs)

If you want to give **specific users** access without changing ownership or group:

#### Install ACL tools

```bash
sudo apt install acl
```

#### Give user permissions

For example, to give `alice` read/write/execute:

```bash
sudo setfacl -m u:alice:rwx /srv/shared
```

To verify:

```bash
getfacl /srv/shared
```

------

### Summary

| Goal                     | Command                                                      |
| ------------------------ | ------------------------------------------------------------ |
| Give one user ownership  | `sudo chown -R alice /srv/shared`                            |
| Give group access        | `sudo chmod 770 /srv/shared && sudo chown :sharedgroup /srv/shared` |
| Fine-grained user access | `sudo setfacl -m u:alice:rwx /srv/shared`                    |



## Permissions for a external drive

### Show list

```bash
df -h
```

Output

```bash
/dv/dm   20G     /media/user/drive
/dv/dm   30G     /media/user/drive2
```

### Check permissions

```bash
cd /media/user/
ls -l
```

Output

```bash
drwxrwxrwx 23 user users <date>
```


### Give access to all users to a drive

```bash
sudo chmod 777 '/media/drive'
```

### see the new permissions

```bash
stat '/media/drive'
```



# References

* https://wiki.debian.org/UsersAndGroups
* https://wiki.debian.org/Permissions
* Learn Linux TV
  * Linux Crash Course - Understanding File & Directory Permissions: https://youtu.be/4e669hSjaX8

* https://www.redhat.com/en/blog/manage-permissions