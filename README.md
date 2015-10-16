## About
This is a copy of the official Ubuntu docker creation script in https://github.com/tianon/docker-brew-ubuntu-core with the difference that this scripts create a 32bit variant of the container (useful for compilation). I made it as an alternative to https://github.com/docker-32bit/ubuntu which doesn't work very well.

## Usage:
run:

    ./update.sh trusty vivid wily precise

(Note: sudo is *not* necessary because the rootfs is downloaded and not generated)

## Result

    $ docker images
    REPOSITORY   TAG       IMAGE ID       CREATED          VIRTUAL SIZE
    ubuntu32     precise   28e622f77681   31 seconds ago   115 MB
    ubuntu32     vivid     f15a860d7d00   45 seconds ago   129.5 MB
    ubuntu32     wily      1eb8a08208f5   36 minutes ago   131.2 MB
    ubuntu32     trusty    1eb7e6ed0a7b   36 minutes ago   183.6 MB

## Usage

In a Dockerfile, you will now have to use

    FROM ubuntu32:wily

instead of

    FROM ubuntu:wily
