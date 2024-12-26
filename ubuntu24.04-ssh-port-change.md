# How to change SSH port on Ubuntu 24.04

The process I used to know to modify the SSH port on a Linux machine was by editing the /etc/ssh/sshd_config file.

Apparently, since Ubuntu 22.04, the way to modify the SSH port was changed. [1]

Steps executed to successfully change port:
1. Edit file `/usr/lib/systemd/system/ssh.socket`
2. Under `[Socket]`, change `ListenStream` parameter to desired port
3. Restart ssh service by command `systemctl restart ssh.socket`
4. Make sure you use ssh.socket otherwise it doesn't work..

Obviously, make sure new port is allowed in firewall config. Using `ufw`:

`ufw allow <PORT>/tcp`

[1] https://askubuntu.com/questions/1439461/ssh-default-port-not-changing-ubuntu-22-10-and-later
