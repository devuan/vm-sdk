vm-sdk
======

vm-sdk is simple distro build system aimed at creating Vagrant boxes
and other virtual machines.

## Requirements

vm-sdk is designed to be used interactively from a terminal.
It requires the following packages to be installed in addition to the
[dependencies required for libdevuansdk](https://github.com/dyne/libdevuansdk/blob/master/README.md#requirements).

`sudo` permissions are required for the user that is running the build.

### Devuan

```
qemu qemu-utils


### Gentoo

```
app-emulation/qemu
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
; build_vm_dist
```

The image will automatically be build for you. Once finished, you will be
able to find it in the `dist/` directory in vm-sdk's root.
