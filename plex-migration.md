# Migrate Plex library from one deployment to another

Migrated Plex from a Windows environment to a LXC on Proxmox. Wanted to keep library(settings/data) like watched/unwatched, 'up next', etc.

Location of Plex data on different environments is documented here: https://support.plex.tv/articles/202915258-where-is-the-plex-media-server-data-directory-located/

Steps taken to migrate successfully:
* Stop Plex service on Windows environment
* Stop Plex service within Proxmox LXC (SSH to LXC and execute ```systemctl stop plexmediaserver```)
* On Windows, zip content of following directory (exclude 'Cache' directory): %LOCALAPPDATA%\Plex Media Server
* Move zip file to Plex LXC (sFTP)
* Plex data location (Plex Media Server folder) in the LXC: /var/lib/plexmediaserver/Library/Application Support/
* From this directory, tar current directory to have a backup: ```tar --exclude='./Plex Media Server/Cache' -zcvf plexserver-lxc.tar.gz "./Plex Media Server"```
* Remove everything from 'Plex Media Server' folder: ```cd /var/lib/plexmediaserver/Library/Application\ Support/Plex\ Media\ Server/ && rm -rf *```
* Move Windows backup to 'Plex Media Server' folder: ```mv /root/plexserver-win.zip /var/lib/plexmediaserver/Library/Application\ Support/Plex\ Media\ Server/```
* Unzip everything: ```cd /var/lib/plexmediaserver/Library/Application\ Support/Plex\ Media\ Server/ && unzip plexserver-win.zip```
* Make sure plex user has correct rights: ```cd /var/lib/plexmediaserver/Library/Application\ Support/Plex\ Media\ Server/ && chown -R plex:plex *```
* Start Plex: ```systemctl start plexmediaserver```
* Connect to Plex through your web browser and make sure you re-configure the location of each library to the correct mount point in the LXC
* Enjoy!
