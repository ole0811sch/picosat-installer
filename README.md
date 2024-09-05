This is a repository that provides a script for installing PicoSAT as a library for use with xconfig from the Linux project.

# Installation

## Debian-based Distros

With apt, you can install PicoSAT as the following package:

```sh
sudo apt install picosat
```

## Fedora

With dnf, you can install PicoSAT as the following package:

```sh
sudo dnf install picosat
```

## Other

Otherwise, you can install PicoSAT from this repository by running the following commands:

```sh
git clone https://github.com/ole0811sch/picosat-installer.git # clone this repository
cd picosat-installer
make libpicosat-trace.so    # compile PicoSAT
sudo make install           # install PicoSAT
```

To uninstall, run ```sudo make remove```.
