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

