# Debian



## Debian 13 freezes after updates

Debian 13 (Trixie) freezes after updates are typically caused by **incompatible kernel versions** or **broken NVIDIA driver modules** due to missing kernel headers.

*   **Kernel Freezes**: Specific kernels like **6.12.30** and **6.12.69** have been reported to cause system hangs or boot failures. Users have resolved this by **downgrading to kernel 6.11.10** or using the backports kernel **6.18.5**.
*   **NVIDIA Driver Failures**: Updates often fail to install necessary kernel headers, causing the NVIDIA DKMS modules to fail during boot. The fix is to manually install headers and rebuild drivers:
    ```bash
    sudo apt install linux-headers-amd64
    sudo dkms autoinstall
    ```
*   **Boot/Restore Corruption**: Restoring backups or certain updates can corrupt the **initramfs**, causing freezes after the GRUB menu. Rebuilding the initramfs from a live environment resolves this:
    ```bash
    sudo update-initramfs -u -k all
    ```
*   **Workarounds**: For Intel hardware freezes, adding **`intel_iommu=igfx_off`** to GRUB kernel parameters can help. For networking-related service hangs, adding **`up /usr/lib/ifupdown/settle-dad.sh`** to `/etc/network/interfaces` is a known workaround for IPv6 issues.