# Preload
Please read this text before using the app.
Preload application preloads data to RAM to increase read speeds. It works both with and without ROOT access. Recommended to use only on devices with 6+ GB RAM. App doesn't lock processes in RAM, files only.


    >> Without ROOT access the app will preload file data in RAM as cache ('readahead' method). The cache is kept while there is enough free RAM. Once the system needs more free RAM, it will free this cache.
    >> Without ROOT access:
         — You can preload user apps (for OS 10 and below), files and folders - read speeds will be boosted
         — You can't preload apps if you are on OS 11+ due to the system limitations
         — Preloaded data (cache) may be released by OS in a while (depends on amount of available RAM)
         — You don't need to care about unpreloading data - OS will handle it automatically
         — App's RAM indicator may show incorrect values due to the system quickly releasing cache
         — Possible restrictions due to OS permissions


    >> With ROOT access the app will preload files in RAM and lock them there ('mlock' method). All data will be kept in RAM and won't be freed, unless you press the 'Unpreload' button, uninstall the app or reboot the device.
    >> With ROOT access:
         — You can preload any user apps, files and folders on any supported OS version
         — Preloaded data will be kept in RAM as much long as you wish with boosted read speeds
         — You have to manually unpreload data if you want to free used RAM
         — Accurate app's RAM indicator
         — No possible OS permission restrictions
         — On supported kernels OOM score adjustment will be applied for preloaded app process
         — Possible risk of running out of memory. Don't overload RAM with preload data


    >> The indicator shows how much RAM is used/available for preload - measuring method depends on the ROOT access availability.
    >> While preloading apps, their cache is ignored. If obb or files folders of the app wouldn't fit in RAM, they will be skipped. Also avoid preloading files with special characters in names.
    >> You can't preload data that is bigger than available RAM. Also 10% of available RAM is reserved to avoid low RAM causes and stutters.
    >> Swipe left on an app to enable or disable its preloading on boot.

# Use cases
Preload is a tool. And the usage scenario of this app is totally up to you. It readaheads(warmups)/locks data files in RAM of read-only files to reduce I/O jitters and highly increases read speed AND also reduces power consumption of MMC/UFS memory (yes, it's minimal but still, the slower is the memory - the better is the result). Few examples of usage:
- You're listening to music saved in internal memory. You can preload whole music folder (if enough RAM) and: 1) save battery due to no I/O with internal memory; 2) 0-delay playback/rewind due to read speed from RAM is ~10 times faster than from internal memory. Same applies to films/series to watch locally from internal memory.
- You play game which has _.obb_ (or similar read only file) cache in internal memory. You can preload the file itself from file picker or select the game from the app's list. If you have enough RAM to keep the game process and store it's preloaded files, this will give you the same - a bit of powersaving due to no I/O with internal memory and high increase in read speeds (faster textures, cache, media loading). With use of _[FDE.AI](https://github.com/feravolt/FDE.AI-docs)_ app this process can be automized.
- You use [Linux on Android](https://play.google.com/store/apps/details?id=ru.meefik.linuxdeploy) and install it internal memory as ~2GB _linux.img_ file. You preload it from file picker in app and you get your Linux on Android running as beast.
- You use your Android as [NAS](https://en.wikipedia.org/wiki/Network-attached_storage) or [DLNA](https://en.wikipedia.org/wiki/Digital_Living_Network_Alliance). You can preload the most frequently accessed data files/media to increase the access speed for other users.

# FAQ
_— Why preloaded app is not locked in RAM and I can still close it from recents?_<br>
— Because Preload is not "lock process in RAM", it's "lock files in RAM".

_— Why read speed after preload is lower then before?_<br>
— Because you're low on awailable RAM. System starts to unload cache due to RAM pressure at the same time when you're preloading stuff. This is why the app is recommended on devices with at least 6GB RAM onboard.

_— Why I can't see any files in 'obb', 'data' and 'media' folders?_<br>
— Because of [Scoped Storage](https://developer.android.com/about/versions/11/privacy/storage) introduced by Google since Android 11. It blocks the access to this folders. You can still preload the contents of theese folders for each separate package if you have root access by preloading app from the apps list.

_— What if I uninstall Preload app while there is some preloaded data_<br>
— It will be automatically unpreloaded within 10 seconds - there is a fuse for that. In worst case just reboot your device.

to be continued.
<br><br>![Jokes Card](https://readme-jokes.vercel.app/api)<br>

