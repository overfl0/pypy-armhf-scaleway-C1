# pypy-armhf

## Building PyPy from source

https://doc.pypy.org/en/latest/build.html

## Cross compiling PyPy

https://rpython.readthedocs.io/en/latest/arm.html

## Download

https://github.com/overfl0/pypy-armhf/releases/download/1.0/pypy-7.2.0.2-armhf.tar.bz2

### Notes:

If you want to cross compile for Scaleway's C1 server, you will need to download the FS from a running server, instead of fetching one with debootstrap (or fetch it and then replace with Scaleway's). Otherwise, the built PyPy will work until you install pip and try installing any package (it will then segfault).
