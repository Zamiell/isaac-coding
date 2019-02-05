# Coding Mods for The Binding of Isaac: Afterbirth+

If you are looking to code Lua mods for *[The Binding of Isaac: Afterbirth+](https://store.steampowered.com/app/570660/The_Binding_of_Isaac_Afterbirth/)*, you might be wondering: **what text editor should I use?** Good question.

<br />

## The Short Answer

Are you looking to get started as fast as possible? Do you have zero programming experience? Will you be only working on mods that are around 100-200 lines of code or less? Are you a casual piece of shit?

If yes to any of the above questions, then use **[Notepad++](https://notepad-plus-plus.org/download/v7.6.3.html)**. You may now stop reading this tutorial.

<br />

## The Long Answer

As an expert Isaac mod programmer, Notepad++ doesn't cut it. There are two main things that it lacks:

#### 1) Auto-Completion

Being able to tab-complete function calls saves you a lot of time. If you've ever programmed in any kind of IDE before, you will know how useful this is. Enough said.

#### 2) Linting

Nowadays, most programmers use [linters](https://en.wikipedia.org/wiki/Lint_(software)), which are static analysis tools to help catch bugs and force adherence to a style guide. Linters are **especially useful** in weakly-typed languages such as [Lua](https://github.com/mpeterv/luacheck/), [Python](https://www.pylint.org/), and [JavaScript](https://eslint.org/). Even in strongly-typed languages such as [Golang](https://github.com/golangci/golangci-lint/), linters are quickly becoming the industry standard. If you haven't heard of linters before, it is time to crawl out from underneath that rock and join us in 2019.

For example, say that you accidentally make a typo in a variable name (which we all do from time to time). If your text-editor has a linter enabled, it will automatically notify you that the variable does not exist. Words cannot express how useful this kind of thing is, which saves hours of debugging time in the long-run. 

The best Lua linter out there is called [Luacheck](https://github.com/mpeterv/luacheck/), so you will want a text-editor that supports that.

<br />

### The Text Editor Meta

Here's a brief summary of the text-editor meta - which text-editor is the best?

Notepad++ has historically been extremely popular among amateur programmers, but at some point you need something better, as you will want your code to be compiled and linted on the fly.

#### ZeroBrane

The typically solution for this kind of functionality is to get an [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment), or integrated development environment. Lua's best IDE is called [ZeroBrane Studio](https://studio.zerobrane.com/). This is even the solution [encouraged by Spider in the official API](https://moddingofisaac.com/docs/debugging.html).

In order to get auto-completion in ZeroBrane, you will need to use [Yusyuriv's helpful repository](https://github.com/Yusyuriv/Afterbirth-API-for-ZeroBrane). Unfortunately, this is not completely up to date for the latest patches.

I don't have any experience setting up ZeroBrane with Luacheck, although [it does appear possible as of July 2017](https://github.com/pkulchenko/ZeroBraneStudio/issues/768). You are on your own here.

ZeroBrane isn't for everyone. One problem with it is its extensibility - you may not be able to configure it to your liking. 
Lastly, you may feel more comfortable in using a general-purpose editor that is not completely dedicated to Lua, especially if you program other projects in JavaScript, Python, etc. So if you don't want to use ZeroBrane, then let's talk about general-purpose editors.

#### A History of the Best Text Editors

As far as general-purpose editors go, people began to migrate away from Notepad++ en-mass around 2012 to [Sublime Text](https://www.sublimetext.com/) and it quickly became the best-known general-purpose editor. Besides being completely cross-platform, Sublime Text is generally more extensible and has cool features like multi cursor input.

However, Sublime Text is not free (costing $80) and is not open-source. GitHub came onto the text-editor scene with [Atom](https://atom.io/) in 2015. Atom is completely free and open-source. Initial adoption was rocky, with users citing how slow the product was, but by the end of 2016 a huge swathe of programmers has migrated, creating a huge ecosystem with Atom's easy-to-make JavaScript extensions. Atom's main strength is its customizability - you can literally hack the editor to do anything you want. Atom was a strong contender for the best editor of 2017.

VSCode was also released in 2015 by Microsoft. It uses almost the exact same technology as Atom (being Electron / Chromium based), but it remains under active development by the company. What makes VSCode stand out from Atom is its speed - the editor is noticably faster than Atom, but spouts nearly identical features and equally robust customizability. Because of this, VSCode exploded in popularity in 2018 and has now taken the throne from Atom as the best text-editor for general-purpose programming.

It is now 2019, so you should probably be using VSCode. It has Luacheck integration, tab-completion, it is fast, everyone uses it, and it might also make you a more attractive and charismatic person.

**TL;DR Use VSCode, you fucking noobs.**

<br />

## Installation

These are step by step instructions for getting a working Isaac coding environment on a fresh Windows 10. If you are on macOS or Linux, you'll have to tweak the instructions accordingly.

Execute the following commands in an administrative command-prompt:

* Install [Chocolatey](https://chocolatey.org/):
  * `@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"`
* Install Luacheck:
  * https://github.com/mpeterv/luacheck/releases
* Install [VSCode](https://code.visualstudio.com/) and the Lua extension:
  * `choco install vscode -y`
  * `refreshenv`
  * `code --install-extension vscode-lua`

TODO

<br />

## Style

When coding your Isaac mod, what style should you code in? The answer is simple. Use the most popular style guide in the world: http://lua-users.org/wiki/LuaStyleGuide

A lot of people try to use conventions from old programming languages when they learn new ones (including me back in the day). Jumping between JavaScript, Python, and Perl, I had hard-set notions about what was "correct" in the questions of whether to use tabs or spaces, how to break up long lines, and so forth.

A really good learning point for me was when I started getting into the [Golang](https://golang.org) programming language. Golang has a thing called `gofmt`. How it works is that, upon saving a file, all code is formatted automatically using Golang conventions - you don't even have to think about it. Spaces are automatically converted to tabs, extra whitespace is removed, and so forth.

At first, this was unsightly to me and I disliked it. But eventually, I was used to having all my Golang code look a certain way, and it did not bother. But then, when I went out on the internet to read other people's code and copy code-snippets from other programs, I realized something amazing. I could look at any piece of Go code out there that someone else wrote and be able to instantly read it without being distracted by a different coding style. And furthermore, I could just copy-paste their code into my own code without having to fix anything! Coming from the Perl/JavaScript world, this was NOT the norm. 

This "feature" of Golang is amazing! I feel that I have been shown the light, so to speak. Now, when going to a new programming language, **I always go out of my way to always code in the "official" style of that programming language**, whether it be tabs, spaces, or anything in between. This is actually a concept that has been understood for a long time, as Guido, the creator of Python famously said: ["Readability counts"](https://www.python.org/dev/peps/pep-0008/).

So, when you write your own Isaac mods, don't just code it however the fuck you want! I mean, you can. No-one is stopping you, and it is just an Isaac mod, after all. But readability counts! For the love of readability, in accordance with the Lua-Users Wiki style guide:
  * **don't use tabs!**
  * **use 2 spaces to indent!**
  * **put spaces between your operators!**
  * **don't have multiple statements on the same line!**
  * **just read the fucking style guide, it takes 5 minutes!**

<br />

## Community

If you need immediate help, many people in the modding community hang out in the #modding channel of the [BoI Discord server](https://discord.gg/isaac).
