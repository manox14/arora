# Goals #

### Web Browser ###
The project's primary focus is to create an open source browser built on QtWebKit that is capable of being used as a primary day to day web browser.  Supporting all of the regular features that users expect a browser to have.

This includes
  * History
  * Bookmarks
  * Tabs
  * Extensions

### Open Source ###
Arora should remain fully open, its source, its tests, its research, development, and mailing-lists.

### Speed & Stability ###
Arora will strive to be stable, well tested, and built to recover when it does fail with minimal data loss.

### Cross Platform ###
Arora will work on Linux, OS X, Windows and Embedded Linux.

### Hackability ###
To make rapid progress possible, we try to keep the code relatively easy to understand,  straightforward algorithms and data structures are used when possible.  Consistent code styling, clear, maintainable code, and we continue to improve names and code structure to aid understanding. In addition, we make heavy use of regression tests as a safety net, to allow aggressive changes with less risk of regressions.

# Non-Goals #

The following consider out of scope for the project

### Single Desktop Browser ###

Arora will not strive to become a KDE browser or only a Windows browser.  Specifically on Linux Arora should fit just as well in Gnome as it does with KDE.  Rather then calling it a Linux browser perhaps it should be called a FreeDesktop.org Browser.  Specific features to integrate with KDE, Gnome, OS X, or Windows should be built as extensions whenever possible.

### The Kitchen Sink ###

Arora hopes to never become another Mozilla.  The Extension system should allow for many features to be implemented outside of the browser.