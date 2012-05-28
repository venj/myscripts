# My Scripts

## Description

These are my daily scripts with a command wrapper to avoid naming conflict with system and 3rd-party commands. Only usable on a mac. Very sluppy, maybe **ONLY** useful to me.

## Install

1. clone to `/usr/local/bin/`
2. enter `my list` to see available commands 
3. enter `my info` to see all command description
4. enter `my info SOME_CMD` see individual command description
5. You may want to create a symbolic link (or an alias) named `mate` to your favorite editor

## Usage

The core to this repository is the wrapper script: `my`. This wrapper script will search for other scripts located in `/usr/local/bin/myscripts`. The reason why I write this wrapper script is to prevent my own utility scripts polluting system commands. Yes, it is also mean to prevent naming confilicts. 

I also include all the scripts that I use in this repo, so if you want to use it for your own, please fork this repository before you use it. 

### The `my` wrapper

* `my [SOME_COMMAND]` # Used to run a command. If no command specified, it will show help.
* `my list` # List all the commands available
* `my edit [SOME_COMMAND]` # Edit a command/script, if not exists, it will create a new one. If no command specified, it will edit the 'my' wrapper script.
* `my chmodx SOME_COMMAND` # Make a script executable, esp. it is newly created.
* `my info [SOME_COMMAND]` # List command infomation. If command is not specified, it will list all command infomation.
* `my cat [SOME_COMMAND]` # Print out the script source code. If command is not specified, it will print the 'my' wrapper script.
* `my help` # Show help infomation.

## Add your own script

1. `my edit new_script` (or `my e new_script` for short) will create a new script named `new_script` in `/usr/local/bin/myscripts`
2. Don't forget use shibang (`#!`) as the first line of the script
3. You can optionally add a encoding line for your script if the script is not ASCII encoded
4. Add one comment line for script description then.
5. Now start to write your own script as you normally do
6. When you're done, make your script executable with `my chmodx new_script` or just `my x new_script`
7. You are ready to use your script with `my new_script`

Here is am example script template (`new_script`): 

```ruby
#!/usr/bin/env ruby
# encoding = utf-8
# This is a simple hello world script for "my" wrapper.
def hello
  if ARGV.size > 0
    puts "你好, " + ARGV.join(" ")
  else
    puts "你好, 世界。"
  end
end

hello
```

## Misc

Fork me if you really decide to use it for your own.
