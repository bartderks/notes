# DBeaver backup

For MacOS, copy the following folder to backup all connections, stored credentials etc.

```/Users/${USER}/Library/DBeaverData/workspace6/General/.dbeaver/```

If you move from Enterprise to Community Edition, the connections will not work after restoring the backup. Enterprise edition uses 'drivers' that are apparently not known in the 'Community' edition.

Had to re-create the connections..
