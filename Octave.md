# Question #

How to install Octave on Mac OS X?


# Details #

  1. Install Xcode 4.3 or above.
  1. Install Xcode command line tools via XCode -> Preferences -> Download
  1. Install MacPorts from:  http://www.macports.org/install.php
  1. To install Octave, run:
```
sudo port install octave-devel +atlas+docs
```
  1. If it failed to install the package xorg-bigreqsproto, do the following:
    * Install X11 for Mac OS X from:  http://xquartz.macosforge.org/landing/
    * Install Java JRE v7.0 Update 11
  1. For any dependent package ("FAILED\_PACKAGE" below) still failing to be installed,  run the following command to install it manually:
```
sudo port install FAILED_PACKAGE
```
> Or try:
```
sudo port clean FAILED_PACKAGE -f
sudo port install octave-devel +atlas+docs
```
