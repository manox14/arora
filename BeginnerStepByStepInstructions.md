# Step-by-Step Instructions to Run The Latest Arora #

## Introduction ##

Arora is still in early development, which means that there are no compiled installable packages yet. To try the latest code, follow this guide.


## Step 1: Make sure git is installed. ##
To see if git is installed, open up a terminal window and type `git`. If it is not installed, the terminal will report back command not found. If it is installed, you'll receive the git help text. To install git: [Windows](http://code.google.com/p/msysgit/downloads/list), [Mac](http://code.google.com/p/git-osx-installer/downloads/list?can=3), and for Linux, use your distro's package manager.

## Step 2: Download and install Qt 4.4 or greater. ##
If you already have **Qt 4.4** or greater installed, you can skip this step. To install qt 4.4, visit the [Official Install Instructions](http://doc.trolltech.com/installation.html) and the [Download Page](http://trolltech.com/downloads/opensource). Be sure to add the correct PATH variable if required in the official install instructions. When you're done, skip the alternative method section, and move onto Step 3.

### _Alternative Method_: Download and install qt-snapshot. ###
Qt snapshot is the latest trolltech snapshot of the upcoming qt version. Choose this alternative method only if you are especially curious. Otherwise, follow the directions in the section above to get the release version. Issue these commands to get the latest qt snapshot:
```
$ git clone --depth 1 git://labs.trolltech.com/qt-snapshot
$ cd qt-snapshot
$ ./configure -no-accessibility -no-exceptions -no-qt3support
```

Accept the licence. At the end of this, jot down the directory that qt will be installed into. On my computer it is `/usr/local/Trolltech/Qt-4.5.0-snapshot-20080518`. Now we are ready to compile and install qt. This will take a while. Type: `make && sudo make install` and press enter. Be sure to add the bin directory inside of installation directory to your PATH: `export PATH="/usr/local/Trolltech/Qt-4.5.0-snapshot-20080518/bin:$PATH"`. Be sure to use the directory given by the configure script, and not the one used here as an example.

_**Optional**_: To update the qt snapshot in the future, you can issue these commands:
```
$ cd qt-snapshot
$ git pull
$ make && sudo make install
```

## Step 3: Download and compile the latest Arora. ##
Now we will download the latest tree of Arora. Issue these commands:
```
$ git clone git://github.com/Arora/arora.git
$ cd arora
$ qmake
$ make
```
Arora is now compiled. To run arora, simply run `./arora` from the current directory.

_**Optional**_: To update to the latest Arora in the future, you can issue these commands:
```
$ cd arora
$ git pull
$ make distclean
$ qmake
$ make
```

Under Debian-based systems, including Debian and Ubuntu, use `qmake-qt4` instead of `qmake`. You will need to install the `libqt4-dev` package version 4.4, which is available in Debian testing, as well as Ubuntu 8.04 in the `hardy-backports` repository.

If you are looking for an IDE to develop Arora in you can checkout the free IDE <a href='http://www.qtsoftware.com/downloads'>Qt Creator</a> that is available with Qt 4.5.