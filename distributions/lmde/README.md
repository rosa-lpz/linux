## [Linux Mint Debian Edition](lmde/)
* [Keyboard shortcuts](lmde/keyboard-shorcuts/)
* [Errors](lmde/errors)



 # Install a Package

 
sudo apt install ./vs-code.deb


# Enable Root Login
* https://forums.linuxmint.com/viewtopic.php?t=463938

1. Setting > Login Window > Users > Allow manual login.
2. sudo passwd root, set password for the root account
3. sudo passwd -u root , output should be "passwd: password expiry information changed"
4. Restart machine
5. Click the "Login" option on the login screen
6. Type username root
7. Type password you selected in step 2
