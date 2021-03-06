Sget
====

| **Linux + Mac** |
|-----------------|
| [![Build status](https://travis-ci.org/d99kris/sget.svg?branch=master)](https://travis-ci.org/d99kris/sget) |

Sget (source get) - is a small utility facilitating installation of software from source
packages, by automating the process of downloading the source and doing configure, make,
sudo make install.

Example Usage
=============

    $ sudo sget install https://github.com/d99kris/heapusage

Why
===
Standard package managers (apt, brew, yum, etc) handling dependency resolution,
updates, etc is generally the preferred way to install software. The sget
utility mainly caters for installation of softwares not (yet) available through
package managers. 

Supported Platforms
===================
Sget should work on most Linux and macOS systems.

Installation
============

Using sget
----------

    wget -qO - https://raw.githubusercontent.com/d99kris/sget/master/sget | sudo bash -s -- install https://github.com/d99kris/sget

From source
-----------
Download source:

    git clone https://github.com/d99kris/sget

Build:

    cd sget && mkdir -p build && cd build && cmake .. && make -s

Install:

    sudo make install

Usage
=====

General usage syntax:

    [sudo] sget [--prefix PREFIX] install PKG [PKG ...]
    [sudo] sget [--prefix PREFIX] remove PKG [PKG ...]
    sget --help
    sget --version

Options:

    PKG          web link to a version controlled (Subversion or Git) 
                 repository or web link to a source code package, or path 
                 to a locally stored source code package
    install      builds and installs specified package
    remove       uninstalls specified package
    PREFIX       specifies an alternative installation prefix path
    --help       display this help and exit
    --version    output version information and exit

Examples:

    sget install https://github.com/d99kris/heapusage   # install from repository

    sget install ~/Downloads/heapusage-master.zip       # install local package

    sget remove https://github.com/d99kris/heapusage    # uninstall

Technical Details
=================
The test suite can be run using these commands:

    mkdir -p build && cd build && cmake .. && make -s && ctest --output-on-failure

License
=======
Sget is distributed under the MIT license. See LICENSE file.

Keywords
========
install from source,linux,macos

