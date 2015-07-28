# My Scripts
[中文](#我的脚本)

## Description

These are my daily scripts with a command wrapper to avoid naming conflict with system and 3rd-party commands. Only usable on a mac. Very sluppy, use at your own risk.

## Install/Upgrade

*Be sure to fork this repository before you install and edit following install script properly!!!*

You can use following install script to install and upgrade:

```bash
#!/bin/sh
# Update script for users.

cdir=$(pwd)
curl -sLO https://github.com/venj/myscripts/archive/master.zip
unzip -q master.zip
cd myscripts-master
adir=$(basename $(pwd))
cp my /usr/local/bin/my
cp -rf myscripts /usr/local/bin
cd $cdir
rm -rf $adir
rm master.zip
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
transcode           # Change encoding for text files. (Save you some typing.)
tweak               # System tweak commands for OS X lion.
unpack              # Unpack and rename archives downloaded from wowebooks. 
update              # Update script for users.
uza                 # A very sluppy code to deal with 0day archives.
xclean              # Clean up your Xcode cache and applications to speedup Xcode.
```

Above is the information you will see after you install the whole repo and fireup `my info`.

## Q&A

Q: Darn, the `my` stuff is f**king boring!!!<br/>
A: Well, you can use alias to your shell's rc file to get rid of the `my` stuff. e.g.:

```
alias lx="my lx"
alias mylx="my lx"
alias remux="my remux"
alias inject="my inject"
alias unpack="my unpack"
alias repack="my repack"
alias tweak="my tweak"
```

## Misc

Fork me if you really decide to use it for your own.

--------------------------------------

# 我的脚本

## 描述

这个源保存了我日常使用的一些脚本。我用一个封装脚本用于避免我自己的脚本和系统命令和第三方程序发生名字冲突。这些脚本绝大部分只对Mac有用，很多都很粗糙。如果你要使用，请自己承担风险。

## 安装、升级

*如果你打算使用本源的所有脚本，请Fork本git repo之后再开始使用。*

你可以使用如下脚本安装和升级脚本：

```bash
#!/bin/sh
# Update script for users.

cdir=$(pwd)
curl -sLO https://github.com/venj/myscripts/archive/master.zip
unzip -q master.zip
cd myscripts-master
adir=$(basename $(pwd))
cp my /usr/local/bin/my
cp -rf myscripts /usr/local/bin
cd $cdir
rm -rf $adir
rm master.zip
```

## 使用方法

这个源的核心是封装脚本`my`。这个脚本会搜索并执行`/usr/local/bin/myscripts`下的脚本。这个封装脚本的作用是避免自己的脚本和系统命令发生名字冲突。

这个源还包括了很多我自用的脚本，所以，如果你打算用这些脚本，请先fork，并修改之后再使用。

### 封装脚本`my`

* `my [SOME_COMMAND]` # 用来运行某个脚本。如果没有指定脚本，则显示帮助信息。
* `my edit [SOME_COMMAND]` # 编辑一个脚本。如果脚本不存在，则创建新脚本。如果没有指定脚本，则编辑`my`封装脚本。
* `my chmodx SOME_COMMAND` # 让某个脚本可执行。新创建的脚本请务必在使用前执行这个命令。
* `my info [SOME_COMMAND]` # 列出某个脚本的介绍信息；如果没有指定脚本，则显示所有脚本的介绍。
* `my cat [SOME_COMMAND]` # 打印脚本源码；如果没有制定脚本名，则打印`my`封装脚本的源码
* `my del [SOME_COMMAND]` # 删除一个不再使用的脚本
* `my help` # 显示帮助信息

## 增加你自己的脚本

1. `my edit new_script` (或者 `my e new_script`) 将在`/usr/local/bin/myscripts`中创建一个名为`new_script`的新脚本
2. 别忘了使用`#!`行作为脚本的第一行
3. 你可以在第二行使用encoding行，如果你的脚本中包含非ASCII字符
4. 接着，请使用一个注释行来说明脚本的作用
5. 然后你就可以像编写普通脚本那样写脚本了
6. 写完脚本之后，不要忘记使用`my chmodx new_script`或`my x new_script`将脚本标记为可执行的
7. 然后，你就能运行`my new_script`了

以下是一个示例脚本的模版：

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

## 单独的脚本

如果你不想照单全收本源中的所有脚本，那么你也可以单独使用这个源里的任何脚本。看[这里](https://github.com/venj/myscripts/tree/master/myscripts)。你可以下载某个脚本，然后直接执行它。

以下是本源中的所有可用脚本：
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
transcode           # Change encoding for text files. (Save you some typing.)
tweak               # System tweak commands for OS X lion.
unpack              # Unpack and rename archives downloaded from wowebooks. 
update              # Update script for users.
uza                 # A very sluppy code to deal with 0day archives.
xclean              # Clean up your Xcode cache and applications to speedup Xcode.
```
如果你完全安装了本源，你也可以使用`my info`命令看到以上信息。

## 问答

问：我去，为什么要我在每个命令前打`my`啊！<br/>
答：你可以在shell的rc脚本里创建命令的别名（alias），示例如下：

```
alias lx="my lx"
alias mylx="my lx"
alias remux="my remux"
alias inject="my inject"
alias unpack="my unpack"
alias repack="my repack"
alias tweak="my tweak"
```

## 其他
完整安装本源之前，建议你先Fork。
