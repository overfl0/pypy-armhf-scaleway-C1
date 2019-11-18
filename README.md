# pypy-armhf

## Building PyPy from source

https://doc.pypy.org/en/latest/build.html

## Cross compiling PyPy

https://rpython.readthedocs.io/en/latest/arm.html

## Download

https://github.com/overfl0/pypy-armhf-scaleway-C1/releases/download/7.2.0/pypy3.6-v7.2.0-armhf.tar.bz2

### Notes:

If you want to cross compile for Scaleway's C1 server, you will need to download the FS from a running server, instead of fetching one with debootstrap (or fetch it and then replace with Scaleway's). Otherwise, the built PyPy will work until you install pip and try installing any package (it will then segfault).

## Commands

Note that these may not be 100% complete as I'm just dumping my bash_history here

    # TODO
    rsync -zavt --exclude dev --exclude home --inplace --progress root@your.scaleway.server.com:/ /srv/chroot/bionic_arm/
    # TODO
