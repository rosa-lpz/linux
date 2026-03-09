# Permissions

## Content

* ### [Users](users/)

* ### [Groups](groups/)



# Permissions

In Debian (and other Linux systems), you can give a user permission to access a directory in several ways — depending on what kind of access you want (read, write, execute, etc.). Here’s a step-by-step guide for the main methods.

------

### 1. Basic Ownership and Permissions

Let’s say the directory is `/srv/shared` and the user is `alice`.

##### **a) Change the directory’s owner**

If you want `alice` to *own* the directory:

```bash
sudo chown alice /srv/shared
```

To also make her the owner of everything inside it:

```bash
sudo chown -R alice /srv/shared
```

------

##### **b) Adjust permissions**

To let only `alice` (the owner) read/write/execute:

```bash
sudo chmod 700 /srv/shared
```

That gives:

- `rwx` to the owner (read/write/execute),
- no permissions for others.

------

### 2. Shared Access via Group Permissions

If multiple users should access the directory, create a group for them.

#### **a) Create a group**

```bash
sudo groupadd sharedgroup
```

#### **b) Add users to the group**

```bash
sudo usermod -aG sharedgroup alice
sudo usermod -aG sharedgroup bob
```

#### **c) Assign group ownership of the directory**

```bash
sudo chown -R :sharedgroup /srv/shared
```

**chown** - changes ownership of a file. Can be used recursively. Usage may be restricted to root, or even disabled, for security reasons. usage: **chown** userid files or: **chown** -R userid files
 Use chown -R user:group directory/ for recursive ownership changes.chmod +rwx filename – Adds read, write, and execute permissions.

- [https://wiki.debian.org/PrincipalCommands?highlight=%28chown%29](https://wiki.debian.org/PrincipalCommands?highlight=(chown))
- https://www.geeksforgeeks.org/linux-unix/chown-command-in-linux-with-examples/

#### **d) Set permissions for the group**

Give read/write/execute to the group:

```bash
sudo chmod 770 /srv/shared
```

#### **e) Optional: make new files inherit the group**

```bash
sudo chmod g+s /srv/shared
```

That ensures all new files and subdirectories created inside `/srv/shared` belong to the same group (`sharedgroup`).

------

### 3. Fine-Grained Control (ACLs)

If you want to give **specific users** access without changing ownership or group:

#### **a) Install ACL tools**

```bash
sudo apt install acl
```

#### **b) Give user permissions**

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

Show list

```bash
df -h
```

Give access to all users to a drive

```bash
sudo chmod 77 '/media/drive'
```





# References

* Learn Linux TV
  * Linux Crash Course - Understanding File & Directory Permissions: https://youtu.be/4e669hSjaX8
