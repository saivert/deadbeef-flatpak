# deadbeef-flatpak

DeaDBeeF stable build (currently version 1.8.0) does not support use of xdg-desktop-portal yet so currently only the the ~/Music folder (xdg-music) is made available. This will land in 1.8.1.

The master build manifest (music.deadbeef.player-master.json) builds DeaDBeeF with support for GtkFileChooserNative which gives portal access to single files. 

Portals does not currently support opening folders so opening .cue files this way is currently broken.

You can allow full filesystem and network share access by using overrides like so:

    $ flatpak --user override --filesystem=host --filesystem=xdg-run/gvfs music.deadbeef.player

This flatpak uses my improved pulseaudio output plugin and does not include the one included with DeaDBeeF by default, nor does it include ALSA.
