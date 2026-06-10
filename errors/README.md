# Errors

Debian Sleep Not Working

**Debian sleep issues often stem from BIOS incompatibility, insufficient swap space for hibernation, or conflicting display manager settings.** If the system fails to wake, try setting `SYSTEMD_SLEEP_FREEZE_USER_SESSIONS=false` in `/etc/systemd/systemd-suspend.service` or updating the initramfs with `sudo update-initramfs -u -k all`. For systems that go to sleep unintentionally, mask the targets using `sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target` or edit `/etc/gdm3/greeter.dconf-defaults` to set `sleep-inactive-ac-type='blank'`.

**Troubleshooting steps include:**
*   **Check Swap Space**: Ensure swap size is at least equal to system memory for hibernation; add `resume=/swapfile` to `GRUB_CMDLINE_LINUX_DEFAULT` if using a swap file.
*   **BIOS Settings**: Disable "C States" or "Sleep states" in BIOS if kernel versions fail to wake from deep sleep.
*   **Driver Conflicts**: Install latest Nvidia drivers and ensure `nvidia-persistenced` is running; check `dmesg` for GPU errors after waking.
*   **Service Conflicts**: Remove `light-locker` or switch to `lightdm` if screen locking prevents waking.

**To prevent unwanted sleep, create a custom configuration file at `/etc/systemd/sleep.conf.d/disable-suspend-hibernate.conf`** with the following content:
```ini
[Sleep]
AllowSuspend=no
AllowHibernation=no
AllowSuspendThenHibernate=no
AllowHybridSleep=no
```
*Note: This method works on Debian 10 and newer, but Debian 12 may still require editing GDM settings.*