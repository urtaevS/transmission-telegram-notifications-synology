# Bash script that sends a message to the telegram bot after the transmission finishes downloading a torrent. (changed README for synology nas)

#### Bash script [here](https://github.com/ricardotx/transmission-telegram-notifications/blob/master/src/transmission_telegram_notification.sh)

### Instructions:

 * Put the script in a folder at your choice

 * Stop tansmission-deamon service

    `sudo synopkg stop transmission`
    
    or stop from Web UI

 * Allow the execution of the script

    `sudo chmod +rx transmission_telegram_notification.sh`

 * Open the transmission-daemon settings file

     `sudo nano /volume1/@appstore/transmission/var/settings.json`
     
     or
     
     `sudo vim /volume1/@appstore/transmission/var/settings.json`

    Change the following:
      ```json
       "script-torrent-done-enabled": true,
       "script-torrent-done-filename": "/your/script/path",
      ```

  * Save the changes and start the transmission-daemon service
     
     `sudo synopkg start transmission`
     
     or start from Web UI

**Note:** *Those variables are inherited from Transmission*
    
  * `TR_APP_VERSION`
  * `TR_TIME_LOCALTIME`
  * `TR_TORRENT_DIR`
  * `TR_TORRENT_HASH`
  * `TR_TORRENT_ID`
  * `TR_TORRENT_NAME`
