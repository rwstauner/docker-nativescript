# Docker Image for [NativeScript][nativescript] (for Android) development

[![docker-badge](http://dockeri.co/image/rwstauner/nativescript)](https://hub.docker.com/r/rwstauner/nativescript)

## Setup

### Simple

    docker pull rwstauner/nativescript
    docker tag  rwstauner/nativescript nativescript

### DIY

    git clone git@github.com:rwstauner/docker-nativescript.git
    cd docker-nativescript
    docker build -t nativescript .

### Alias

    alias tns='docker run -it --rm --device=/dev/bus/usb:/dev/bus/usb -v $HOME/.local/share/.nativescript-cli:/root/.local/share/.nativescript-cli -v $HOME/.android:/root/.android -v $HOME/.gradle:/root/.gradle -v $PWD:/src -e TERM=$TERM nativescript tns'

The alias command lets you use `tns` for running any command inside the nativescript container.

## Caveats

**NOTE**: This (the `/dev/bus/usb` trick) only works on a Linux host with an
Android device plugged in via USB (with USB Debugging enabled).

## New Project

    tns create hello
    cd hello
    tns platform add android
    tns run android

## References

Inspired by:
* https://github.com/oren/docker-nativescript
* https://github.com/Kallikrein/dockerfiles/tree/master/android-cordova
* https://github.com/beevelop/docker-android-nodejs

[nativescript]: https://www.nativescript.org/
