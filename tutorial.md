# How to Change a Folder's Icon using Terminal in Mac OSX
> Difficulty: Medium - Time Required: 45 minutes  - By: Ila Wallace

---
## Introduction

This tutorial will teach you how to change the default folder icon into your own custom folder icon using Terminal in Mac OSX.

After the completion of this tutorial, you will be able to navigate through the Mac OSX directory in Terminal and assign your own custom .png image as a folder icon.

---
## Requirements
To complete this tutorial, you will need access to a Mac OSX computer with at least 5 GB of available memory space. You must also have a basic understanding of how to use a Mac OSX computer and how to back up files.

Additionally, you will need to have Xcode command line tools installed. If you do not already have it installed, the section [Installing Xcode Command Line](#installing-xcode-command-line-tools) helps guide you through the installation process. 

Lastly, you will need to create a target folder and download a custom icon picked out in the form of a .png file placed inside. If you do not have an image file, you may choose from one of the default options provided in the section [Downloading a Custom Icon](#downloading-a-custom-icon).

<br>

> **Warning**:
> If you have any important files on your desktop, make sure to back up
> these files in a separate location like on a flash drive or in
> OneDrive before proceeding any further. Using a UNIX Terminal can
> change your computer's file system and its data.

<br>

---
---
### Table of Contents
  - [Introduction to Terminal](#introduction-to-terminal)
      - [Table of Terminal Commands](#table-of-terminal-commands)
  - [Getting Started](#getting-started)
    - [Creating a New Folder](#creating-a-new-folder)
    - [Downloading a Custom Icon](#downloading-a-custom-icon)
    - [Opening a New Terminal Window](#opening-a-new-terminal-window)
    - [Installing Xcode Command Line Tools](#installing-xcode-command-line-tools)
  - [Navigating a Directory](#navigating-a-directory)
    - [Identifying the Current Location](#identifying-the-current-location)
    - [Changing the Current Location](#changing-the-current-location)
  - [Changing a Folder's Default Icon](#changing-a-folders-default-icon)
    - [Generating a Custom Icon for a Folder](#generating-a-custom-icon-for-a-folder)
    - [Attaching a Custom Icon to a Folder](#attaching-a-custom-icon-to-a-folder)
    - [Hiding a Custom Icon in a Folder](#hiding-a-custom-icon-in-a-folder)
    - [Removing a Custom Icon from a Folder](#removing-a-custom-icon-from-a-folder)
  - [Wrap Up](#wrap-up)
    - [Further Reading](#further-reading)
--- 

## Introduction to Terminal



<!--Terminal Commands List-->
### Table of Terminal Commands

This table lists all terminal commands used within this tutorial and states briefly what they do.

| Terminal Commands | Description |
| ----------- | ----------- |
| `xcode-select --install` | Installs Xcode command line tools |
| ```xcode-select -v``` | Prints the current version of installed Xcode command line tools |
| ```sips -i icon.png``` | Formats image `.png` file to icon `.png` file |
|```DeRez -only icns icon.png > tmpicns.rsrc``` | Converts `.png` file to `.icns` file referenced through the `tmpicns.rsrc` file | 
| ```Rez -a tmpicns.rsrc -o Icon$'\r'```| Generates `Icon?` file from `.icns` reference file|
| ``SetFile -a C .`` | Sets `Icon?` file  as the folder's custom icon |
| ``SetFile -a V Icon$'\r'``| Hides the `Icon?` file inside the folder |
| ``rm tmpicns.rsrc icon.png``| Removes unecessary leftover files |
| ``rm Icon$'\r'`` | Deletes the custom icon from the folder |

<br>

---

## Getting Started

The downloads required for this tutorial are Xcode command line tools and at least one .png image file. Additionally, you will need to create a new folder on your desktop and place the image file inside.



<!--Making a Folder-->
### Creating a New Folder
If you know how to create a new folder, rename your folder as ``custom`` and place your custom image into the folder. Then, skip to [Navigating Directories](#navigating-directories).

> **Note**: For the purposes of this tutorial, we will name and refer to the new folder as ``custom``, but you can give the folder your own personalized name.

<br>

To create a new folder, you must do the following:

1) Navigate to your desktop home screen
   
2) Move your cursor to a preferred location and then press two fingers down on the track pad, or if you have an external mouse, right click on the folder to select it
   
3) Click on the option ``New Folder``
   
You should now see a blue default folder icon appear on your desktop. 

<br>


To rename the folder, you must do the following:

1) Place your cursor over the folder and then select the new folder by either pressing two fingers down on the track pad or right click on the folder to select it
   
2) Click on the option ``Rename``
   
3) Type ``custom`` and then hit  `Return↩︎`
   
Your folder should now be named ``custom``.


<br>

Lastly, select the image file with your cursor and then drag it into the ``custom`` folder. 

<br>

> **Checkpoint**: The custom image should now be inside the ``custom`` folder.

<br>

<!--Downloading Image File-->
### Downloading a Custom Icon
In order to change the default folder icon, we need to have a new icon file to change it to.

If you have a custom icon downloaded to your computer, move a copy of the image to the icon to your desktop and name it ``icon.png``. 

If you do not have a custom .png file on hand, you can download an icon from [here](<https://icons8.com/icons/set/mac-folder>). Make sure to name it ``icon.png`` and save it to your desktop.

<br>

> **Checkpoint**: The custom image ``icon.png`` should now be saved on your desktop.

<br>

<!--Opening Terminal-->
### Opening a New Terminal Window
To open the Terminal application, you must do the following:

1) Press both the `Command ⌘` and `Space bar` keys on your keyboard at the same time to open ``Spotlight Search``

2) Type the following text into the ``Spotlight Search`` prompt:
   
   ```sh
   Terminal
   ```


3) Press `Return↩︎` on your keyboard.

<br>

> **Checkpoint**: A new Terminal window should be open and visible on your screen.

<br>



<!--Xcode tools installation-->
### Installing Xcode Command Line Tools
To install Xcode command line tools, you must do the following:

1) Open a new `Terminal` window

2) Type the following text into the prompt:

   ```sh
   xcode-select --install
   ```

3) When the pop up appears asking you if you would like to install the tools, click on the option ``Install``.

4) When the pop up appears stating the software was installed, click on the ``Done`` option.

<br>

If you would like to confirm your download, you can do the following:

1) Open a new `Terminal` window 
2) Type the following text into the prompt and then press `Return↩︎`:
   
   ```sh
   xcode-select -v
   ```
   
The resulting output prints your Xcode tools current installed version to the console. 

<br>

> **Checkpoint**: The Xcode command line tools should be installed on your computer.


<br>


---

## Navigating a Directory
When using ``Terminal`` for any task, it is important to have a basic understanding of where our current location in the Mac OSX directory file system and how to move through the directory file system.

If you know how to navigate a directory file system in ``Terminal``, you may skip to [Generating Icons](#generating-icons).

<br>

<!--Finding the working directory location-->
### Current Location
To identify our current location in the directory tree, we can use ``pwd``.

Type the following text into the terminal prompt and then hit `Return↩︎`:


  ```sh
  pwd
  ```


The output printed to the console is shown below, where `username` is the name of your computer's current user.
```text
  $ Users/username
```

> **Note**:
> If the output printed to the console does not match the output format, type the following
> and then hit `Return↩︎`:
> ```sh
> cd ~; pwd
> ```

<br>
The figure below is an asbtract representation of our current location. Congrats, you are now in your computer's home directory!

```text
Users/
└── username/
```

<br>

> **Checkpoint**: The current location should be inside the ``username`` folder directory.

<br>


<!--Moving to folder location-->
### Changing Locations
Now that we know where we are, we need to move to where we need to go. 

> **Note**: For the purpose of this tutorial, we will be working in your
> Desktop directory. If you would like to learn more about how to move
> through other directories, please see [insert link here]. 

<br>

To change our current directory to the Desktop, we can use ``cd``.

Type the following text into the terminal prompt and then hit `Return↩︎`:

```sh
cd Desktop/custom/
```

If you would like to confirm you are in the Desktop directory, type the following text into the terminal prompt and then hit `Return↩︎`:

```sh
pwd
```
Output:

```text
$ /Users/username/Desktop/custom
```

<br>

The figure below is an abstraction of our current location. We are now in the ``custom`` folder directory.
```text
Users/
└── username/
    └── Desktop/
        └── custom/
            ├── icon.png
```

> **Checkpoint**: The current location should be inside the ``custom`` folder directory.

<br>



---
## Changing a Folder's Default Icon

<!--Generating Icon format-->
### Generating a Custom Icon for a Folder
Now that we are in the right location, we can now start converting ``icon.png`` into a usable icon for the ``custom`` folder.

To convert the image file, you must do the following:

1) Type the following text into the terminal prompt and then hit `Return↩︎`:
   ```sh
   sips -i icon.png
   ```
   This command prepares the format of the png file for its transformation into an .icns file.

2) Type the following text into the terminal prompt and then hit `Return↩︎`:
   
   ```sh
   DeRez -only icns icon.png > tmpicns.rsrc
   ```
   This command transforms the .png file into an .icns file and points to the newly converted file using the tmpicns.rsrc file.

3) Type the following text into the terminal prompt and then hit `Return↩︎`:
   
   ```sh
   Rez -a tmpicns.rsrc -o Icon$'\r'
   ```
   This command generates the finalized icon file ``Icon?`` as a usable folder icon.

<br>

> **Checkpoint**: The custom image file ``Icon?`` should be generated inside the ``custom`` folder.

<br>


<!--Add Custom Icon-->
### Attaching a Custom Icon to a Folder
With the correct icon file generated, we can now attach it to the folder itself so it can be displayed.

To attach the icon and set it visible, type the following text into the terminal prompt and then hit `Return↩︎`:

```sh
SetFile -a C .
```

<br>

> **Checkpoint**: The custom image file ``Icon?`` should now be visible as the ``custom`` folder's new icon.

<br>



<!---Hide Icon File-->
### Hiding a Custom Icon in a Folder
To avoid accidental deletion of the ``Icon?`` file, it is best to hide the file from normal view. In addition, removing the ``icon.png`` and ``tmpicns.rsrc`` files helps keep your newly customized folder tidy.

To hide the ``Icon?`` file, type the following text into the terminal prompt and then hit `Return↩︎`:

```sh
SetFile -a V Icon$'\r'
```

<br>

To remove unnecessary files, type the following text into the terminal prompt and then hit `Return↩︎`:

```sh
rm tmpicns.rsrc icon.png
```

<br>


> **Checkpoint**: The custom image file ``Icon?`` should now be invisible in the ``custom``. The files ``tmpicns.rsrc`` and ``icon.png`` should also be gone from the folder.

<br>



<!--Remove Custom Icon-->
### Removing a Custom Icon from a Folder
If at any point you wish to remove the custom icon, you can do so by removing the hidden ``Icon?`` file. 

To remove the icon, type the following text into the terminal prompt and then hit `Return↩︎`:

```sh
rm Icon$'\r'
```

With the file now removed, your folder icon should return to its default icon.


---

## Wrap Up

In this tutorial, you have learned how to:
1) Create a new folder 
2) Download a custom icon .png file
3) Place icons into a folder
4) Open terminal
5) Change to the new folder's directory location
6) Generate the icon file
7) Attach the icon to the folder
8) Hide the icon file
9) Remove unecessary files
10) Remove the custom icon from the folder


### Further Reading
