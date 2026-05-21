# PebbleCustomFunctions

PebbleCustomFunctions is a  designed for 
[Code on the Go](https://github.com/appdevforall/CodeOnTheGo).
It provides a set of reusable templates to:
* Show how to write one or more Pebble Custom Functions and package them into a reusable jar file
* Show how to invoke the Pebble Custom Functions and display the results

## Overview
This repository contains code to create and use Pebble Custom Functions. It also contains shell scripts to build and transfer the templates to a mobile device. These files are:
* **make-build.sh** This script will
   * package the files in *core-build* into a template file (.cgt)
   * transfer the cgt file to the mobile device's directory */sdcard/Download*
 * **make-example.sh** The script will do the same as **make-build.sh** but for the files in *core-example*
 * **core-build** Source files for the jar builder that holds the executable code for the Pebble Custom Functions
   demonstrated in *core-example*
 * **core-example** Source files for the template that demonstrates how to invoke the Pebble Custom Functions in
   *core-build*
 * **core-buld.cgt** prebuilt template file for the *core-build* template
 * **core-example.cgt** prebuilt template file the the *core-example* template

## Requirements
. *Code On the Go*
. *zip* utilty
. replace the *adb* command in the shell scripts with a copy command, if needed 

## Customization
To create your own Pebble Custom Fuctions, you need to:\
* Replace the Pebble source file(s) in\
```PebbleCustomFunctions/core-build/BuildExtensionsActivity/ext/src/main/java/PACKAGE_NAME/EXAMPLE_CODE```\
with the executable code for your own Pebble Custom Function(s)
* Change the mapping of function names to classes in:\
```PebbleCustomFunctions/core-build/BuildExtensionsActivity/ext/src/main/java/PACKAGE_NAME/BasicExtensions.kt.peb```
* Run the *make-build.sh* script to build the template (cgt) file
* Install it as shown in the **Installation** section
    

## Installation
1. Open *Code On the Go*
2. From the main menu select *Terminal*
3. If you have not done so already, from the Termux window clone the repository, cloning into */sdcard/Download* is recommended\
   ```git clone https://github.com/appdevforall/PebbleCustomFunctions.git```    
4. Copy your cgt files into the *Code On the Go* templates directory as follows:\
  ``` cp /sdcard/Download/*.cgt $HOME/../home/.cg/templates ```
6. *exit* Termux

## Usage
Installing the *core-build.cgt* file will create a new template in the *Code On the Go New Project* screen named *Build Extensions*. This template is used to create a jar file named *extension.jar* which contains the exectable code to the Pebble Custion Functions. This file **must** be included in any template (cgt) files that use them. To create the *extensions.jar* file:
1. Select the *Build Extensions* template from the *New Project* screen
2. If the *Include Sample Functions* checkbox is checked, then the example Pebble Functions will be created
3. Select *Create Project*
4. After the project has been initialized successfully, select the *Gradle Tasks* icon from the action bar
5. In the search bar, enter *:ext:build* and select :ext:buildExtensionsJar* from the drop-down menu
6. Select the green run arrow twice to start the build
7. After the build has completed successfully, return to the *File tree* by selecting the *Project Menu* icon
8. In the *File Tree*, navigate to \
   ```ext/build/libs```
9.  Long press on *extensions.jar* and select *Copy path" from the menu
10.  


