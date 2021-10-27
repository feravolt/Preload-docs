# Preload
Preload application preloads data to RAM to significantly increase read speeds. It works both with and without ROOT access. Recommended to use only on devices with 6+ GB RAM.

    If you don't have ROOT access:
        - You can preload user apps (for OS 10 and below), files and folders - read speeds will be boosted (read data in cache - 'readahead' method)
        - You can't preload apps if you are on OS 11+ due to Scoped Storage
        - Preloaded data may be released by OS in a while (depends on amount of available RAM) and you will get regular read speeds
        - You don't need to care of unpreloading data - OS will handle it all automatically
        - App's RAM indicator may show incorrect values due to the system may quickly release preloaded data
        - Safe

    If you have ROOT access:
        - You can preload any user apps, files and folders on any supported OS version (read and lock data in RAM  - 'mlock' method)
        - Preloaded data will be kept in RAM as much long as you wish with boosted read speeds
        - You have to manually unpreload data if you want to free used RAM
        - Accurate app's RAM indicator
        - Possible risk of OOM in system - don't overload RAM with preload data

    > Without ROOT access app will preload data in RAM as cache. Cache is kept while there is enough free RAM. Once there is a need for more free RAM, system will free this cache.
    > With ROOT access app will preload data in RAM and lock them there. All preloaded data will be kept in RAM and won\'t be freed, unless you press the 'Unpreload' button, uninstall Preload app or reboot device.
    > While preloading files on OS 11+ open them from internal storage directory.
    > The circle indicator shows how much RAM is used/available for preload - memory measure method depends on the ROOT access availability.
    > While preloading apps, their cache files are ignored. If obb or files folders of the app are not fitting in RAM to preload - they will be skipped. Also avoid preloading files with special characters in name.
    > You can't preload data which are bigger in size than available RAM. Also 5-10% of available RAM is always reserved to avoid low available RAM and potential system lags.


