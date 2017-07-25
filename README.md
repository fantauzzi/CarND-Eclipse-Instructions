# Instructions for the adoption of Eclipse CDT for  Udacity's Self-Driving Car Nanodegree Program

I am providing guidance to use Eclipse CDT (C++) under Ubuntu to develop projects for Udacity's Self-Driving Car Nanodegree.  

Eclipse is a feature-rich IDE that includes integration with GNU GCC, the GDB debugger and GIT versioning system. If one is new to it, it may have a bit of a learning curve. Its configuration needs to be tweaked to develop efficiently the C++ projects for the Nanodegree program. This guide tries to give a quick start to those new to Eclipse, or familiar with its Java support.

## Applicability
 
If one develops his/her C++ projects on a PC, I strongly recommend to adopt a "proper" installation of Ubuntu 16.04, in dual-boot with Windows if desired. It will provide the best compatibility with the needed libraries and simulators, and fewer configuration troubles. In case of issues, an on-line search will almost invariably reveal possible solutions (usually from Stackoverflow or Askubuntu).
  
I have tested these instructions under Ubuntu 16.04 64-bit. They do not apply to the Ubuntu shell for Windows.


### First installation


Download and run the [Eclipse Installer](http://www.eclipse.org/downloads/eclipse-packages/), and direct it to install Eclipse CDT.

Eclipse does not need superuser privileges for installation or to be run. I like to install it under `~/.local/eclipse`, a location that I excluded from my backups.

Start Eclipse and run `Help > Check for Updates` to ensure it is up-to-date.

### Essential configuration

Now some basic but important configuration.

Under `Windows > Preferences` find preferences for C++ Content Assist: for a shortcut, type "content assist" in the field at the top-left corner of the dialog, see picture below. Make sure your preferences are set as in the picture.
 
 ??? pic1
 
 The go to the "Advanced" sub-section, I recommend you set the options as per picture below.
 
 ???pic2
 
 In the Workspace section, make sure "Build automatically" and "Save automatically before build" are selected.
 
 ??? pic3
 
 In the Indexer section I recommend to lift some limits, to make the indexer work correctly with Eigen. I have adopted the configuration below with 8 GB of RAM.
 
 ??? pic4
 
 You may skip changes to the Indexer section for the time being. If you get errors in the "Problems" view that don't appear in the "Console" view after a re-build of the project, that is the section to tweak. 

### Useful optional plug-ins

There are some optional plug-ins that are nice to have.

I quite like [IndentGuide](https://sschaef.github.io/IndentGuide/), that provides indentation guides (thin vertical lines) to identify code blocks at a glance.

I also install [ANSI Escape in Console](https://marketplace.eclipse.org/content/ansi-escape-console) which supports ANSI escape characters in the Console, i.e. colors and cursor movements. Not only could my program use them, but also they are used by some unit test frameworks. 



