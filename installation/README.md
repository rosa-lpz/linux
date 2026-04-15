# Debian

## Download 

* https://www.debian.org/download

This is Debian 13, codenamed *trixie*, netinst, for 64-bit PC (amd64) [debian-13.4.0-amd64-netinst.iso](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-13.4.0-amd64-netinst.iso).



## Verify iso:

Download checksum: [SHA512SUMS](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/SHA512SUMS) [Signature](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/SHA512SUMS.sign)

In terminal

```bash
cd Downloads
sha256sum debian-13.4.0-amd64-netinst.iso
sha512sum debian-13.4.0-amd64-netinst.iso
```

Compare with checksum: [SHA512SUMS](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/SHA512SUMS)

**References**

* https://www.debian.org/download

* https://www.thelinuxvault.net/blog/how-to-verify-an-authenticity-of-downloaded-debian-iso-images/#step-2-verify-integrity-with-sha256-checksum

# Drivers

## NVIDIA
### Prerequisites
#### apt components

Make sure that components contrib, non-free and non-free-firmware are enabled at least for the base (bookworm, trxie, fortky etc) and -security suites in your /etc/apt/sources.list file. For example for Trixie you should have at least entries similar to the two below: (the order of components does not matter)
```bash
deb http://deb.debian.org/debian/ trixie main contrib non-free non-free-firmware
deb http://security.debian.org/debian-security/ trixie-security contrib non-free main non-free-firmware
```
...and often also for -updates:

```bash
deb http://deb.debian.org/debian/ trixie-updates non-free-firmware non-free contrib main
```

If any entry in /etc/apt/sources.list related to the official Debian suites (like trixie, trixie-security in case of Trxie and possibly also trixie-updates and trixie-backports if you use them) misses any of the mentioned components, append them accordingly.

If you have corresponding deb-src entries configured, it is recommended to add the components to them as well.

Afterwards run
```bash
# apt update
```
This will fetch information about the new components from remote Debian repositories.

You can see SourcesList for more information on configuring apt sources.

#### Kernel headers
In standard cases you can just ask apt to install linux-headers-generic virtual package and it will pick the right blend for you:
```bash
# apt install linux-headers-generic
```
This will install for example linux-headers-amd64 if you have an AMD/Intel CPU or linux-headers-arm64 if you have an ARM CPU.

If you use some special features kernel like -rt or -cloud, you may need to manually point the corresponding -rt/-cloud headers instead of the standard ones mentioned above:
```bash
# apt install linux-headers-rt-amd64
```
ToDo: verify if apt cannot figure that out via linux-headers-generic.

### Debian 13 "Trixie"

550.xx.yy series
This version series supports Maxwell, Pascal, Volta, Turing, Ampere and Ada/Hopper GPUs, it does not support Blackwell (the full list of supported devices). For older devices, use nouveau, which should be already installed and in use. For Blackwell consider other packaging methods.

Note: this version will not work with kernels 6.16 or newer like the current one from trixie-backports: use the the corresponding version from trixie-backports instead.

Choose a flavor to install:

To install the proprietary flavor, packages nvidia-kernel-dkms and nvidia-driver should be installed:
```bash
# apt install nvidia-kernel-dkms nvidia-driver
```
To instead install the open flavor, packages nvidia-open-kernel-dkms and nvidia-driver should be installed:
(reminder: Maxwell, Pascal and Volta GPUs are not supported by this flavor)

```bash
# apt install nvidia-open-kernel-dkms nvidia-driver
```
DKMS will build the modules for your system from either nvidia-kernel-dkms or nvidia-open-kernel-dkms package.

Proceed to post-installation steps.


### References
* The Easiest Way to Install Nvidia Drivers on Debian in 2024 No More Headaches!: https://youtu.be/aYhWcJo1Zf8
* HOWTO INSTALACIÓN paso a paso NVIDIA repos Drivers en Debian 13 Trixie (lo que nadie te cuenta):https://youtu.be/v_Ly1s-Qgio
