# Welcome to the SlackOnly software repository!

(This is the $ARCH Slackware $RELEASE directory)

## Introduction

SlackOnly is a third party software repository for Slackware Linux that
provides binary packages built from SlackBuilds.org (SBo) build scripts.
The goal is to enable users to install any package from SBo and to do so
with just a quick download.  SlackOnly also provides meta data that
supports automatic dependency resolution with certain package managers.
SlackOnly assumes that users have installed a full installation of
Slackware Linux prior to use.

SlackOnly supports the following Slackware releases and architectures:

 * Slackware 14.1 32 bit [14.1-x86][1]
 * Slackware 14.1 64 bit [14.1-x86_64][2]
 * Slackware-current 32 bit [current-x86][3]
 * Slackware-current 64 bit [current-x86_64][4]
 * Custom Packages 64 bit [custom-x86_64][5]

 [1]: http://packages.slackonly.com/pub/packages/14.1-x86/
 [2]: http://packages.slackonly.com/pub/packages/14.1-x86_64/
 [3]: http://panos.slackonly.com/pub/packages/current-x86/
 [4]: http://packages.slackonly.com/pub/packages/current-x86_64/
 [5]: http://packages.slackonly.com/pub/packages/custom-x86_64/


## Why should you use SlackOnly?

 * To quickly test a program before building it from source
 * Your computer is too slow or old to build a piece of software from
   source in a timely fashion
 * You are not worried about customizing every package and default
   package configurations are adequte
 * Some packages have a massive dependency chain and building it can be
   very complicated and time consuming


## How to use SlackOnly

There are a variety of ways to enable and use SlackOnly on your
Slackware installation.

 * Install slackpkg+
 * Install slpkg
 * Install slapt-get
 * Install gslapt and use it with slapt-get

#### Slackpkg+ Usage

__Important:  slackpkg+ does not provide automatic dependency
resolution. Skip down to one of the other package managers for this
feature__

1.  Install slackpkg+, which is an extension to slackpkg.

    * [Download slackpkg+ Here](http://www.slakfinder.org/slackpkg+.html)
    * Then in the directory containing slackpkg+, as the root user run
      the following command to install slackpkg+:

    > root@localhost~# installpkg slackpkg+*.t?z

2.  Add to and edit the appropriate sections of slackpkgplus.conf. This
    file is located in /etc/slackpkg/ and requires root permissions to
    edit it.

    * Change this line:

    > REPOPLUS=( slackpkgplus restricted alienbob slacky )

    * To read like this line:

    > REPOPLUS=( slackpkgplus restricted alienbob slacky slackonly )

    * Add SlackOnly to the list of mirrors.
    * Where RELEASE is either "14.1 or "-current"
    * Where ARCH is either "x86" or "x86_64" architecture

    > MIRRORPLUS['slackonly']=http://slackonly.com/pub/packages/RELEASE-ARCH/

    * Save your changes to /etc/slackpkg/slackpkgplus.conf

3.  Next run the following commands as root to import the SlackOnly GPG
    key and to update the slackpkg cache with the SlackOnly package
    list.

    > root@localhost~# slackpkg update gpg

    > root@localhost~# slackpkg update

4.  You are now ready to use slackpkg with the slackpkg+ extension to
    access the SlackOnly repository of your choice.

    * Notes:  Be sure to add the same repository and architecture as
      your Slackware installation.  You may run into problems if you add
      the wrong repository.
    * Further directions can be found in the man page or viewed online
      in the [slackpkg+ README][6].

[6]: http://slakfinder.org/slackpkg+/src/README

#### Slpkg Usage

 (EDIT: Add directions)

#### Slapt-get and Gslapt Usage

 (EDIT: Add directions for stand alone slapt-get)
 (EDIT: Add optional direction to include gslapt)


## For Developers and Packagers

 (EDIT: Add information for package maintainers)
 (EDIT: Add information discussing depenendcy resolution)

## SlackOnly Contact and Contributors

* Web Site: [www.slackonly.com](http://slackonly.com)
* Project Lead:  Panagiotis Nikolaou <hostmaster -at- slackonly [dot] com>
* Contributor:  Brenton Earl [www.exitstatusone.com](http://exitstatusone.com)

## Credits and Thanks

* Patrick Volkerding for [Slackware Linux][20]
* David Spencer for [slackrepo][21]
* zerouno for the slackpkg extension, [slackpkg+][22]
* Eric Hameleers for the [slackpkg+ directions][23]
* Dimitris Zlatanidis for the [slpkg package manager][24]
* Jason Woodward and Contributors for [slapt-get and gslapt][25]

[20]: http://www.slackware.com/
[21]: https://idlemoor.github.io/slackrepo/index.html
[22]: http://www.slakfinder.org/slackpkg+.html
[23]: http://alien.slackbook.org/blog/introducing-slackpkg-an-extension-to-slackpkg-for-3rd-party-repositories/
[24]: https://github.com/dslackw/slpkg
[25]: http://software.jaos.org/

## Copyright

* Slackware� is a Registered Trademark of Patrick Volkerding.
* Linux is a Registered Trademark of Linus Torvalds.