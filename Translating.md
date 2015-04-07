This page contains instructions that you could use to contribute to Arora by translating its interface into another language.

# Instructions #

  * Download the latest source code from git. See [source](source.md) for instructions on how to do that and set up a Qt development environment.
  * Open the file src/locale/locale.pri. If your ISO language code (lang\_COUNTRY) is not in the TRANSLATIONS section, add it to the list:

```
TRANSLATIONS += \
  xx_XX.ts \     # line to add, replace xx with your language code
  ru_RU.ts \
  en.ts \
...
```

> Do not bother to actually create the file, lupdate will do this for you.
  * Run this command:

```
lupdate ../src/src.pro
```

> or under Windows:

```
(path to Qt bin directory)\lupdate.exe ..\src\src.pro
```

  * Open the src/locale directory inside the source. It should now contain the .ts file for your language.
  * Open the file in Qt Linguist. If you need help using that program, see [the official Qt Linguist documentation](http://doc.trolltech.com/4.4/linguist-manual.html).
  * Save the file when you're finished translating.

The new translation will now be integrated into both Unix installations (`make install`) and the Windows installer created by the `windowsinstaller.nsi` script.

To test the language under Linux you can set the LANG environment variable.  You can run 'LANG=foo ./arora' where foo is the translation you are working on.

To ask the developers to add the translation to the main source tree, you can:
  * If you modified an existing file check the locale/maintainers file to see if you should email the change to the maintainer of that locale.
  * Create a github.com branch with your translation, as outlined in [contributing](contributing.md).
  * Alternatively, create an issue in the Google Code issue tracker, with a summary like "Add translation into the X language" (or "Update X translation" if one already exists), and attach the .ts file.

# Maintaining translations #

If you feel like your contribution isn't the last and the only one and you would like to continue updating your favourite language pack, you can become a maintainer. A maintainer takes care of the translation and is the one to review the patches sent by others. This system makes it possible to keep translations consistent. Also, as the developers find it hard to review translation patches as they don't know the languages being updated, it is the maintainers that can make sure that the patches are correct and fit into general style of particular translations.

If there is already a maintainer assigned to the language you would like to contribute to, you should first contact him and propose collaboration. If the maintainer has been inactive for a while, you can stand in for him.
If you have translated Arora to a new language and would like to become a maintainer of that translation, you become at once.
If you've been contributing to a language that had been already present in the tree, you can become a maintainer having provided the first patch.

Three ways to become a maintainer:
  * Send an e-mail to arora-translation mailinglist http://groups.google.com/group/arora-translation.
  * Pop in the irc channel and ask.
  * Ask when requesting pulling your first translation patch.

The maintainers are listed in the src/locale/maintainers file so that other contributors can pass the patches directly to the maintainers.

Lastly join the arora-translation mailinglist.  http://groups.google.com/group/arora-translation  This list will be limited to discussions about the translations and calls for translations for the next release.

Thank you for helping out!