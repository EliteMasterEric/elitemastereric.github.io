---
layout: post
title: My Top VSCode Extensions
date: 2023-2-16
tags: development vscode
---

_My recommended suite of Visual Studio Code extensions to maximize productivity, as well as tips and tricks for how to best use them._

This list will exclude common/obvious extensions like [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools).

## Formatting and Static Analysis

These extensions provide utilities for code cleanup, style checking, and code quality checks.

- **[Format Files](https://marketplace.visualstudio.com/items?itemName=jbockle.jbockle-format-files) by jbockle**

This simple extension adds convenient utilities to automatically call the `Format Document` command on groups of files at once. The extension will open, format, save, and close each document in turn.

You can right click a folder to format all files in that folder, or use the command palette (Ctrl+Shift+P) to format the entire workspace, or just files matching a specific glob.

## Haxe

- **[Haxe](https://marketplace.visualstudio.com/items?itemName=nadako.vshaxe)**

Anyone who has written Haxe has this extension, and has used its syntax highlighting and 



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
