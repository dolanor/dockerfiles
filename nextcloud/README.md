# Nextcloud

Since the few last version of nextcloud server (v15, v16), I can't synchronize my files correctly with the desktop app.
So I reinstalled an older version that worked with the previous auth system. This auth system seems to still be present in the latest servers.
So this version running in docker still works. Yay.

# Run

```
docker run -d --name nextcloud \
# save the config in some persistent directory
-v ~/var/nextcloud:/root/.local/share/data/Nextcloud \
# the directory that you're really gonna synchronize
-v ~/cloud:/data \
# some various environment + volumes for making it work with host X11 server
-e DISPLAY=unix$DISPLAY -v /etc/localtime:/etc/localtime:ro -v /tmp/.X11-unix:/tmp/.X11-unix \
dolanor/nextcloud:2.3.2-utf8 nextcloud
```

# Launching the UI

If the nextcloud client is already running in the background with docker, you can still access the UI.
(even though I didn't figure out how to display the systray icon)o

```
docker exec nextcloud nextcloud
```
Now you can select the directories you want to synchronize, or desynchronize, or watching synchronizing status. 

# Limitations

I don't know how to make a dockerized process able to display a systray icon on the host.
If you know, PR accepted!
