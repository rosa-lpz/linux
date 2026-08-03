# Debian

​              **Table 2.6. Basic package management operations with the commandline using** **[apt(8)](https://manpages.debian.org/unstable/apt(8)), [aptitude(8)](https://manpages.debian.org/unstable/aptitude(8)) and [apt-get(8)](https://manpages.debian.org/unstable/apt-get(8)) /[apt-cache(8)](https://manpages.debian.org/unstable/apt-cache(8))**            

| `apt` syntax                  | `aptitude` syntax          | `apt-get`/`apt-cache` syntax | description                                                  |
| :---------------------------- | :------------------------- | :--------------------------- | :----------------------------------------------------------- |
| `apt update`                  | `aptitude update`          | `apt-get update`             | update package archive metadata                              |
| `apt install foo`             | `aptitude install foo`     | `apt-get install foo`        | install candidate version of "`foo`" package with its dependencies |
| `apt upgrade`                 | `aptitude safe-upgrade`    | `apt-get upgrade`            | install candidate version of installed packages without removing any other packages |
| `apt full-upgrade`            | `aptitude full-upgrade`    | `apt-get dist-upgrade`       | install candidate version of installed packages while removing other packages if needed |
| `apt remove foo`              | `aptitude remove foo`      | `apt-get remove foo`         | remove "`foo`" package while leaving its configuration files |
| `apt autoremove`              | N/A                        | `apt-get autoremove`         | remove auto-installed packages which are no longer required  |
| `apt purge foo`               | `aptitude purge foo`       | `apt-get purge foo`          | purge "`foo`" package with its configuration files           |
| `apt clean`                   | `aptitude clean`           | `apt-get clean`              | clear out the local repository of retrieved package files completely |
| `apt autoclean`               | `aptitude autoclean`       | `apt-get autoclean`          | clear out the local repository of retrieved package files for outdated packages |
| `apt show foo`                | `aptitude show foo`        | `apt-cache show foo`         | display detailed information about "`foo`" package           |
| `apt search *regex*`          | `aptitude search *regex*`  | `apt-cache search *regex*`   | search packages which match *regex*                          |
| N/A                           | `aptitude why *regex*`     | N/A                          | explain the reason why *regex* matching packages should be installed |
| N/A                           | `aptitude why-not *regex*` | N/A                          | explain the reason why *regex* matching packages can not be installed |
| `apt list --manual-installed` | `aptitude search '~i!~M'`  | `apt-mark showmanual`        | list manually installed packages                             |

# References

* https://www.debian.org/doc/manuals/debian-reference/
* https://www.debian.org/doc/manuals/debian-reference/ch02.en.html#_debian_package_management_prerequisites



