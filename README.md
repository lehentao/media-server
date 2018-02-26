## References
- Plex container: https://github.com/plexinc/pms-docker
- Subliminal:
- Flexget: 

## Parameters
###### Plex
- `<path/to/transcode/temp>` The path where you wish Plex Media Server to store its configuration data.  This database can grow to be quite large depending on the size of your media collection.  This is usually a few GB but for large libraries or libraries where index files are generated, this can easily hit the 100s of GBs.  If you have an existing database directory see the section below on the directory setup. **Note**: the underlying filesystem needs to support file locking. This is known to not be default enabled on remote filesystems like NFS, SMB, and many many others.  The 9PFS filesystem used by FreeNAS Corral is known to work but the vast majority will result in database corruption.  Use a network share at your own risk.
- `<path/to/transcode/temp>` The path where you would like Plex Media Server to store its transcoder temp files.  If not provided, the storage space within the container will be used.  Expect sizes in the 10s of GB.
- `<path/to/media>` This is provided as examples for providing media into the container.  The exact structure of how the media is organized and presented inside the container is a matter of user preference.  You can use as many or as few of these parameters as required to provide your media to the container.
- `<time/zone>` Set the timezone inside the container.  For example: `Europe/London`.  The complete list can be found here: [https://en.wikipedia.org/wiki/List_of_tz_database_time_zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)
- `<plex_claim>` The claim token for the server to obtain a real server token.  If not provided, server will not be automatically logged in. If server is already logged in, this parameter is ignored.  You can obtain a claim token to login your server to your plex account by visiting [https://www.plex.tv/claim](https://www.plex.tv/claim)
