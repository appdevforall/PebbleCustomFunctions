# PebbleCustomFunctions

PebbleCustomFunctions is a  designed for 
[Code on the Go](https://github.com/appdevforall/CodeOnTheGo).
It provides a set of reusable functions to:
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

## Installation
1. Open *Code On the Go*
2. From the main menu select *Terminal*
3. If you have not done so already, from the Termux window clone the repository, cloning into */sdcard/Download* is recommended\
   ```git clone https://github.com/appdevforall/PebbleCustomFunctions.git```    
4. Copy your cgt files into the *Code On the Go* templates directory as follows:\
  ``` cp /sdcard/Download/*.cgt $HOME/../home/.cg/templates ```
6. *exit* Termux

## Usage
