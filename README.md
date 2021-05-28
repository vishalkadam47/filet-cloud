# filet-cloud
A lean slice of Cloud Storage

This project attempts to make a sofisticated personal cloud storage solution similar to the google-drive ecosystem, using the design philosophies of the filet project series. This project will hopefully contain little code, and rather bring together existing technologies into a simple project.

It will target a single build running on a Raspberry Pi.

## Hardware
The following hardware was used for this build:
* Raspberry Pi 4B 4GB https://www.raspberrypi.org/products/raspberry-pi-4-model-b/
* 32GB Transcend microSDXC/SDHC 300S https://www.transcend-info.com/Products/No-948
* Seagate 5TB Basic Portable External Drive https://www.seagate.com/gb/en/products/external-hard-drives/basic-external-hard-drive/
* 2.7inch Mono E-Ink display (with 4 buttons) https://www.waveshare.com/wiki/2.7inch_e-Paper_HAT

## Setup
### Basic Host Setup
* Install Raspberry Pi OS to a microSD card (https://www.raspberrypi.org/software/)
* Enable ssh on your Pi (https://www.raspberrypi.org/documentation/remote-access/ssh/)
* Make a better password for the pi user (https://www.raspberrypi.org/documentation/configuration/security.md)
* Set up WiFi if needed (https://www.raspberrypi.org/documentation/configuration/wireless/).
* If you intend to connect from outside your local network, setup port forwarding for port 22 (https://en.wikipedia.org/wiki/Port_forwarding), static DHCP, and dynamic DNS, if needed (https://wiki.archlinux.org/title/Dynamic_DNS).
* Ensure you have connected power, network, an empty USB drive to store the data, inserted the SD Card, and disconnected all other USB drives, then power on.

### USB Drive Setup
* Format the USB drive (for the data) as btrfs (https://wiki.archlinux.org/title/Btrfs).

### Filet-Cloud Installation
```bash
ssh raspberrypi.local
git clone https://github.com/fuglaro/filet-cloud.git
sudo filet-cloud/install
```
### Create New Login Account:
```bash
filet-cloud-new-user
```

## Compatible Clients
* Android filebrowser - Solid Explorer
* Android filebrowser (opensource) - Ghost Commander (with SFTP plugin)
* Android filesyncer - FolderSync
* Linux filebrowser client - Filezilla

## TODO and Missing Features
* Guide for interacting from Android, Windows, Linux etc.
* Web Page server.
* Snapshot count indicator on hat.
* Replace python code with C code (to work better on lower spec machines like the PiZero W)


## Design and Engineering Philosophies

This project explores how far a software product can be pushed in terms of simplicity and minimalism, both inside and out, without losing powerful features. Window Managers are often a source of bloat, as all software tends to be. *filetwm* pushes a Window Manager to its leanest essence. It is a joy to use because it does what it needs to, and then gets out of the way. The opinions that drove the project are:

* **Complexity must justify itself**.
* Lightweight is better than heavyweight.
* Select your dependencies wisely: they are complexity, but not using them, or using the wrong ones, can lead to worse complexity.
* Powerful features are good, but simplicity and clarity are essential.
* Adding layers of simplicity, to avoid understanding something useful, only adds complexity, and is a trap for learning trivia instead of knowledge.
* Steep learning curves are dangerous, but don't just push a vertical wall deeper; learning is good, so make the incline gradual for as long as possible.
* Allow other tools to thrive - e.g: terminals don't need tabs or scrollback, that's what tmux is for.
* Fix where fixes belong - don't work around bugs in other applications, contribute to them, or make something better.
* Improvement via reduction is sometimes what a project desperately needs, because we do so tend to just add. (https://www.theregister.com/2021/04/09/people_complicate_things/)
