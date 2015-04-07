# Introduction #

First off, thanks for helping out.

After you get push access to the Arora repository when you go to http://github.com/Arora/arora/tree/master
you will now see a clone url for you to use (not the public read only one).

This url needs to be added as a remote.  "git remote add -f upstream url"  You will now have an upstream branches and tags such as upstream/master.

Everyone forks off upstream so they get every branch/tag that exists in the main repo.  Don't push up experimental branches or tags, keep your own work and branches in your own repository until it is ready to go into the main branch after it is reviewed. For example all of Ben's experimental branches can be found in his icefox account on github.

# Typical workflow #

The master branch on my local machine is a copy of upstream/master.  When I get a patch to review I usually checkout their branch, try it out and if everything is ok then I switch to master, rebase against upstream/master, and then cherry-pick or merge the branch.  After that I 'git push upstream master'

**Never do a force push to upstream/master as that will screw things up for other people.**

# Hooks #

When developing with Arora you should use the git hooks that are included with Arora.  Just symlink them into your .git directory

```
cd .git
mv hooks hooks_default
ln -s ../git_hooks hooks
```

These will help to make your commits cleaner and better.  They are only guidelines and can always be overridden with --no-verify.  If they have a bug or missing feature please let Ben know or take a stab at improving them yourself.