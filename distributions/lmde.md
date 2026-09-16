# Linux Mint Debian Edition

## Download 

* https://www.linuxmint.com/

 

## Installation instructions

* https://linuxmint-installation-guide.readthedocs.io/en/latest/



## Verify ISO Image

* https://linuxmint-installation-guide.readthedocs.io/en/latest/verify.html#

### Download the SHA256 sums provided by Linux Mint

All [download mirrors](https://www.linuxmint.com/mirrors.php) provide the ISO images, a `sha256sum.txt` file and a `sha256sum.txt.gpg` file. You should be able to find these files in the same place you downloaded the ISO image from.

If you can’t find them, browse the [Kernel.org download mirror](https://mirrors.kernel.org/linuxmint/stable/) and click the version of the Linux Mint release you downloaded.

Download both `sha256sum.txt` and `sha256sum.txt.gpg`.

Do not copy their content, use “right-click->Save Link As…” to download the files themselves and do not modify them in any way.

### Integrity check

To check the integrity of your local ISO file, generate its SHA256 sum and compare it with the sum present in `sha256sum.txt`.

```bash
sha256sum -b yourfile.iso
```

Compare with checksum: [SHA512SUMS](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/SHA512SUMS)



# References

* https://www.linuxmint.com/
* https://linuxmint-installation-guide.readthedocs.io/en/latest/
* https://linuxmint-installation-guide.readthedocs.io/en/latest/verify.html