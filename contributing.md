# Introduction #

Quick tutorial on how to contribute to Arora.  Because we use git there are many different ways you can contribute, and here is just one way.

# Details #

On your local machine (if you haven't already) set your git user name and e-mail address
  * git config --global user.name "Foo Bar"
  * git config --global user.email "foo@example.com"

## For just one or two patches ##

  * Checkout the git repository
  * Make a change and commit it
  * Use git format-patch to make a patch with and make an issue with the patch attached.  When the patch is applied it goes into git just like any other commit and you get full credit.

## For multiple patches ##

  * Make an account on https://github.com/
  * Goto http://github.com/arora/Arora/tree/master and click on the fork button
  * Clone your forked repository onto your local machine
  * It is often convenient to make a branch for individual features or fixes 'git checkout -b branchname master'
  * Make any changes and then do a 'git push origin' to have it uploaded to github
  * It is encouraged to make autotests when possible.
  * Make a pull request http://github.com/guides/pull-requests to icefox or faw

  * It is good to symlink the project git hooks:
```
cd .git
rm -rf hooks
ln -s ../git_hooks hooks
```

  * If you want an image to show up next to your commits on github you have to make an account on http://gravatar.com/

After it is merged or to update to the latest arora
  * git pull --rebase git://github.com/Arora/arora.git master

Some more info on git
  * http://trac.webkit.org/wiki/QtWebKitGitInstructions
  * http://trac.webkit.org/wiki/UsingGitWithWebKit
  * http://excess.org/article/2008/07/ogre-git-tutorial/
  * http://www.gitcasts.com/
  * ![http://ktown.kde.org/~zrusin/git/git-cheat-sheet-medium.png](http://ktown.kde.org/~zrusin/git/git-cheat-sheet-medium.png)