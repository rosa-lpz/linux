
# Keyboard shortcuts

## Terminal keyboard shortcuts 

Ctrl + Alt + T | Alt+F2 | Ctrl+Alt+F1	Launch Terminal
Shift + Ctrl + T	New tab
Shift + Ctrl + W	Close tab
Shift + Ctrl + N	New window
Shift + Ctrl + Q	Close window
Shift + Ctrl + C	Copy
Shift + Ctrl + V	Paste
Ctrl + +	Zoom in on current page
Ctrl + –	Zoom out on current page
Ctrl + 0	Zoom to default
F11	Full screen
Shift + Ctrl + F	Find
Shift + Ctrl + G	Find next
Shift + Ctrl + H	Find previous
Shift + Ctrl + J	Clear highlight

https://www.reallinuxuser.com/great-keyboard-shortcuts-for-linux-mint-cinnamon/
 

# Errors

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
https://forums.linuxmint.com/viewtopic.php?t=385154
