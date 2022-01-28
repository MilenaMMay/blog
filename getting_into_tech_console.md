# Getting into tech: explore the console

I recently talked with a friend who'd like to get into tech and didn't know where to start. It can feel intimidating to think about starting into this field that techies have studied many years until they started their first job.
But I also know some techies who came from a non tech background and now are excellent in their tech job. So I wanted to support her to get a first hands on glimpse into tech. 👩‍💻

If you're also interested in getting into tech or want to support a non techie to become one, here's what I shared with her to get started:

## How do computers work?

Computers are structured in layers: the lowest level is the hardware.

* Harddrives / Storage: stores files and programs
* RAM (Random Access Memory): stores what you need temporarily, e.g. program code that you are just executing
* CPU (Central Processing Unit): does calculations, executes programs

She has a Mac, so I asked her to open "About this Mac" and we explored the hardware listed there: how many GB of RAM, how many TB of storage...

The software that runs on the hardware is itself composed in many layers:
* the Operating System (OS) abstracts the usage of specific hardware and provides standard commands to use it, i.e. MacOS, Linux or Windows
* Programming Languages provide more sophisticated concepts to write more complex applications, i.e. Java, Javascript, Go, C/C++, C#, Kotlin, Ruby, Python and many more
* Applications are run on top of it, i.e. the Browser, visual Text Editors, Games...

## How does the command line work?

To get her hands on with executing her first commands, I chose the command line because it requires no setup. I think if you want to get hands on it can be very frustrating to first install dependencies and configure your development environment. Nearly no setup is hazzle free and going through trial-and-error with cryptic error messages without understanding at which level they occur and how to find solutions might put you off to continue.

The console or terminal or shell however, is installed on every device as it is part of the operating system. I shared with her some UNIX commands. Both MacOS and Linux are based on UNIX. If you want to use them on a Windows machine, you need the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install).

* open the terminal (it's an app that you can find on MacOS by using the search)
* tipps: 
  * you can repeat previous commands by hitting the arrow up key
  * you can autocomplete commands or file or directory names by hitting tab when you wrote the first characters or the word
* type `ls -l` to list the files in your current folder (always hit enter after a command)
* type `cd ` (change directory) and add the name of the directory (folder) that you want to open 
* type `ls -l` and you see the content of the newly opened folder 🎉
* type `ps aux` to see the process status of all processes (programs) that are running on your computer - wow, that's a lot! 😮 
  * skim through it to get a basic understanding what your computer is doing. 
  * notice that CPU and Memory usage are listed
  * you find the same information in your Activity Monitor. It's just an UI build on top of it.
* reduce the list by filtering it with `ps aux | grep System`
  * the pipe `|` concatenates (i.e. joins) two commands: it takes the output of the first one as input of the second
  * `grep` searches for a pattern (in this case "System" is our search pattern)
* even more than two commands can be chained, type `ps aux | grep System > foo.txt` to write the output to a text file (`>` is the write operation)
* find your newly created file in the list: `ls -l` 🎉
* print the content of the file with `cat foo.txt`
* we're just looking at the system in a more basic way than you're used to: you also find the file in your Finder and can open it with the text editor of your choice
* why is the print command called `cat`? Let's look at the manpage: `man cat`
  * `cat` is not a 🐱 and `man` is not a 🧔‍♂️: 
  * `man` stands for manual and will explain every command to you - try it with the other commands you already learned like `ls`, `cd`, `ps`
  * `cat` stands for concatenate and joins characters and prints them
  * within a manpage you can scroll with enter or arrow down and up, to leave the manpage type `q` for  quit
  * by looking at the manpage for `cat` you learn to use parameters - type `cat -n foo.txt` to add line numbers to the output
* type `vi hello.txt` to open the text editor vi (or vim)
  * now your in vi's "command mode" and before you can start typing hit `i` for insert
  * write some lines that contain "hello" and some lines that don't
  * to exit insert mode hit ESC
  * now you're in command mode again and if you want to position your cursor, hit `j` for down, `k` for up and `w` (word) for jumping word by word
  * you can hit `i` again to wite something at the point your cursor is
  * hit ESC again and type `:wq` to write and quite the file - see that this command is written in the bottom left. `:` gets you from command mode into "last line mode" where specific commands can be executed
  * after hitting enter you left vi and can now `cat hello.txt` to see the content of the file you just created 🎉

It was fun for her to explore the console like that and I also really enjoyed the hour I spent unveiling the curtain and showing a glimpse into my techie world. 😃 

I think this is an easy way to start into tech because it requires no setup (if you have a Mac or Linux System). Understanding these concepts already helps you to understand if you like the way of thinking like a techie. 🤓

Having the tools now to explore, go and find more commands, read their manpages and combine them! 🚀

⬅️ [Back](/blog)
