# deadbeef-flatpak

DeaDBeeF static build is not built to support use of xdg-desktop-portal yet so currently only the the ~/Music folder (xdg-music) is made available.

The master build manifest (music.deadbeef.player-master.json) builds DeaDBeeF with support for GtkFileChooserNative which gives portal access to single files. 

Portals does not currently support opening folders so opening .cue files this way is currently broken.

You can allow full filesystem and network share access by using overrides like so:

    $ flatpak --user override --filesystem=host --filesystem=xdg-run/gvfs music.deadbeef.player

