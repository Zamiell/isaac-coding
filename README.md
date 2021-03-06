# Coding Mods for The Binding of Isaac: Afterbirth+

You might be wondering: **what text editor should I use to code Lua mods for *[The Binding of Isaac: Afterbirth+](https://store.steampowered.com/app/570660/The_Binding_of_Isaac_Afterbirth/)*?**

<br />

## Table of Contents

1. [The Short Answer](#the-short-answer)
1. [The Long Answer](#the-long-answer)
1. [Installation](#installation)
1. [Community](#community)

<br />

## The Short Answer

### Novice

Are you looking to get started as fast as possible? Do you have zero programming experience? Will you be only working on smaller mods?

If you answered yes to any of the above questions, then use **[Notepad++](https://notepad-plus-plus.org/download/v7.6.3.html)**. It is a fantastic text editor that is simple and fast - there is **no need to invest a bunch of time and effort** in going for more complex solutiions. You may now stop reading this tutorial.

<br />

### Expert

Are you an expert coder? Do you plan to spend hundreds of hours coding Isaac mods? Do you want full auto-complete and type safety?

Then use **[VSCode](https://code.visualstudio.com/)** with [IsaacScript](https://isaacscript.github.io/). You may now stop reading this tutorial.

<br />

## The Long Answer

For experienced coders, Notepad++ doesn't cut it. Here is some stuff that it is missing:

<br />

#### 1) Linting

Nowadays, most programmers use [linters](https://en.wikipedia.org/wiki/Lint_(software)), which are static analysis tools to help catch bugs and force adherence to a style guide. Linters are **especially useful** in weakly-typed languages such as [Lua](https://github.com/mpeterv/luacheck/), [Python](https://www.pylint.org/), and [JavaScript](https://eslint.org/). Even in strongly-typed languages such as [Golang](https://github.com/golangci/golangci-lint/), linters are quickly becoming standard.

Why are linters such a big deal? For example, say that you accidentally make a typo in a variable name (which we all do from time to time). If your text-editor has a linter enabled, it will automatically notify you that the variable does not exist. **Words cannot express** how useful this kind of thing is, which **saves hours of debugging time in the long-run**. 

The best Lua linter out there is called [Luacheck](https://github.com/mpeterv/luacheck/), so you will want a text-editor that supports that.

<br />

#### 2) Auto-Completion

Being able to tab-complete function calls saves you a lot of time. If you've ever programmed in any kind of IDE before, you will know how useful this is. Enough said.

<br />

#### 3) Other Miscellaneous Stuff

* Good syntax highlighting.
* The ability to manage folder structures with minimal hassle (e.g. a "project" view).
* Cross-file search, so you can search your entire mod for instances of a keyword. (And cross-file replace, so that you can easily refactor a function name throughout your entire mod.)
* Git integration, so that you can see which files are changed and so forth. (If you don't already use Git, you should be - it's free and will save you hours of time in the long run.)

<br />

### The Text Editor Meta

Here's a brief summary of the text-editor meta - which text-editor is the best?

Notepad++ is great for both general file viewing and amateur programming. But at some point you will want your code to be compiled or linted on the fly.

#### ZeroBrane

Historically, the typical solution to get this kind of functionality is to use an [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment), or integrated development environment. Lua's best IDE is called [ZeroBrane Studio](https://studio.zerobrane.com/). This is even the solution [encouraged by Spider in the official API](https://moddingofisaac.com/docs/debugging.html).

You can [set up ZeroBrane with Luacheck](https://github.com/pkulchenko/ZeroBraneStudio/issues/768) as of July 2017. And you can also [set up auto-complete](https://github.com/Yusyuriv/Afterbirth-API-for-ZeroBrane) using Yusyuriv's helpful repository. Unfortunately, the API definitions are very old and are missing all of the Booster Pack stuff and all of the Repentance stuff. For this reason alone, I would not recommend using ZeroBrane.

Beyond this:
- ZeroBrane is not as extensible as the modern Chromium-based editors.
- You may feel more comfortable in an editor that is not completely dedicated to Lua - especially if you regularly program in other programming languages.

So, let's move on to discussing more general-purpose editors.

<br />

#### A History of the Best Text Editors

As far as general-purpose editors go, people began to migrate away from Notepad++ to [Sublime Text](https://www.sublimetext.com/) en-mass around 2012. With its darker theme, cool features like multi-cursor input, and greater extensibility, Sublime quickly became known as the best general-purpose editor of the era. And Sublime is cross-platform, so you can have the exact same setup when switching from your PC to your Mac.

However, Sublime Text is not free (costing $80) and is not open-source. In 2015, GitHub came onto the text-editor scene with the completely free and open-source [Atom](https://atom.io/) text editor. Initial adoption was rocky, with users citing how slow the product was. But by the end of 2016, tons of people had migrated over, creating a huge ecosystem with Atom's easy-to-make JavaScript extensions. Atom's main strength is its customizability - you can hack the editor to do anything you want. Like Sublime before it, Atom is cross-platform, and it was widely regarded as the best editor of 2016 and 2017.

[VSCode](https://code.visualstudio.com/) was also released in 2015 by Microsoft, although not many people cared at the time. It uses almost the exact same technology as Atom (being Electron / Chromium based), but it remains under active development by the company. What makes VSCode stand out from Atom is its speed - the editor is noticably faster than Atom, but spouts nearly identical features and equally robust customizability. Because of this, VSCode exploded in popularity in 2018 and has now taken the throne from Atom as the best text-editor for general-purpose programming.

Nowadays, if you are not using ZeroBrane, you should probably be using VSCode. It has Luacheck integration, (some) Afterbirth+ auto-completion, and is very fast. It is also the recommended editor for people using [IsaacScript](https://isaacscript.github.io/).

<br />

## Installation

These are step by step instructions for getting a working Isaac Lua coding environment (VSCode + Luacheck + auto-complete) on a fresh Windows 10. If you are on macOS or Linux, you will have to skip over or tweak the commands accordingly.

Execute the following commands in an administrative command-prompt:

* Install [Chocolatey](https://chocolatey.org/) (if for some reason you don't have it installed already):
  * `@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"`
* Install [VSCode](https://code.visualstudio.com/) and [wget](https://www.gnu.org/software/wget/):
  * `choco install vscode wget -y`
  * `refreshenv`
* Install the [vscode-lua extension](https://marketplace.visualstudio.com/items?itemName=trixnz.vscode-lua) :
  * `code --install-extension trixnz.vscode-lua`
* Install the [Afterbirth+ extension](https://marketplace.visualstudio.com/items?itemName=Zamiel.vscode-isaac-afterbirth-plus):
  * `code --install-extension Zamiel.vscode-isaac-afterbirth-plus`
* Download Luacheck:
  * `choco install wget -y`
  * `mkdir "C:\Program Files\Microsoft VS Code\Lua\"`
  * `wget "https://github.com/mpeterv/luacheck/releases/download/0.23.0/luacheck.exe" -O "C:\Program Files\Microsoft VS Code\Lua\luacheck.exe"` <br />
  (you can put it anywhere you want, but we might as well put it here)
* Download and import a solid set of starting VSCode user settings:
  * `wget "https://raw.githubusercontent.com/Zamiell/isaac-coding/master/settings.json" -O "%APPDATA%\Code\User\settings.json"` <br />
  (feel free to tweak these to your liking)
* Go to your mod directory:
  * `cd "%USERPROFILE%\Documents\My Games\Binding of Isaac Afterbirth+ Mods\my-mod"`
* Download the default [.luacheckrc file](https://luacheck.readthedocs.io/en/stable/config.html) for [new Isaac projects](https://github.com/Zamiell/isaac-coding/blob/master/.luacheckrc):
  * `wget https://raw.githubusercontent.com/Zamiell/isaac-coding/master/.luacheckrc`
* Open VSCode using this directory as the root of the project:
  * `code .`
* Test to see if it the linter is working:
  * Make a new file called "test.lua".
  * Type in "local test".
  * In the bottom-left-hand corner, you should see one warning pop up. Click on it to make the "Problems" pane appear.
  * In this pane, luacheck will report that there is an "unused variable 'test'".
  * You can leave the panel up as you program.

When you program your Isaac mods, all of your code should "pass" the linter with 0 warnings and 0 errors.

<br />

## Community

If you need immediate help, many people in the modding community hang out in the #modding channel of the [BoI Discord server](https://discord.gg/isaac).
