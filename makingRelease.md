# tag #

  * Check for any patches on github and the mailinglist
  * Regenerate AUTHORS, check for duplicates
  * Run findstyleerrors.sh
  * Update changelog
  * bump version in
    * debian-upstream/changelog.in
    * src/browserapplication.cpp
    * buildosx.sh
    * generateReleaseContributors
    * windowsinstaller.nsi

  * Make a git tag
```
 git tag -a 0.12.0 -m "Version 0.12.0"
```

# tarball #

  * Make a tarball
  * git archive --format=tar --prefix=arora-0.12.0/ 0.11.0 | gzip > arora-0.12.0.tar.gz
  * upload to arora-browser.org

# binary packages #
  * Build a windows package and upload, see [BuildingOnWindows](BuildingOnWindows.md)
  * Build a OS X package and upload, see [BuildingOnMacOS](BuildingOnMacOS.md)

# Other #
  * update this wiki to use the next version :)

# Blog #

  * Changelog, screenshots, Authors