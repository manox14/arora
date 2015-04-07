Feature requests should be filed in issues, not in comments

# Introduction #

This is a list of major projects that need to be done for Arora.  Rather then being a simple patch or two each of these are larger project that need to be developed in a branch with possible patches going into other projects such as Qt, QtWebKit, KDE, or Kubuntu.  New UI elements should have Autotests and Manualtests.  All of these projects will require an amount of research to determine what features are needed and will often contain many sub tasks.

# Details #

Kubuntu Karmic 9.10 Inclusion
  * http://wiki.kubuntu.org/KubuntuKarmicWebbrowser
  * http://wiki.kubuntu.org/seele/KarmicTODO/Arora

KDE Integration
  * Make sure KDE users are happy with Arora, they are most likely initial set of users.
  * Pretty much complete http://code.google.com/p/arora/wiki/KDE4Integration patching KDE style if need be.
  * Owner: ?

Extensions
  * Support extensions with QScript
  * P1 Arora needs an action manager.
  * P2 QScript plugin infrastructure.

Top Sites start page
  * A rich widget that show images of the top sites.  Safari4 really nails this feature.  Maybe make something in html, graphicsview or the new qt-kinetics?  This will become the face of Arora.

Url Icons
  * Currently url icons with QtWebKit are broke,
  * P1 QtWebKit must be fixed/enhanced and then we can get icons or get a signal when they are loaded
  * P2 Patch the toolbar, menu, and dialogs to load the icon
  * manyoso has started patches for qtwebkit and arora

RSS
> Owner: Benjamin Meyer
  * P1 Library: download / parse/ fetch  rss/atom with autotests (copy tests from other rss libraries)
  * P2 UI: location bar widget, webpage, settings
> http://sites.google.com/a/chromium.org/dev/user-experience/feed-subscriptions
> http://www.rss4lib.com/2008/06/google_has_an_rss_embedding_to.html

Spellcheck
  * Add hunspell support to QtWebKit