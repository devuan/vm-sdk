vm-sdk
=======

vm-sdk is simple distro build system aimed at creating Vagrant boxes
and other virtual machines.

## Requirements

vm-sdk is designed to be used interactively from a terminal.
It requires the following packages to be installed in addition to the
[dependencies required for libdevuansdk](https://github.com/dyne/libdevuansdk/blob/master/README.md#requirements).

`sudo` permissions are required for the user that is running the build.

### Devuan

```
virtualbox vagrant qemu qemu-utils
```
* http://download.virtualbox.org/virtualbox/5.1.30/virtualbox-5.1_5.1.30-118389~Debian~stretch_amd64.deb
* http://download.virtualbox.org/virtualbox/5.1.30/virtualbox-5.1_5.1.30-118389~Debian~jessie_amd64.deb

* https://releases.hashicorp.com/vagrant/2.0.0/vagrant_2.0.0_x86_64.deb

### Gentoo
```
app-emulation/virtualbox app-emulation/vagrant app-emulation/qemu
```

## Initial setup

After cloning the vm-sdk git repository, enter it and issue:

```
git submodule update --init
```

### Updating

To update vm-sdk, go to the root dir of the git repo and issue:

```
git pull && git submodule update --init --recursive
```

## Quick start

Edit the `config` file to match your needs. Sensible defaults are
already there. Then run zsh. To avoid issues, it's best to start a
vanilla version, without preloaded config files so it doesn't cause
issues with libdevuansdk/vm-sdk functions.

```
; zsh -f -c 'source sdk'
```

Now is the time you choose the OS and (optionally) a blend you want
to build the image for.

### Currently supported distros

* `devuan`

```
; load devuan
```

Once initialized, you can run the helper command:

```
; build_vagrant_dist
```

The image will automatically be build for you. Once finished, you will be
able to find it in the `dist/` directory in vm-sdk's root.

For more info, see the `doc/` directory.

## Acknowledgments

Devuan's SDK was originally conceived during a period of residency at the
Schumacher college in Dartington, UK. Greatly inspired by the laborious and
mindful atmosphere of its wonderful premises.

The Devuan SDK is Copyright (c) 2015-2017 by the Dyne.org Foundation

Devuan SDK components were designed, and are written and maintained by:

- Ivan J. <parazyd@dyne.org>
- Denis Roio <jaromil@dyne.org>
- Enzo Nicosia <katolaz@freaknet.org>

This source code is free software: you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the Free
Software Foundation, either version 3 of the License, or (at your option)
any later version.

This software is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY
or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for
more details.

You should have received a copy of the GNU General Public License along
with this source code. If not, see <http://www.gnu.org/licenses/>.
