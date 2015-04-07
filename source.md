The Arora source code is in a git repository and the main repository is currently hosted on github.com

## Checkout ##

To checkout a copy of the source execute the following command

> ` git clone git://github.com/Arora/arora.git `

## Browse ##

To browse the source code go to: http://github.com/Arora/arora

## Information about Git ##
More information about git include tutorials and GUI tools can be found at http://git.or.cz/

## Building ##

For beginner instructions, read [BeginnerStepByStepInstructions](BeginnerStepByStepInstructions.md).

Arora requires Qt version 4.4 or newer. Get Qt from http://www.trolltech.com/ : [Official Install Instructions](http://doc.trolltech.com/installation.html) and [Download Page](http://trolltech.com/downloads/opensource). On Linux check with your distribution for packages.

Simple steps to build Arora:
```
git clone git://github.com/Arora/arora.git
cd arora
qmake "CONFIG-=debug" -r
make
```
Type `nmake` instead of `make` if using Visual C++ to compile.

To compile in debug simply remove the "CONFIG-=debug" from the qmake line.

On OS X when using the binary Qt package use 'qmake -spec macx-g++' to generate the Makefile rather then the XCode project.

If you get a compile error that goes something like:
```
webview.cpp:(.text+0x300c): undefined reference to `QWebPage::createStandardContextMenu()'
```

Try cleaning up the old object files with the following command
```
make clean;qmake;
```

### Getting Flash ###

To have flash in Arora you need to use a newer version of webkit then the one that comes with Qt 4.4.  You can either use qt-snapshot or you can use any version of Qt and QtWebKit Trunk.

### Building with QtWebKit Trunk ###
If you want to use Arora with QtWebKit trunk you need to get a copy WebKit trunk as well at Qt 4.4.  Setting the environment variables QT\_WEBKIT and WEBKITDIR and rebuilding Arora will cause it to use QtWebKit trunk.  See the file 'webkittrunk.pri' in Arora's source for more details and customizations you might need to do to point it to the location of your QtWebKit checkout.

Simple steps to build QtWebKit trunk:

```
$ svn checkout http://svn.webkit.org/repository/webkit/trunk WebKit
$ cd WebKit
$ ./WebKitTools/Scripts/build-webkit --qt --release
```

If qmake is not the qt4 binary (such as on debian where qmake points to the Qt3's qmake and qmake-qt4 points to the Qt4's qmake).  To specify the version of qmake to use (such as on Debian) append the following to the build-webkit script
```
--qmake=qmake-qt4
```

To compile in debug use
```
--debug
```
rather then --release

WebKit will be built in the subdirectory **WebKitBuild/Release/**

And the build Arora with it:

```
$ cd /path/to/arora/source
$ export QT_WEBKIT=webkit_trunk
# WEBKITDIR should be set to the parent directory of WebKitBuild
$ export WEBKITDIR=$HOME/dev/webkit
$ qmake  "CONFIG-=debug" -r
$ make clean
$ make
```

QtWebKit should pick up the plugins that are installed in your system.  It will look in the normal locations and if it works in firefox it should also work in arora.  If plugins don't work you can double check that arora is using webkit trunk run running ldd on arora to make sure it is using the correct webkit library.   More details about the exact directories can be found in WebCore/plugins/PluginDatabase.cpp or for a quick cheatsheet: http://pastebin.com/f47afa819