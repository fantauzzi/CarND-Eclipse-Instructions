# Eclipse CDT for  Udacity's Self-Driving Car Nanodegree Program

I am providing instructions to use Eclipse CDT (C++) under Ubuntu to develop projects for Udacity's Self-Driving Car Nanodegree.  

Eclipse is a feature-rich IDE that includes integration with GNU GCC, the GDB debugger and GIT versioning system. If one is new to it, it may have some learning curve. Its configuration needs to be tweaked to develop efficiently the C++ projects for the Nanodegree program. This guide wants to give a quick start to those new to Eclipse, or familiar with its Java support.

## Applicability 
 
If one develops his/her C++ projects on a PC, I strongly recommend to adopt a "proper" installation of Ubuntu 16.04, in dual-boot with Windows if desired. It will provide the best compatibility with the needed libraries and simulators, and fewer configuration troubles. In case of issues, an on-line search will almost invariably find possible solutions (mostly from Stackoverflow or Askubuntu).
  
I have tested these instructions under Ubuntu 16.04 64-bit. They do not apply to the Ubuntu shell for Windows.

## Installation and Configuration

The next sub-sections cover how to have Eclipse CDT up-and-running and properly configured for all projects. Further below there are instructions specific to making a project.

### First installation

Download and run the [Eclipse Installer](http://www.eclipse.org/downloads/eclipse-packages/), and direct it to install Eclipse CDT.

Eclipse does not need superuser privileges for installation or to be run. I like to install it under `~/.local/eclipse`, a location that I excluded from my backups.

Start Eclipse and run `Help > Check for Updates` to ensure it is up-to-date.

### Essential configuration

Now some basic but important configuration.

Under `Windows > Preferences` find preferences for C++ Content Assist: for a shortcut, type "content assist" in the field at the top-left corner of the dialog, see picture below. Make sure your preferences are set as in the picture.
 
 ??? pic1
 
 Then go to the "Advanced" sub-section, I recommend you set the options as per picture below.
 
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

To go easy on the eyes, especially at night, the [Darkest Dark Theme](https://marketplace.eclipse.org/content/darkest-dark-theme) is a good one.

These plug-ins add specific sections to the `Windows > Preferences` dialogue, for their configuration. It is easy to find them using the shortcut text entry at the top left of the dialogue. 

??? pic5

## Making the Eclipse Project

The Self-Driving Car Nanodegree program provides, for each project, some "starter code". There are two ways to take it under Eclipse. In this document I show how to make a new Eclipse project from scratch. For the alternative approach, generating the Eclipse project with Cmake, see https://github.com/udacity/CarND-Extended-Kalman-Filter-Project/tree/master/ide_profiles/Eclipse .

### Build the project with Cmake

It is good to try build the project starter code with Cmake alone, no Eclipse involved. One can verify that project dependencies are met and working properly. Then there is a solid baseline from where to add the Eclipse project.

To build the starter code:
* clone the GitHub repository;
* go into the project directory;
* type

```bash
mkdir build
cd build
cmake ..
make
```

If it all goes well, you should get an executable that, once run, won't do much, or may core dump right away. If there are errors, you should resolve them before trying to take the project under Eclipse.

### Making a new Eclipse project from scratch

Having verified the starte-code builds with cmake/make, remove the `build` directory and rename Cmake files, otherwise they will mess-up the new Eclipse project; from the project directory:
 
```bash
rm -rf build
mv CMakeLists.txt CMakeLists.txt.orig
mv cmakepatch.txt cmakepatch.txt.orig
```
Now you are all set to make a new Eclipse project. From Eclipse `File > New C++ Project` (also see picture below).

Uncheck "Use default location" and browse to the directory where you cloned the repository.

Assign a project name; I usually adopt the same as the repository name (which is also the directory name). Note the project name must be unique in your Eclipse workspace; if not, the dialogue will tell you.

From `Project type` choose `Empty Project` and from `Toolchains` choose `Linux GCC`.

The dialogue will warn that the directory with specified name already exists; that is OK.

Click `Finish`

??? picture here

### Configuring the project

Before trying to build and run the program for the first time, you need to apply some settings to the project.

If you don't see a `Project Explorer`, then open it with `Window > Show View > Project Explorer`.

Make sure the new project is selected in the `Project Explorer`, right-click on it and choose `Properties`; or also from the main menu `Project > Properties'.








