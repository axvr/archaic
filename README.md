# ALIS - Arch Linux Installation Script


**NOTE: ALIS (what was going to become Archaic) has been depreciated, this is
due to several factors which I explain below.**

* ALIS was in dire need of yet a second rewrite/full refactor. I wrote ALIS when
  I was learning Perl (and programming in general), and didn't know enough about
  it (e.g. Moose and OOP, Perl CPAN, the list goes on).
* It was started as a learning project. I was using and learning about Arch
  Linux at the time, and thought it would be a great way to learn more about the
  Linux world, and it has helped me a great deal.
* During the process of building ALIS, I learnt how to manually install Arch
  (the "normal" way), so I no longer required an installer (this had been the
  plan all along).
* I no longer use Arch Linux. At the time of writing this, I have moved to
  Fedora, There are several reasons for this but the main one was that I wanted
  to actually get stuff done rather than having to fix OS issues all of the time
  (especially WiFi drivers). Arch is still one of my favourite Linux distros.
* Feature creep had become a huge problem in ALIS. ALIS was beginning to evolve
  into a full on desktop configuration tool (even before the installer had been
  completed). I now try to follow the [Unix
  philosophy](http://www.catb.org/~esr/writings/taoup/html/ch01s06.html) in my
  programs, and focus on code
  [simplicity](https://www.youtube.com/watch?v=rI8tNMsozo0) and
  [minimalism](http://minifesto.org/) in an effort to minimise complexity. ALIS
  had become a complexity nightmare, and an example of what not to do (it even
  had colour theme support!  Seriously, who needs that?). 

Things that were going to be implemented next:

* Split the Libraries away from the ALIS core.
* Rewrite the Whiptail module to be a wrapper over the Newt Perl CPAN module, in
  an OOP style.
* Simplify the code, especially `src/main.pl`.
* Integrate network checking into the `network.pm` Perl module.
* Improve multi-language support.

---

<!-- Badges made using https://shields.io/ -->
[![Version Badge](https://img.shields.io/badge/Version-v0.3.0-brightgreen.svg)](https://github.com/axvr/alis/releases)
[![Licence Badge](https://img.shields.io/badge/Licence-MIT-blue.svg)](https://github.com/axvr/alis/blob/master/LICENCE)

The successor of Architect Linux (currently still in development)

This is ALIS - Arch Linux Installation Script. ALIS has been built from the ground up, using the Perl scripting language and Bash. The aim of ALIS is to help guide beginner Arch Linux users through the Arch installation process. ALIS has many advanced configuration options, these make ALIS well suited for use by both advanced users and beginners. ALIS will create a base plain and simple Arch system, with zero bloat.

The inspiration for this project was Architect Linux, which sadly ceased development on 2016-04-05. ALIS is it's (hopefully successful) successor.

This is the ```README.md``` file for [ALIS](https://github.com/axvr/alis). Created by [Alex Vear - axvr](https://github.com/axvr).

This project is licenced under the [MIT Licence](https://github.com/axvr/alis/blob/master/LICENCE).

If you find any bugs or errors, please feel free to submit an issue as i cannot test ALIS on every possible system for problems. I would in the future like to add multi-language support to ALIS, help would be greatly appreciated, especially since Google Translate is not entirely accurate a lot of the time. For more information on contributing to ALIS see the [contributing document](https://github.com/axvr/alis/blob/master/CONTRIBUTING.md) and ensure that you read and agree to the [Code of Conduct](https://github.com/axvr/alis/blob/master/CODE_OF_CONDUCT.md).

---

## Screenshots

![Welcome Screen](docs/screenshots/001-alis-welcome-screen.png)

![Network Check](docs/screenshots/003-alis-network-check.png)


---

## How to use ALIS

In order to use ALIS, you will need an Arch Linux live CD, and the machine you wish to install Arch onto.

### Compatible System Architecture and Boot Modes

Please ensure that your system meets these system types:

#### Architecture

* x86_64

#### Boot Mode

* BIOS
* UEFI

#### Still to be Supported

* PowerPC


### Make an Arch Linux live Disk/CD

Follow the instructions from the Arch Wiki on how to [make and verify your own Arch live disk](https://wiki.archlinux.org/index.php/Category:Getting_and_installing_Arch). This will be reqired for ALIS to work correctly. Once this has been done then insert the medium into the machine you wish to install Arch Linux to, then boot up the system, to that disk.

Alternatively, if you are looking to test out Arch or just to experiment with it, there is also the option of using a Virtual Machine (A computer running on a computer). To do this follow these instructions and download the Arch ISO from [here](https://wiki.archlinux.org/index.php/Category:Getting_and_installing_Arch), and optionally (recommended) verify your download. Follow these [instructions](https://www.virtualbox.org/manual/ch01.html) to setup a virtual machine in your current OS using Oracle's VirtualBox.

### Setup and Start ALIS

**NOTE: ALIS and Arch Linux both require a stable internet connection, this is best done using an ethernet connection directly into the machine (virtual machines have internet by default if the host machine has an internet connection).**

First ALIS will need to be downloaded to the live Arch distro. The ALIS download contains all of the files needed for ALIS to run without any problems. This can be done by typing **exactly** this command (replace the ```<version>``` with the [latest version number](https://github.com/axvr/alis/releases)).

```wget https://github.com/axvr/alis/archive/v<version>.tar.gz```

Extract the downloaded gzip (tar.gz) file (the ```<version>``` will be version number from before).

```tar -zxvf v<version>.tar.gz```

You will then need to Move into the new ALIS directory (the ```<version>``` will be version number from before).

```cd alis-v<version>/```

Start ALIS using

```./alis```

Follow the on screen instructions to install Arch Linux.


### All ALIS Options

* Set language for ALIS to use: ```--language``` or ```-l``` followed by language code (see below for codes).
* Display help message: ```--help``` or ```-h```.
* Display usage information: ```--usage``` or ```-u```.
* Display ALIS version information: ```--version``` or ```-v```.
* Select a theme for ALIS: ```--theme``` or ```-t``` followed by a theme name (see below).


### ALIS Language Options (language codes)

* ```en``` => English
* ```fr``` => French
* ```es``` => Spanish


### ALIS Theme Options (theme names)

* ```default```   => Default theme
* ```cyberpunk``` => Cyberpunk style theme


---


## To do

### Core components

* [x] Multi-language support
* [x] Language selection and changing
* [x] Log file functioning (and reduce chance of data corruption)
* [x] Create a new help menu
* [x] Create a usage menu
* [x] Split sections into individual modules
* [x] Create Whiptail module
* [x] Extend Whiptail module to use smart parameters
* [x] Complete a basic version of the Whiptail module
* [x] Design and create a new menu page using the new modules

### Documentation

* [x] Include all current commands in the README.md file
* [x] Comment code and increase readability
* [x] Expand Documentation to include contribution page
* [x] Change project Licence to the MIT Licence from the GPL v3
* [ ] Create a "Hacking ALIS" document
* [ ] Update contribution document
* [ ] Update code of conduct

### Start up

* [x] Check hardware configuration of device
* [x] Create base version of the program
* [x] Check the network connection
* [x] Sync the time with NTP servers
* [ ] Replace old keyboard layout selector (maybe move sections)

### Pre Install Section

* [x] Display partition map
* [x] Allow device/partition wiping securely
* [x] Allow manual partitioning
* [ ] Create auto partition script
* [ ] Format disks

### Installation Section

* [ ] (PENDING)

### System Configuration Section

* [ ] (PENDING)

### Post Installation Section

* [ ] (PENDING)

