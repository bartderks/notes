# SSH to older devices

When starting SSH session to older devices, it's possible you get the following error:

```
Unable to negotiate with XXX.XXX.XXX.XXX port 22: no matching key exchange method found. Their offer: diffie-hellman-group1-sha1,diffie-hellman-group14-sha1,kexguess2@matt.ucc.asn.au
```

This is due to the SSH client not wanting to use older key exchange mechanisms. Had this issue with a Unifi device with old firmware.

Specify the following options in the ```ssh``` command to make use of these older mechanisms:

```
ssh -oKexAlgorithms=+diffie-hellman-group1-sha1 -oHostKeyAlgorithms=+ssh-rsa -c 3des-cbc ubnt@XXX.XXX.XXX.XXX
```

This should make the connection work. Pointed the Unifi device to a new controller and updated the firmware. After the firmware update, the default ssh command (with the newer key exchange mechanisms) worked again.
