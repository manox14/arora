Making Arora fit better in KDE4

# Introduction #

As it is today Arora doesn't fit as well as it could into KDE4.  Below is a list of ideas on ways to improve that.

Feel free to add items not listed here as a comment.

## Done ##

The following should already happen
  * Use the default KDE style (Oxygen)
  * Use KDE shortcuts
  * Use KDE icons back/forward/stop/reload (given by the style)
  * Use KDE icons in the menu's (given by the style)
  * Desktop file should appear in the KDE menu
  * Import Konq's bookmarks (Both applications use XBel format, this could even be a shared file via a sym links)
  * Use XDG for opening files/folders
  * Use XDG for getting the location for the data, cache, and settings folder.
  * Use QButtonBox so button order in dialogs will be correct in KDE
  * Meta keys
  * QDir::tempDir();
  * QSettings
  * honor the QLineEdit background contents rect so in LocationBar::paintEvent where we paint the background yellow for https sites we're are not painting a larger area than oxygen does
  * KDE icons in menus

In KDE; fixed for KDE 4.3
  * KStyle needs to add support several new QTabBar style hints that  were added in 4.5 http://labs.trolltech.com/blogs/2008/07/02/some-qtabbar-qtabwidget-love/ http://bugs.kde.org/show_bug.cgi?id=184782
  * KStyle needs to overload standardIconImplementation and return the  KDE icons for the back/forward/stop/reload and other icons so Arora will get them rather then the standard ones oxygen is giving today.

In Oxygen; fixed for KDE 4.3
  * Oxygen does not cause the KDE file dialog because it does not link to kio

## TODO ##

From the Kubuntu guys: https://wiki.kubuntu.org/KubuntuKarmicWebbrowser

In Oxygen
  * Oxygen has rendering issues in qtwebkit with buttons.

In Arora
  * Use the new proxy stuff in 4.5 which in theory will pickup KDE's proxy setting in the future.
  * Don't use activate in the bookmark manager/cookie manager (Need to  test in kde)

Other
  * KRunner integration. Konqueror's history and bookmarks are supported in a search-and-open functionality, but the importance of this feature is debatable, as KRunner is not well-known.

Q -> K (We would get)
  * Toolbar dots/handles, KDE apps have "Lock/Unlock Toolbars" option in context menu (to hide/show them), along with stuff like text position, orientation and icon size.
  * Some more discussion on Q -> K http://groups.google.com/group/arora-dev/browse_thread/thread/fdb8427d72a8739

Screenshots
  * http://imagebin.ca/view/4Z7EiR.html