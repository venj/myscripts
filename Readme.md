My Scripts
==========

These are my daily scripts with a command wrapper to avoid naming conflict with system and 3rd-party commands. Only usable on a mac. Very sluppy, maybe **ONLY** useful to me.

Install
=======

1. clone to `/usr/local/bin/`
2. enter `my list` to see available commands 
3. enter `my info` to see all command description
4. enter `my info SOME_CMD` see individual command description

Usage
=====

The core to this repository is the wrapper script: `my`. This wrapper script will search for other scripts located in `/usr/local/bin/myscripts`. The reason why I write this wrapper script is to prevent my own utility scripts polluting system commands. Yes, it is also mean to prevent naming confilicts. 

I also include all the scripts that I use in this repo, so if you want to use it for your own, please fork this repository before you use it. 

The `my` wrapper
----------------

* `my SOME_COMMAND # Used to run a command.`
* `my list # List all the commands available`
* `my edit [SOME_COMMAND] # Edit a command/script, if not exists, it will create a new one. If no command specified, it will edit the 'my' wrapper script.`
* `my chmodx SOME_COMMAND # Make a script executable, esp. it is newly created.`
* `my info [SOME_COMMAND] # List command infomation. If SOME_COMMAND is not specified, it will list all command infomation.`
* `my cat [SOME_COMMAND] # Print out the script source code. If SOME_COMMAND is not specified, it will print the 'my' wrapper script.`
* `my help # Show help infomation.`

Misc
====

Fork me if you really decide to use it for your own.
