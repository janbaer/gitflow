# Overview

This document describes the installation and usage of gitflow at **CHECK24**

- Version: 2

## External links
* [GitFlow on Github](https://github.com/nvie/gitflow)
* [GitFlow on Github (Forked janbaer)](https://github.com/janbaer/gitflow)
* [Git-Flow-Cheatsheet](http://danielkummer.github.com/git-flow-cheatsheet/)
* [Why aren't you using git-flow](http://jeffkreeftmeijer.com/2010/why-arent-you-using-git-flow/)
* [Git Flow – einfaches Arbeiten mit dem perfekten Git Workflow](http://splitshade.wordpress.com/2012/04/22/git-flow-einfaches-arbeiten-mit-dem-perfekten-git-workflow/)
* [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/)
* [Video on Vimeo](http://vimeo.com/16018419)
* [Video Using Git-Flow to Relieve Your Headaches](http://www.youtube.com/watch?v=NdXhz4rt_sQ)
* [Poshgit with GitFlow integration](https://github.com/janbaer/posh-git)

## Installation

* Copy the files *optgen.exe* and *libint3.dll* from the *optgen* subdirectory to the bin folder of your git installation path
* Your Git-Bin directory should be in the *PATH* evironment variable
* cd gitflow
* *contrib\msysgit-install.cmd "{Path to your git-installation-folder}"*

## Initialization (Empty repository)

* *git init*
* *git flow init*
	* Production releases: *release*
	* Next release *main*
	* Feature branches: *feature/*
	* Release branches: *qa*
	* Support branches: *support*/
	* Hotfix branches: *hotfix/*
* *git push origin --all*

## Initialization (With clone from server)
* *git clone http://jan.baer@localhost:8080/scm/git/gitflowtest/ -b main -o origin* (Die Angabe von origin ist optional)
* Wenn release lokal benötigt wird: *git remote set-branches origin release release --add*
* *git flow init*
	* Production releases: *release*
	* Next release *main*
	* Feature branches: *feature/*
	* Release branches: *qa*
	* Support branches: *support*/
	* Hotfix branches: *hotfix/*

## Add aliases for the most used commands
* *git config –-global --add alias.pom "push origin master"*
* *git config –-global --add alias.ffs "flow feature start"*
* *git config –-global --add alias.ffr "flow feature rebase"*
* *git config –-global --add alias.fff "flow feature finish"*

## Workflow - NewFeature

1. Start feature with: *git flow feature start **MYFEATURE***
2. Add changes to Index: *git add .*
3. Commit the changes to current: *git commit -m "My changes for the new feature*
4. Finish feature with: *git flow feature finish*

## Workflow - NewFeature with Rebase
1. Start feature with: *git flow feature start **MYFEATURE***
2. Add changes to Index: *git add .*
3. Commit the changes to current: *git commit -m "My changes for the new feature"*
4. Try to rebase with *Main*: *git flow feature rebase*
4. Finish feature with: *git flow feature finish*

## Share a Feature with other users
1. Publish the feature: *git flow feature publish **MYFEATURE***
2. Getting a published feature: *git flow feature pull **MYFEATURE***

## Workflow - New Release

1. Start with new release: *git flow release start **RELEASE** [BASE]*
2. Publish this release: *git flow release publish **RELEASE***
3. Finishing the release: *git flow release finish **RELEASE***





