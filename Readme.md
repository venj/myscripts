# My Scripts

## Description

These are my daily scripts with a command wrapper to avoid naming conflict with system and 3rd-party commands. Only usable on a mac. Very sluppy, use at your own risk.

## Install/Upgrade

*Be sure to fork this repository before you install and edit following install script properly!!!*

You can use following install script to install and upgrade:

```bash
#!/bin/sh
# Update script for users.

cdir=$(pwd)
curl -sLO https://github.com/venj/myscripts/zipball/master 
unzip -q master
cd venj-myscripts-*
adir=$(basename $(pwd))
cp my /usr/local/bin/my
mkdir -p /usr/local/bin/myscripts
cp -rf myscripts /usr/local/bin/myscripts
cd $cdir
rm -rf $adir
rm master
```

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
* `my del [SOME_COMMAND]` # Delete a command you no longer use.
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

## Individual Scripts

If you don't want to put all the sluppy stuff on your machine, you may found some individual scripts that are useful to you. Check'em out [here](https://github.com/venj/myscripts/tree/master/myscripts). You may run it directly on the command line without "my" wrapper.

Here are the functions for all the scripts in this repo: 
```
bu                  # Very silly script to update brew softwares.
checksum            # Checksum files with *ALL* md5 and shaX hash.
commit              # Commit and push your git repo with only one line of command.
dm                  # Download manga from manhua.178.com.
ed2k                # Extract all ed2k links from a webpage.
epub                # Pack a folder containing ePub necessary data into a ePub file.
gem                 # Install rubygems without install docs.
gitsync             # Sync all my local git repos.
icns                # Make icns file for Mac App Store from a large image file.
inject              # Inject f-script into a running application
iphone              # Check iPhone 4S availablity in HK and China Mainland.
keyrepeat           # Turn on and off OSX Lion's key repeat feature.
lx                  # This script is a wrapper for Xunlei-lixian python script. 
octoup              # Update Octopress and push code to blog source code repo (and publish to github pages)
pac                 # Encode plain text pac into a base64 encoded file.
pack                # Pack git repo into a zip archive for sharing.
ramdisk             # Make ramdisk with specific size.
remux               # Remux MP4/H264 videos (mkv, avi, etc.) to m4v.
rename              # Unpack or/and rename zip archive and/or ebook to a user specified name.
repack              # Repack ePub files under a directory to add iTunes recognizable book cover.
sparkle             # Sparkle keygen and sign update
sync                # Sync and push myscripts to github.
sysapk              # Install apks in current directory to an Android phone as system apps.
test                # Test sctipt for "my" wrapper.
transcode           # Change encoding for text files. (Save you some typing.)
tweak               # System tweak commands for OS X lion.
unpack              # Unpack and rename archives downloaded from wowebooks. 
update              # Update script for users.
uza                 # A very sluppy code to deal with 0day archives.
xclean              # Clean up your Xcode cache and applications to speedup Xcode.
```

Above is the information you will see after you install the whole repo and fireup `my info`.

## Misc

Fork me if you really decide to use it for your own.
