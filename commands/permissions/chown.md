# chown

* [Command Syntax](command-syntax)
* [Changing File Owner](changing-file-owner)
* [Changing Owner and Group](changing-owner-and-group)
* [How to Change Group Ownership Only](how-to-change-group-ownership-only )
* [Quick Reference](#quick-reference)

## Command Syntax 

The basic syntax of the `chown` command is:

txt

​      

```txt
chown [OPTIONS] USER[:GROUP] FILE(s)
```

Syntax Breakdown:

- **USER** - The user name or the user ID (UID) of the new owner.
- **GROUP** - The new group’s name or the group ID (GID). Numeric IDs for the user or group should be prefixed with the `+` symbol to avoid conflicts with names.
- **FILE(s)** - The name of one or more files, directories, or symlinks.

**Key patterns**:

- `USER` - Sets the file owner to the given user. The group ownership is not changed.
- `USER:` - With GNU `chown`, a trailing colon changes the owner and sets the group to the user’s login group.
- `USER:GROUP` - If both the user and the group are specified (with no space between them), the user ownership of the files is changed to the given user, and the group ownership is changed to the given group.
- `:GROUP` - If the User is omitted and the group is prefixed with a colon (`:`), only the file’s group ownership is changed to the given group (equivalent to `chgrp`).
- `:` If only a colon (`:`) is given, without specifying the user and the group, no change is made.

**Most common chown options**:

- `-R` - Apply to the directory and its contents recursively.
- `-h` - Change ownership of the symbolic links, not the referenced file.
- `-v` - Verbose output.
- `--reference=REF_FILE` - Copy ownership from reference file.

By default, `chown` does not produce any output on success and returns zero.

**Who Can Use chown?**

- Regular users can change the file group only if they own the file and only to a group they are a member of.
- Administrative users can change the ownership of all files.

## Changing File Owner 

To change the owner of a file, use the `chown` command followed by the user name of the new owner and the target file as an argument:

```txt
chown USER FILE
```

For example, the following command will change the ownership of a file named `file1` to a new owner named `linuxize`:

```bash
chown linuxize file1
```

To change the ownership of multiple files or directories, specify them as a space-separated list:

```bash
chown linuxize file1 dir1
```

The numeric user ID (UID) can be used instead of the username:

​      

```bash
chown +1000 file2
```



***Warning***

* If a numeric owner exists as a user name, the ownership will be transferred to the user name. To avoid this, prefix the ID with `+`.

## Changing Owner and Group 

To change both the owner and the group of a file, use the `chown` command followed by the new owner and group separated by a colon (`:`) with no intervening spaces and the target file as argument:

txt

​      

```txt
chown USER:GROUP FILE
```

The following command will change the ownership of a file named `file1` to a new owner named `linuxize` and group `devs`:

Terminal

​      

```bash
chown linuxize:devs file1
```

With GNU `chown`, a trailing colon with no group name sets the group to the user’s default login group:

Terminal

​      

```bash
chown linuxize: file1
```

Info

Ubuntu 25.10 and newer ship the Rust-based uutils `chown` as the default. In our tests on Ubuntu 26.04 (uutils 0.8.0), `chown USER: FILE` changed the owner but left the group unchanged. If the group matters, name it explicitly with `USER:GROUP`. The GNU version is still installed as `gnuchown` and follows the documented behavior.

## How to Change Group Ownership Only 

To change only the group of a file, use the `chown` command followed by a colon (`:`) and the new group name (with no space between them) and the target file as an argument:

```txt
chown :GROUP FILE
```

The following command will change the group of the file named `file1` to `www-data`:      

```bash
chown :www-data file1
```

Alternatively, to change the group ownership of files, you can use the [`chgrp`](https://linuxize.com/post/chgrp-command-in-linux/) command.



## Quick reference

| Command                      | Description                                               |
| ---------------------------- | --------------------------------------------------------- |
| `chown USER FILE`            | Change file owner                                         |
| `chown USER:GROUP FILE`      | Change owner and group                                    |
| `chown :GROUP FILE`          | Change group only                                         |
| `chown USER: FILE`           | Change owner; set group to user’s login group (GNU chown) |
| `chown -R USER:GROUP DIR`    | Recursively change ownership                              |
| `chown -h USER FILE`         | Change symlink ownership (not target)                     |
| `chown --reference=REF FILE` | Copy ownership from reference file                        |
| `chown +UID FILE`            | Use numeric UID (prefix `+` to avoid name conflicts)      |



# References

* https://linuxize.com/post/linux-chown-command/
* https://www.geeksforgeeks.org/linux-unix/chown-command-in-linux-with-examples/