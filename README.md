# Keychain
* Originally authored by Daniel Robbins <drobbins@gentoo.org>
* Maintained August 2002 - April 2003 by Seth Chandler <sethbc@gentoo.org>
* Maintained and rewritten April 2004 - July 2007 by Aron Griffis <agriffis@n01se.net>
* Maintained July 2009 - September 2017 by Daniel Robbins <drobbins@funtoo.org>
* Maintained September 2017 - present by Ryan Harris <x48rph@gmail.com>
* Forked by @jordantrizz https://github.com/jordantrizz/keychain
* Forked by @necrotech https://github.com/necrotech/keychain

## Changes
All changes are documented in the [CHANGES.md](CHANGES.md) file including a TODO list.

## Goal
The goal of this fork is to make keychain better for my own use. I will be monitoring other forks for new commits, review and apply patches.

## Branches
* main - This is the default branch.
* original-recipe - This branch is based on the original recipe from funtoo/keychain and uses tag 2.8.5.
* new-recipe - This branch is based on the last commit from necrotech/keychain and uses tag 2.8.6.
* devel - This branch is used for development and will be merged into main when a new release is made.
* release - This branch is used for release and will be merged into main when a new release is made.
* feature - This branch is used for feature development and will be merged into devel when the feature is complete.

# IMPORTANT - GitHub Contributors

Please apply your patches to `keychain.sh`, *not* the generated `keychain`
script, which we are now including in the git repo to facilitate the
distribution of release archives direct from GitHub. All development work will 
be done on the 'devel' branch and will only be merged with the master branch when 
a new release is made. This should allow the generated files (keychain, man pages,
spec file)to remain in sync on the master branch but no guarantees are made except
for the tagged release. They will be regenerated for official release archives 
only (those tagged with the release version.). Anyone using or contributing to the
'devel' branch should assume the generated files are out of date and regenerate 
locally if needed.
Thanks!

# Introduction to Keychain

**Official documentation for Keychain can be found on [the official Keychain
wiki page](http://www.funtoo.org/Keychain).**

`Keychain` helps you to manage ssh and GPG keys in a convenient and secure
manner. It acts as a frontend to `ssh-agent` and `ssh-add`, but allows you
to easily have one long running `ssh-agent` process per system, rather than
the norm of one `ssh-agent` per login session. 

This dramatically reduces the number of times you need to enter your
passphrase. With `keychain`, you only need to enter a passphrase once every
time your local machine is rebooted. `Keychain` also makes it easy for remote
cron jobs to securely "hook in" to a long running `ssh-agent` process,
allowing your scripts to take advantage of key-based logins.


