---
layout: post
title: Creating a Launch Script with Haxe/Lime
date: 2023-2-22
tags: development haxe
---

During the development of the library `hxCodec`, I found that I needed to add a launch script to be used on Linux, because if the executable was simply run directly, several dynamically linked libraries would not be found. This is because Linux does not search the current directory for libraries by default. This is a problem because these library files are necessary for the video player code that `hxCodec` uses.

I eventually discovered that you can use Lime's template feature to do this for you. Including files with `template` is similar to including files with `assets`, but additional application context flags are replaced with the appropriate values. For example, the `::APP_FILE::` flag is replaced with the name of the executable file.

Here's the snippet I used to add a launch script to `hxCodec`:

**include.xml**
```xml
<extension>
    <template path="templates/Linux/Start.sh" rename="Start.sh" if="linux" />
</extension>
```

And here's the launch script. Note that 

**templates/Linux/Start.sh**
```bash
#!/bin/bash

# Start the game
env LD_LIBRARY_PATH=./lib/ ./::APP_FILE::
```

Note the use of `::APP_FILE::` in the launch script. The value will get replaced based on the target user's `project.xml` file, which may look like this:

**project.xml**
```xml
	<app main="Main" path="export" file="Sample" />
```

The resulting export will be this:

**export/linux/bin/Start.sh**
```bash
#!/bin/bash

# Start the game
env LD_LIBRARY_PATH=./lib/ ./Sample
```

This is useful in the case where you need to include launch arguments or environment variables for the application to work.
