# Linux Mint Debian Edition - Errors

## X Session warning Unable to write to /temp X session may exit with an error
### Description
When I rebooted I got the error message "X Session warning Unable to write to /temp X session may exit with an error" when I entered my login information.

### Solution
Open the terminal with Ctrl+Alt+F1 and execute
```bash
sudo apt-get update
sudo apt-get install nemo
sudo apt-get install cinnamon
```
or

```bash
sudo apt-get install mint-meta-cinnamon
sudo reboot
```
### References
* https://forums.linuxmint.com/viewtopic.php?t=385154


## Menu is not shown in panel in Linux Mint Cinnamon 
* Go to panel settings
* Restore everythin by default

### References
* How to Reset & Restore Panel in Linux Mint Cinnamon | Taskbar: https://www.youtube.com/watch?v=XGA1ue9T7SY
