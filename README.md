This is a repository that provides a script for installing PicoSAT for use with
xconfig from the Linux project.

# Installation

To install PicoSAT, run the following commands:

```sh
git clone https://github.com/ole0811sch/picosat-installer.git # clone this repository
cd picosat-installer
make libpicosat-trace.so    # compile PicoSAT
sudo make install           # install PicoSAT
```

To uninstall, run ```sudo make remove```.
