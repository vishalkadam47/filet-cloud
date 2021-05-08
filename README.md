# filet-cloud
A lean slice of Cloud Storage

This project attempts to make a sofisticated personal cloud storage solution similar to the google-drive ecosystem, using the design philosophies of the filet project series. This project will hopefully contain little code, and rather bring together existing technologies into a simple project.

It will target a single build running on a Raspberry Pi.

## Setup

* Install Raspberry Pi OS to a microSD card (https://www.raspberrypi.org/software/)
* Place in the Pi.
* Format a external USB drive (for the data) as btrfs (https://wiki.archlinux.org/title/Btrfs).
  * Create a subvolume `sudo btrfs subvolume create filetclouddata`
  * Make it open writable `sudo chmod a+w filetclouddata`
* Connect the external USB storage to the Pi.
* Power on and set up your Pi with WiFi and a better password.
* Enable ssh on your Pi (https://www.raspberrypi.org/documentation/remote-access/ssh/).

TBC

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
