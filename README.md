# Preload
Preload application preloads data to RAM to significantly increase read speeds. It works both with and without ROOT access. Recommended to use only on devices with 6+ GB RAM. App doesn't lock processes in RAM, files data only.


    >> Without ROOT access app will preload file data in RAM as cache ('readahead' method). Cache is kept while there is enough free RAM. Once there is a need for more free RAM, system will free this cache - in such case you will get lower read speed.
    >> Without ROOT access:
         — You can preload user apps (for OS 10 and below), files and folders - read speeds will be boosted
         — You can't preload apps if you are on OS 11+ due to Scoped Storage
         — Preloaded data may be released by OS in a while (depends on amount of available RAM) and you will get regular read speeds
         — You don't need to care of unpreloading data - OS will handle it all automatically
         — App's RAM indicator may show incorrect values due to the system may quickly release preloaded data
         — Possible restrictions due to OS permissions
         — Safe


    >> With ROOT access app will preload data in RAM and lock them there ('mlock' method). All preloaded data will be kept in RAM and won't be freed, unless you press the 'Unpreload' button, uninstall Preload app or reboot device.
    >> With ROOT access:
         — You can preload any user apps, files and folders on any supported OS version
         — Preloaded data will be kept in RAM as much long as you wish with boosted read speeds
         — You have to manually unpreload data if you want to free used RAM
         — Accurate app's RAM indicator
         — No possible OS permission restrictions
         — Possible risk of OOM in system. Don't overload RAM with preload data


    >> The indicator shows how much RAM is used/available for preload - memory measure method depends on the ROOT access availability.
    >> While preloading apps, their cache files are ignored. If obb or files folders of the app are not fitting in RAM to preload - they will be skipped. Also avoid preloading files with special characters in name.
    >> You can't preload data which is bigger in size than available RAM. Also 10% of available RAM is always reserved to avoid low available RAM and potential system lags.
    >> In order to automatically preload the desired app on system boot longpress on it in the list. Longpress on same app again to disable the feature.

# Use cases
Preload is a tool. And the usage scenario of this app is totally up to you. It readaheads(warmups)/locks data files in RAM of read-only files to reduce I/O jitters and highly increases read speed AND also reduces power consumption of MMC/UFS memory (yes, it's minimal but still, the slower is the memory - the better is the result). Few examples of usage:
- You're listening to music saved in internal memory. You can preload whole music folder (if enough RAM) and: 1) save battery due to no I/O with internal memory; 2) 0-delay playback/rewind due to read speed from RAM is ~10 times faster than from internal memory. Same applies to films/series to watch locally from internal memory.
- You play game which has _.obb_ (or similar read only file) cache in internal memory. You can preload the file itself from file picker or select the game from the app's list. If you have enough RAM to keep the game process and store it's preloaded files, this will give you the same - a bit of powersaving due to no I/O with internal memory and high increase in read speeds (faster textures, cache, media loading). With use of _[FDE.AI](https://github.com/feravolt/FDE.AI-docs)_ app this process can be automized.
- You use [Linux on Android](https://play.google.com/store/apps/details?id=ru.meefik.linuxdeploy) and install it internal memory as ~2GB _linux.img_ file. You preload it from file picker in app and you get your Linux on Android running as beast.
- You use your Android as NAS. YOu can preload the most frequently accessed data files/media to increase the access speed for other NAS users.

# FAQ
_— Why preloaded app is not locked in RAM and I can still close it from recents?_<br>
— Because Preload is not "lock process in RAM", it's "lock files in RAM".

_— Why read speed after preload is lower then before?_<br>
— Because you're low on awailable RAM. System starts to unload cache due to RAM pressure at the same time when you're preloading stuff. This is why the app is recommended on devices with at least 6GB RAM onboard.

_— Why I can't see any files in 'obb', 'data' and 'media' folders?_<br>
— Because of [Scoped Storage](https://developer.android.com/about/versions/11/privacy/storage) introduced by Google since Android 11. It blocks the access to this folders. You can still preload the contents of theese folders for each separate package if you have root access by preloading app from the apps list.

to be continued.
![Jokes Card](https://readme-jokes.vercel.app/api)<br>
