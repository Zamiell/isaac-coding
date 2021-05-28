## Coding Style

A lot of times, we type up code that works and we don't give it too much thought. But it can be worthwhile to stop to think for a moement about the style that you code in.

It is fairly common for programmers to use conventions from old programming languages when they learn new ones. Jumping between JavaScript, Python, and Perl, I used to have hard-set notions about what was "correct" in terms of whether to use tabs or spaces, how to break up long lines, and so forth.

A really good learning point for me was when I started getting into the [Golang](https://golang.org) programming language in 2014. Golang has a thing called `gofmt`. How it works is that, upon saving a file with Golang source code, the `gofmt` tool is automatically run, and it formats your file using Golang conventions. Spaces are automatically converted to tabs, extra whitespace is removed, and so forth.

At first, this was a little unsightly to me, and I disliked it. But after some time, I got used to having all my Golang code look a certain way. However, when I went out on the internet to read other people's code, I realized something amazing. I could look at it and instantly read it without being distracted by a different coding style. And furthermore, when I needed to steal code-snippets from StackOverflow and elsewhere, **I could just copy-paste their code into my own code without having to change the style or fix anything!** Coming from other languages, this was NOT the norm.

This "feature" of Golang is like a superpower and it really feels amazing. But going beyond Golang, I realized that there is nothing stopping this from happening in all programming languages - people just have to adhere to common standards. So now whenever I program, **I go out of my way to always code in the official (or most-popular) style of the specific programming language that I am coding in**, whether that necessitates tabs, spaces, or anything in between.

I kind of stumbled upon this lesson, but in truth, this concept has been well known to programmers for a long time. Guido, the creator of Python, famously said: ["Readability counts"](https://www.python.org/dev/peps/pep-0008/). One of Guido's great insights was that code is read much more often than it is written.

When you write your own Isaac mods, you could just code it however you want. No-one is stopping you, and it is just an Isaac mod, after all. But remember, readability counts! **Don't write Lua like you would write Python, JavaScript, or anything else. Write Lua like how other Lua coders do.**

While Lua does not have an official style standard [like Python does](https://www.python.org/dev/peps/pep-0008/), **the most popular Lua style guide in the world is the [Lua-Users Wiki style guide](http://lua-users.org/wiki/LuaStyleGuide)**, so it makes a lot of sense to use this and stick to it.

For the love of readability, and in accordance with the Lua-Users Wiki style guide:
  * **don't use tabs, use 2 spaces to indent!**
  * **don't have multiple statements on the same line!**
  * **split up your code into small functions and make your code readable!**

Take some pride in your mod and make it a joy to read for the other modders out there who want to know how it works, copy-paste code snippets, or collaborate with you to add code or fix bugs.

And even if you give the Lua-Users Wiki style guide a read and decide against using it, find another popular style guide and stick to that - all of the code in your codebase should at least be internally consistent!
