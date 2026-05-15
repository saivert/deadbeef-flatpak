# deadbeef-flatpak

This is my experimental flatpak manifest for building DeadBeef music player as a flatpak.

# Notes

DeaDBeeF support building with GTKNativeFileChooser which is utilized to support flatpak portals. Other than that the xdg-music (~/Music) folder is made available by default so it is not fully sandboxed.

Portals does now support opening folders, but there is still no logic to automatically request both files in a cue/mp3 set (or similar). Opening a folder containing such a set does work but is counterintuitive. xdg-desktop-portals project is looking into this. Follow this [issue](https://github.com/flatpak/xdg-desktop-portal/issues/463) for more updates.

You can allow full filesystem and network share access by using overrides like so:

    $ flatpak --user override --filesystem=host --filesystem=xdg-run/gvfs music.deadbeef.player

Or with graphical tools like Flatseal.

This flatpak uses my improved pulseaudio output plugin and does not include the one included with DeaDBeeF by default, nor does it include ALSA.

It supports pipewire natively as well if selected under output plugin settings.

