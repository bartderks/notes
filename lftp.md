# lftp

When using lftp towards a ftps server (with self-signed certificate) you can disable the certificate check by issuing the following command (on lftp cli):

```
set ssl:verify-certificate false
```

To permanently disable it, add the same line to the following file:

```
~/.lftprc
```
