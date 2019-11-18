# pypy3.6-v7.2.0-armhf for Scaleway's C1 server

## Download

https://github.com/overfl0/pypy-armhf-scaleway-C1/releases/download/7.2.0/pypy3.6-v7.2.0-armhf.tar.bz2

## Building PyPy from source

https://doc.pypy.org/en/latest/build.html

## Cross compiling PyPy

https://doc.pypy.org/en/release-2.4.x/arm.html

### Notes:

After trying (and failing) several methods to build PyPy for Scaleway's C1 servers, I finally obtained a working executable by using something that's probably the most time-consuming method:

I created an armv7 chroot on a x86_64 linux machine, overwrote it with original files from a real C1 server, and built PyPy from source, inside it. See links above for more details on how to do that. If you want to build it yourself, expect the compilation to take around 8 (eight) hours!

Note that if you want to compile PyPy for Scaleway's C1 server, you will need to download the FS from a real server, instead of using the one created by debootstrap. Otherwise, the built PyPy will work until you install pip and try installing any package (it will then segfault). No idea why and I didn't have time to investigate further. I've already spent too much time on that "project" anyway.

Also note that **you cannot compile PyPy this way inside a WSL1 linux** as the build process will crash at the very end, on the last step (7 hours down the drain, yay!). You may have more luck with WSL2, which emulates all the linux syscalls better.

## Commands

Note that these may not be 100% complete as I'm just dumping my bash_history here

    # TODO
    rsync -zavt --exclude dev --exclude home --inplace --progress root@your.scaleway.server.com:/ /srv/chroot/bionic_arm/
    # TODO
