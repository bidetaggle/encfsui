## ENCRYPTED FILESYSTEM [ENCFS](http://www.arg0.net/encfs) GUI WRAPPER

This bash script provides a simple gui around the
[encfs](http://www.arg0.net/encfs) command line utility to mount
and unmount an encrypted directory. This script requires
[encfs](http://www.arg0.net/encfs),
[zenity](http://live.gnome.org/Zenity), and
[xdg-open](http://portland.freedesktop.org/wiki/).

Whenever you want to mount your private directory, you click on the
desktop launcher. The launcher runs the script with appropriate
directory arguments. The script uses
[zenity](http://live.gnome.org/Zenity) to prompt you for the passphrase
and then mounts the [encfs](http://www.arg0.net/encfs) directory.
If you click on the launcher when the private directory is already mounted, then
you are prompted to unmount it. There
are some other options, see usage below.

I only use a single encrypted directory under my home directory. My
motivation for creating this script is to give quick single click access
from my desktop to that encrypted directory. I do not want my passphrase
cached anywhere, and I want an easy single click way to close off access.

A sample desktop launcher file (`encfsui.desktop`) is included.

Home: <http://github.com/bulletmark/encfsui>  
Author: Mark Blakeney, <markb@berlios.de>

### PREREQUISITES

Requires bash + encfs + zenity + xdg-open. For ubuntu, xdg-open is part
of xdg-utils and is installed by default. E.g. for ubuntu, you can
install [encfs](http://www.arg0.net/encfs) and
[zenity](http://live.gnome.org/Zenity) with the following command:

    sudo apt-get install encfs zenity

### INSTALLATION

Unpack this archive, or pull a copy the sources, and then type:

    sudo make install

which copies encfsui to `/usr/local/bin`. Alternately, just copy
`encfsui` anywhere in your path, e.g. to `~/bin`.

Copy the sample `encfsui.desktop` file to your
`~/.local/share/applications/` etc.

On a freedesktop.org compliant system such as recent Gnome or KDE,
copy `encfsui.desktop` to `/usr/share/applications` (accessible
to everybody) or to `~/.local/share/applications` (accessible to you only).
Then, e.g. on Ubuntu Unity or Gnome Shell, you can search for encfsui in your
applications list and drag add it to your Unity or Gnome Shell launcher.

Of course you can create multiple encfs source + target directories,
each with a corresponding desktop launcher if you want.

### USAGE

    encfsui [-options] source_enc_dir target_mount_dir

    GUI utility to mount source_enc_dir to target_mount_dir.
    If target already mounted then it will be unmounted instead.

    Options:
    -i <mins> specify idle timeout mins
    -p (make public mount, can only be done by root)
    -o (don't open target dir in gui mode)

### LICENSE

Copyright (C) 2010, 2011 Mark Blakeney. This program is distributed under the
terms of the GNU General Public License.

This program is free software: you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the
Free Software Foundation, either version 3 of the License, or any later
version.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General
Public License at <http://www.gnu.org/licenses/> for more details.
