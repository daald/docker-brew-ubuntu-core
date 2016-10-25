## About
This is a copy of the official Ubuntu docker creation script in https://github.com/tianon/docker-brew-ubuntu-core with the difference that this scripts create a 32bit variant of the container (useful for compilation). I made it as an alternative to https://github.com/docker-32bit/ubuntu which doesn't work very well.

## Usage:
run:

    ./update.sh trusty wily precise xenial

(Note: sudo is *not* necessary because the rootfs is downloaded and not generated)

## Result

    $ docker images
    REPOSITORY   TAG       IMAGE ID       CREATED          SIZE
    ubuntu32     xenial    b9d83c58c531   4 minutes ago    126.6 MB
    ubuntu32     precise   43ba054779c9   4 minutes ago     92.86 MB
    ubuntu32     wily      be9db443ac78   4 minutes ago    135.1 MB
    ubuntu32     trusty    e512c5ca1c0d   4 minutes ago    177.7 MB


## Usage

In a Dockerfile, you will now have to use

    FROM ubuntu32:wily

instead of

    FROM ubuntu:wily

If you want to run the container directly, simply type:

    $ docker run ubuntu32:wily uname -m
    i686
