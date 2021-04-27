---
title: "Getting Started with Homebrew"
date: 2021-04-26T16:08:06-07:00
draft: false
tags:
 - software
---

[Homebrew][1] is a popular package manager which has the ability to install almost any application or software in existence. To start using Homebrew, you&'ll have to open the **command line**, which is the "Terminal" app or program on Mac and Linux and "command.exe" on Windows. 

![ZSH on a Mac](/blog/images/shell.png)

Once in the application or program shown above, type the following command, and hit Return: 


{{< highlight bash >}}
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)
{{< /highlight >}}

The `/bin/bash` should be changed to `/bin/zsh` on Mac. That section of the command tells the command line what **shell** to run the command with. A shell is a type of command line program running system, and [a quick Google Search][2] will give you results about how to change your shell. However, on Mac, ZSH is the default, and should be used. Now, quit the command line, restart it, and try typing the command `brew`. Does the shell return `Example usage:` and then a list of commands? If so, you've got Homebrew up and running. Now you can use all commands associated with a package manager. Happy Brewing!

 [1]: https://brew.sh
 [2]: https://www.google.com/search?q=change+shell+<your+os>
