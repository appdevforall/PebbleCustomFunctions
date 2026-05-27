# PebbleCustomFunctions

PebbleCustomFunctions provides [Code on the Go](https://github.com/appdevforall/CodeOnTheGo) with reusable templates that demonstrate:
*How to write one or more Pebble custom functions and package them into a reusable .jar file
*How to invoke Pebble custom functions and display the results.

## Overview
This repository contains code to create and use Pebble Custom Functions. It also contains shell scripts to build and transfer the templates to a mobile device. These files are:
* **make-build.sh** This script will:
   * Package the files in *core-build* into a template file (.cgt)
   * Transfer the .cgt file to the mobile device's directory */sdcard/Download*
 * **make-example.sh** The script will:
   * Package the files in *core-example* into a template file (.cgt)
   * Transfer the .cgt file to the mobile device's directory */sdcard/Download*
 * **core-build** Source files for the jar builder that holds the executable code for the Pebble Custom Functions
   demonstrated in *core-example*
 * **core-example** Source files for the template that demonstrates how to invoke the Pebble Custom Functions in
   *core-build*
 * **core-build.cgt** is a prebuilt template file for the *core-build* template
 * **core-example.cgt** is prebuilt template file the the *core-example* template

## Requirements
* *Code On the Go*
* Zip utility of your choice
* Do you need to have installed anything template-related with CoGo or is this all automatically included? 


## Customization
Is this section really "customization" or is this section a combination of an overview and a getting started section?
To create your own Pebble Custom Functions, follow these steps:
1. Replace the Pebble source file(s) in\
```PebbleCustomFunctions/core-build/BuildExtensionsActivity/ext/src/main/java/PACKAGE_NAME/EXAMPLE_CODE```\
with the executable code for your own Pebble custom function(s).
2. Change the mapping of function names to classes in:\
```PebbleCustomFunctions/core-build/BuildExtensionsActivity/ext/src/main/java/PACKAGE_NAME/BasicExtensions.kt.peb```
3. Run the *make-build.sh* script to build the template (.cgt) file.
4. Install the template using the instructions in the **Installation** section below.
    
What are we installing here?
## Installing WHAT??
1. Open *Code On the Go*
2. From the main menu, tap <b>Terminal</b>.
   Why would I have already done this? Can I do this using the Clone Git Repo button on the top menu instead since that is  much easier than typing all this?
3. If you have not done so already, clone the repository. Cloning into */sdcard/Download* is recommended\
   ```git clone https://github.com/appdevforall/PebbleCustomFunctions.git```    
4. Copy your .cgt files into the *Code On the Go* templates directory as follows:\
  ``` cp /sdcard/Download/<your cgt filename>.cgt $HOME/../home/.cg/templates ```
5. Exit the Terminal. 

How is this Usage? What am I using? Can we just have a section for creating extensions.jar and a section for using it instead?
## Usage
### Creating the extensions.jar file
Installing the *core-build.cgt* file will create a new template in the *Code On the Go New Project* screen named *Build Extensions*. This template creates a .jar file named *extensions.jar* that contains the executable code to the Pebble custom functions. The *extensions.jar* file **must** be included in any template (.cgt) files that use the custom functions. To create the *extensions.jar* file:
1. On the New project screen, tap the *Build Extensions* template.
2. To include example Pebble functions, check the *Include Sample Functions* checkbox.
3. Tap *Create Project*.
4. After the project has been initialized, tap the *Gradle Tasks* icon in the command slider.
5. In the search bar, enter *:ext:build* and select :ext:buildExtensionsJar* from the drop-down menu.
6. Tap the green arrow. A confirmation message is displayed.
7. Tap the green arrow to start the build.
8. After the build has completed successfully, tap the Project menu to return to the file tree.
9. In the *File Tree*, navigate to \
   ```ext/build/libs```
10. Long-press *extensions.jar* and select *Copy path" from the menu.
11. In the left-hand rail, tap the *Terminal* icon.
To be consistent, please provide the commands to save it in an accessible location because you spell out the commands everywhere else. Also, do I have to use Terminal? Seems a lot easier to use my phone's file manager. And should I be moving the file or making a copy of it in the new location?
12. The *extensions.jar* file needs to be saved in an accessible location (e.g. /sdcard/Download) for later use. The paste action can be used to paste the path previously copied into the copy command. 


### Using The extensions.jar File
To use the Pebble custom function(s) created in the *Build Extensions* template, the extensions.jar file **must** be included in every template (.cgt) file where the custom function is invoked. To ensure that the file is included, follow these steps: 
For #1, where WHICH template can be unzipped?
1. Create a directory where the template can be unzipped.
2. Unzip the template file (.cgt) into that directory.
   Below, is this my new extensions.jar file?
3. Copy the *extensions.jar* file into the top level of the directory.
  Below, remove the old cgt file from where? From the directory where I expanded the template? And which is the old .cgt file? Is it the one I just unzipped?
4. Remove the old .cgt file.
   Are those parameters (-r -9 etc) recommended and if so why? 
6. Using your zip utility, create a new .cgt file. e.g.\
   ```zip -r -9 -D ../<mycgtfile>.cgt *```
7. Copy the new .cgt file into the templates directory using the steps in the **Installation** section. 


