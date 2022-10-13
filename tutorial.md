# How to Change a Folder's Icon using Terminal in Mac OSX
---

```Difficulty: Medium - Time Required: 30 minutes  - By: Ila Wallace```


---
## Introduction
This tutorial will show you how to change the default folder icon into your own custom folder icon using Terminal in Mac OSX.

After the completion of this tutorial, you will be able to navigate through the Mac OSX directory in Terminal and assign your own custom .png image as a folder icon.

---
## Requirements
To complete this tutorial, you will need access to a Mac OSX computer that can run a UNIX runtime environment in the application Terminal. You must also have a basic understanding of how to use a Mac OSX computer.

Additionally, you will need to have Xcode command line tools installed. If you do not already have it installed, the installation instructrions are provided in [Xcode Command Line Tools](#xcode-command-line-tools).

Lastly, you will need to have a custom folder icon picked out in the form of a .png file. If you do not have one, you may use one of the default options provided in [Default Icons](#default-icons).

> **Warning**
> This is a warning and is it working?

> **Warning** 
> 
> Make sure to have a backup of all important files in a separate
> location like on a flash drive or in OneDrive before procedding any
> further. Using a UNIX Terminal on any computer can change the
> computer's file system and data.

> **Warning**
> This is a warning. Is it working?

----------
### Table of Contents
  - [Opening Terminal](#opening-terminal)
  - [Downloads](#downloads)
    - [Xcode Command Line Tools](#xcode-command-line-tools)
    - [Default Icons](#default-icons)
  - [Navigating Directories](#navigating-directories)
    - [Current Location](#current-location)
    - [Changing Locations](#changing-locations)
  - [Creating Icons](#creating-icons)
  - [Adding Icons](#adding-icons)
    - [Attaching Icons](#attaching-icons)
    - [Hiding Icons](#hiding-icons)
  - [Removing Icons](#removing-icons)
  - [Wrap Up](#wrap-up)
  - [FAQ](#faq)
  - [Further Reading](#further-reading)

-----------------
## Opening Terminal

To open the Terminal application, you must do the following:

1) Click on the ``Spotlight Search`` icon located in the menu bar at the top right of the home desktop screen. 
   
   [insert image here]

   Note: If you do not have the icon in your menu, you can alternatively use the Command ⌘ + Space keyboard shortcut. 

2) Type the following text into the ``Spotlight Search`` popup:

   ```sh
   Terminal
   ```


3) Click on the first result called ``Terminal``. The application should have a new terminal window open with its icon appearing in your ``Dock``.

   [insert image here]



> **Pro-tip:** You can add ``Terminal`` to your ``Dock`` for faster access in future projects.
> <details> <summary>Click here to see more</summary>
> <br>
> With the application open, click and hold its icon. Drag it to your desired location in the dock and release. Or alternatively, click on the icon, hover over the 'Options' option, and click on `Keep in Dock`. </details>

----------------------
## Downloads

The downloads required for this tutorial are Xcode command line tools and at least one .png image file.

> **Note:** Xcode command line tools will take up about 2.84 GB of space on your computer. Image files will vary in size.

### Xcode Command Line Tools

To install Xcode command line tools, you must do the following:

1) Open a new `Terminal` window

2) Type the following text into the terminal prompt:

   ```sh
   xcode-select --install
   ```

3) When the pop up appears asking you if you would like to install the tools, click on the option ``Install``.

4) When the pop up appears stating the software was installed, click on the ``Done`` option.

If you would like to confirm your download, open a new `Terminal` window. Then, type the following text into the prompt: ``xcode-select -v``. This command will print your Xcode tools current installed version to the console.

For more details on how to install Xcode tools, click [here](<https://mac.install.guide/commandlinetools/4.html>).



### Default Icons

If you do not have a custom icon png file on hand, you can download some icons from the following list:
- (website)
- (website)
- (website)

--------------------------------------
## Navigating the Directory
When using ``Terminal`` for any task, it is important to have a basic understanding of where our current location in the Mac OSX directory file system, what items are nearby, and how to move through the directory file system.

If you know how to navigate a directory file system in ``Terminal``, you may skip to [Creating Icons](#creating-icons).(#creating-the-icon)

### Current Location

To identify our current location in the directory tree, we can use ``pwd``.

1) Type `pwd` into the terminal prompt and hit `Return`

   insert image here

The output is ``Users/username``, where username is the name of your computer's current user.

To identify what items are located in our current location, we can use ``ls``.

2) Type ``ls`` into the terminal prompt and hit `Return`

The out


### Changing Locations







--------------------------------
## Creating Icons

## Attaching Icons

## Removing Icons

## Wrap Up

## FAQ

## Further Reading



---------------------------------
Some text

- Instruction 1
- Instruction 2
- Instruction 3



Here goes all the budgets



Some text

```text
folder1/
└── folder2/
    ├── folder3/
    │   ├── file1
    │   └── file2
    └── folder4/
        ├── file3
        └── file4
```



Have a bug or a feature request? Please first read the [issue guidelines](https://reponame/blob/master/CONTRIBUTING.md) and search for existing and closed issues. If your problem or idea is not addressed yet, [please open a new issue](https://reponame/issues/new).

## Contributing

Please read through our [contributing guidelines](https://reponame/blob/master/CONTRIBUTING.md). Included are directions for opening issues, coding standards, and notes on development.

Moreover, all HTML and CSS should conform to the [Code Guide](https://github.com/mdo/code-guide), maintained by [Main author](https://github.com/usernamemainauthor).

Editor preferences are available in the [editor config](https://reponame/blob/master/.editorconfig) for easy use in common text editors. Read more and download plugins at <https://editorconfig.org/>.



- <https://github.com/usernamecreator1>



Some Text

## Copyright and license

Code and documentation copyright 2011-2018 the authors. Code released under the [MIT License](https://reponame/blob/master/LICENSE).




<details>
<summary>Click here to see more</summary>
<br>
This is how you dropdown.
</details>
