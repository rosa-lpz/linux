# chgrp

* [Quick Reference](quick-reference)

## Quick Reference 

| Task                           | Command                   |
| ------------------------------ | ------------------------- |
| Change group of a file         | `chgrp GROUP file`        |
| Change group of multiple files | `chgrp GROUP file1 file2` |
| Use numeric GID                | `chgrp +1000 file`        |
| Verbose output                 | `chgrp -v GROUP file`     |
| Show only changed files        | `chgrp -c GROUP file`     |
| Suppress errors                | `chgrp -f GROUP file`     |
| Change symlink itself          | `chgrp -h GROUP symlink`  |
| Recursive change               | `chgrp -R GROUP /path`    |





# References

* https://www.geeksforgeeks.org/linux-unix/chgrp-command-in-linux-with-examples/
* https://linuxize.com/post/chgrp-command-in-linux/