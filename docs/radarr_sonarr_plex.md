# Simple Deploy PTS-MHA
### Radarr Jackett Sonarr Plex Deployed.

**PTS is currently in maintenance mode and is considered feature complete.** From time-to-time developers will take it upon themselves to add new containers to Community-Apps as requested and update the Core-Apps whenever required.

We consider PTS to be a remarkable collaborative achievement and take pride in the fact we have built a solid foundation for any person to setup and learn basic Linux and also run a media server with minimal effort.

We encourage anyone wanting to contribute to the project in the future to join our community, this is also where we provide support: https://discord.gg/cKsMwMZ

Thanks to our valued contributors over the past couple of years, you have helped create something to be proud of and that will serve the community well into the future.

**You know who you are.** PTS is forever, others will come and go.

----

### What we have done.

We have deployed Plex Sonarr, Radarr and Jackett.
Other tools like portainer comes with PTS-MHA by default.

So you can access the plex at:.
```
http://<your server ip>:32400
```

For Sonarr:

```
http://<your server ip>:8989
```

For Radarr:

```
http://<your server ip>:7878
```

and for Jackett:

```
http://<your server ip>:9117
```

if you want to use a team drive fell free to ssh on it and.


Configure pts

```
sudo pts
```

then select `4` and follow the steps depending if you want to encrypt or not your data, i prefer it encrypted to prevent 3rd party read it.

### Configure remote paths for teamdrive(Google Drive Storage)

**Why do I need to change remote paths?**  

PTS will create one download folder for completed downloads using any NZB client `/mnt/downloads/nzb` and one download folder for completed downloads using any torrent client `/mnt/downloads/torrent`. Both folder names are different to those used in previous versions of PTS. This remote paths need to be changed in your configuration settings (nzbget/radarr/sonarr etc) which you can do in either in terminal or webUI.  

**NOTE**  PTS fork does **not** install PGUI by default.


**Important Info**

Copy and paste these mappings into your sonarr/radarr/lidarr config.
Keep the host all lowercase, it doesn't matter what you did, keep it lowercase!

**the paths must be 100% the same as we have listed here, again copy and paste.**

* DO NOT change or add additional folders or categories to the end of these paths!

* DO NOT change the host, do not add your domain url, leave it alone!

| Host        | Remote Path                 | Local Path                |
|-------------|-----------------------------|---------------------------|
| <span style="color:white">sabnzbd</span>     | <span style="color: white">/mnt/downloads/nzb/</span>         | <span style="color: white">/mnt/unionfs/nzb/         |
| <span style="color:black">nzbget</span>       | <span style="color: black">/mnt/downloads/nzb/</span>          | <span style="color: black">/mnt/unionfs/nzb/</span>         |
| <span style="color:white">qbittorrent | <span style="color: white">/mnt/downloads/qbittorrent/ | <span style="color: white">/mnt/unionfs/qbittorrent/ |
| <span style="color:black">rutorrent   | <span style="color: black">/mnt/downloads/torrent/     | <span style="color: black">/mnt/unionfs/torrent/     |
| <span style="color: white">deluge      | <span style="color: white">/mnt/downloads/deluge/      | <span style="color: white">/mnt/unionfs/deluge/      |