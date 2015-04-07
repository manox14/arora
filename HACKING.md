If you run 'make dox' it will build a doc/ directory using Doxygen which you can use to browse and explore the code.

# /src/ #

  * BrowserApplication - Various functions and owner of main objects like the BrowserManager, has a list of BrowserMainWindow's.
  * BrowserMainWindow - The main window, owner of all of the actions, location bar, search widget, and a TabWidget.
  * TabWidget - Subclass of QTabWidget, has a bunch of QWebView's.  Decides if a middle mouse click should open a new tab or not.
  * WebView - Subclass of QWebView, has a WebPage.  Right click menu and actions are here.
  * WebPage - Subclass of QWebPage.

Various other classes such the view source classes, the drop down search widget, and the download window class, and settings dialog.

# /src/locationbar/ #

Our customized location bar, the site icon and privacy icon.  It is a subclass of LineEdit which isfound in src/utils.  The completion is done by the HistoryCompleter which is in ...

# /src/history/ #

  * HistoryManager - Owner of all of the history, stored in a very simple format (pretty much one entryper line in a text file)
  * HistoryCompleter - sits on top of HistoryManager and populates the completer in the location bar.
  * HistoryDialog (and friends) - Used to show the History Dialog and History Menu

# /src/bookmarks/ #

We use the open standard xBel for bookmarks, classes to read/write are found in the xbel/ folder.  I
mporting html to xbel is found in the tools/html2bel tool.

  * BookmarksManager - Ownser of all bookmarks, loads and saves.
  * BookmarksToolbar - class that sits in the main window
  * BookmarksMenu, BookmarksDialog, AddBookmarkDialog - User interfaces to our bookmarks

# /src/opensearch/ #

All of the code that handles the search widget in the top right of the toolbar is found in here.

  * OpenSearchManager - owns a bunch of OpenSearchEngines which are read and written via  OpenSearchReader and OpenSearchWriter
  * OpenSearchDialog - the configuration dialog

# /src/network/ #

The NetworkAccessManager which routes all network connections is here.  Disk cache, proxy, custom sc
heme's and a complete replacement CookieJar is found here.

# /src/qwebplugins/ #

QtWebKit's "plugin" system (like netscape plugins, but for Qt), currently only clicktoflash is here.

# /src/utils/ #

This is a collection of very useful classes (i.e. stuff that could/should be in Qt) that are not specific to Arora and other applications can/do copy the code.  See the README file for details.

# /autotests/ #

Many of the classes in Arora have matching autotests that can be found here.  They use the Qt test system.

# /manualtests/ #

Many of the classes in Arora have little manual test application that can be found here.

# /git\_hooks/ #

If you sym-link this directory to your .git/hooks these scripts will run on commit.  They do several things including:
  * Spell check your commit message
  * Run the autotest that goes to the file you are changing to confirm that you didn't break anything. (and only that autotest, not all of them)
  * Makes sure arora builds (this should be a noop because you built before committing, right...?)
  * Runs a simple shell script that does some code style checking.