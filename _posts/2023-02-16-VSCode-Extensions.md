---
layout: post
title: My Top VSCode Extensions (Updated Feb. 16, 2023)
date: 2023-2-16
tags: development vscode
---

_My recommended suite of Visual Studio Code extensions to maximize productivity, as well as tips and tricks for how to best use them. Regularly updated to add new entries and remove old ones._

This list will exclude common/obvious extensions like [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools).

## Formatting and Static Analysis

These extensions provide utilities for code cleanup, style checking, and code quality checks.

- **[Format Files](https://marketplace.visualstudio.com/items?itemName=jbockle.jbockle-format-files) by jbockle**

This simple extension adds convenient utilities to automatically call the `Format Document` command on groups of files at once. The extension will open, format, save, and close each document in turn.

You can right click a folder to format all files in that folder, or use the command palette (Ctrl+Shift+P) to format the entire workspace, or just files matching a specific glob.

- **[Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) by esbenp**'

This extension provides a powerful code formatter for many languages, including JavaScript and JSON. It is highly configurable, and can be used to format code on save, or on paste.

## Haxe

- **[Haxe](https://marketplace.visualstudio.com/items?itemName=nadako.vshaxe)**

This is the recommended extension for Haxe, and anyone who has written Haxe has used its syntax highlighting, problem reporting, and code completion features. However, you might not be aware that it has a wide variety of powerful features, such as:

- Full debugging support with breakpoints (see [my Haxe Debugger guide](/Haxe-VSCode-Debugger/)).
- Refactoring (Right Click -> Refactor)
- Formatting with hxformat (see [my Haxe formatting guide](/Haxe-Formatting/))

- **[Lime](https://marketplace.visualstudio.com/items?itemName=openfl.lime-vscode-extension)**

The Lime extension provides several useful features for those developing with Lime, OpenFL, or HaxeFlixel:

- Populate dependency tree automatically based on libraries listed in `project.xml`
- Launch configurations for use with the debugger
- Additional code completion

- **[Haxe Checkstyle](https://marketplace.visualstudio.com/items?itemName=vshaxe.haxe-checkstyle)**

This extension provides a wide variety of static analysis tools for Haxe code. It can be configured to run on save, or on demand. It also provides fixes for many of the issues it reports. For a more in-depth guide on Checkstyle, see [my Haxe formatting guide](/Haxe-Formatting/).

- **[Haxe blocks](https://marketplace.visualstudio.com/items?itemName=jeremyfa.haxe-blocks)**

This simple extension for Haxe annotates the closing brace of blocks with a comment containing the name of the block. This is useful for quickly identifying the end of a function or class, especially within long files.

## Shaders/GLSL

- **[GLSL Language](https://marketplace.visualstudio.com/items?itemName=slevesque.shader) by slevesque**

This extension provides syntax highlighting and code completion for GLSL shaders. It also provides a few useful commands for compiling and running shaders.

- **[Shader Toy](https://marketplace.visualstudio.com/items?itemName=jakearl.shader-toy-web) by jakearl**

This extension provides a live web preview of GLSL shaders, matching the syntax of ShaderToy. It can be configured to automatically reload the preview when the shader is saved.

## AI Assistance

- **[GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)**

GitHub Copilot provides AI-generated code completion built directly into the VSCode editor view. Copilot will automatically generate suggestions based either on existing code, or comments you have written. When Copilot has a suggestion, it will display as grey text after your cursor, and you can press `Tab` to fill in the suggestion or `Esc` to dismiss it.

Copilot is backed by a paid service. A free trial is available.

*PRO TIP*: Copilot works best when you heavily document your code, or when you are doing something repetitive. Copilot needs to be able to intuit what your next action will be. If you maintain a consistent code (see [Formatting and Static Analysis](#formatting-and-static-analysis)), Copilot can often generate the bodies for entire functions given only a Javadoc-style code comment.

- **[GitHub Copilot Labs](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-labs)**

GitHub Copilot Labs is a companion extension for GitHub Copilot, providing experimental features such as explaining chunks of code, language-to-language translation, test generation, and more. These features are located in a new tab of the sidebar.

Copilot Labs requires a GitHub Copilot subscription.

- **[ChatGPT](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-labs) by Ali Gençay**

This simple extension provides access to OpenAI's state-of-the-art chat bot via a tab in the sidebar. Support for other services such as Google's LaMDA are expected to come in the future.

The extension can be buggy (especially during periods of high load), and ChatGPT is not specifically built for code, but it is very powerful when it comes to explaining or describing chunks of code and especially with explaining algorithms.

ChatGPT requires an OpenAI account (which is free), and supports OpenAI Plus accounts which get priority during periods of high demand.

## Other

- **[CodeSnap](https://marketplace.visualstudio.com/items?itemName=adpyke.codesnap) by adpyke**

This extension provides a simple way to take screenshots of code. It can be used to create images for use in documentation, or to share code snippets.

- **[vscode-icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons) by vscode-icons-team**

This extension is the largest icon theme for Visual Studio Code. It provides icons for many file types, and can be used to quickly identify files in the explorer view.

You can find more extensions on the [Visual Studio Code Marketplace](https://marketplace.visualstudio.com/search?term=tag%253Aicon-theme&target=VSCode).