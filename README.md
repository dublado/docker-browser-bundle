# Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [How it works](#how-it-works)
- [Upgrading](#upgrading)
- [Uninstallation](#uninstallation)

# Introduction

Dockerized google-chome and tor-browser with audio support via pulseaudio and does not required any complicated setup.

The image does require pulseaudio for audio support which is installed on all major linux distributions out of the box.

![browser](https://cloud.githubusercontent.com/assets/410147/4377777/2ccda3d2-4352-11e4-9314-122e4f58a30c.gif)

# Installation

Install the wrapper scripts using:

```bash
docker run -it --rm -v /usr/local/bin:/target \
sameersbn/browser-bundle:latest install
```

This will install wrapper scripts to launch

- `google-chome`
- `tor-browser`

**If the application being launched is already installed on the host, then the host command is executed and the docker image is not started.**

# Use Cases

`tor-browser`
- Protects your anonymity on the internet.
- Access websites your ISP has blocked.

`google-chrome`
- Guest access????

# How it works

The wrapper scripts volume mount the X11 and pulseaudio sockets in the launcher container. The X11 socket allows for the user interface display on the host, while the pulseaudio socket allows for the audio output to be rendered on the host.

# Upgrading

To upgrade to newer releases, simply update the image

```
docker pull sameersbn/browser-bundle:latest
```

# Uninstallation

```bash
docker run -it --rm -v /usr/local/bin:/target \
sameersbn/browser-bundle:latest uninstall
```

# References

- http://fabiorehm.com/blog/2014/09/11/running-gui-apps-with-docker/
