---
layout: post
title: Formatting and Checkstyle in Haxe
date: 2023-2-14
tags:
- development
- vscode
- haxe
---

_A rundown on the various formatting and checkstyle options useful for maintaining Haxe code. This article was partially written with ChatGPT, with manual proofreading._

# Introduction

Haxe is a versatile programming language that can be used to create applications for a wide range of platforms. As with any programming language, it's important to write clean and well-formatted code to ensure that it is easy to read, maintain, and debug.

This is where formatting and checkstyle options come in. By using the right formatting and checkstyle options, you can automate the process of maintaining code quality, which can save you time and prevent errors down the line.

In this article, we will provide a comprehensive rundown of the various formatting and checkstyle options that are available for Haxe, along with tips on how to use them effectively.

Whether you are a seasoned Haxe developer or just starting out, this guide will help you improve your coding practices and write more efficient and maintainable code.

Note that this article assumes that the [Visual Studio Code](https://code.visualstudio.com/) IDE is being used.

# Formatting vs Static Analysis

**Code formatting** and **static analysis** are two distinct processes that are often used to maintain the quality of code in software development.

**Code formatting** refers to the process of applying a specific layout or structure to source code to make it more readable and consistent. Code formatting can be automated with the help of tools that follow a set of rules and guidelines to ensure that the code is easy to read and follow.

**Static analysis**, on the other hand, is a process of analyzing code without actually running it, to detect potential issues and bugs in the code. Static analysis tools check the code for various issues such as syntax errors, code smells, potential security vulnerabilities, and adherence to coding standards.

In summary, code formatting deals with the **appearance and layout of code**, whereas static analysis focuses on the **quality and correctness of the code itself**. Both processes are important for maintaining code quality, and by using them together, developers can ensure that their code is not only easy to read and maintain but also free of errors and potential issues.

# Formatting

Standardizing code formatting has numerous benefits, particularly when using version control systems such as Git. Consistent formatting leads to easier code reviews, improved merge conflicts, clearer history, and better collaboration. Additionally, code formatting standards help to reduce errors, improve readability, and ensure code consistency. These benefits ultimately lead to higher quality code with fewer bugs, a smoother development process, and more efficient teamwork.

Have you ever opened up a pull request, only to find it made hundreds of minor formatting changes that drastically increased the amount of time (and mental load) required to review it? Standardized formatting can help solve this.

## Formatting Haxe

To standardize the formatting in your Haxe project, follow these steps:

1. Ensure the [official Haxe extension](https://marketplace.visualstudio.com/items?itemName=nadako.vshaxe) is installed.
2. Create a file named `hxformat.json` in your Haxe project folder.
3. Start adding rules to the haxe-formatter config.

There are many automated formatting rules available to Haxe. The full list of rules is [rather long (you can look at it here)](https://github.com/HaxeCheckstyle/haxe-formatter/blob/master/resources/default-hxformat.json), but here is a good template to start with.

```
{
  "indentation": {
    "character": "  ",
    "tabWidth": 2
  },
  "lineEnds": {
    "leftCurly": "both",
    "rightCurly": "both",
    "objectLiteralCurly": {
      "leftCurly": "after"
    }
  },
  "sameLine": {
    "ifElse": "next",
    "doWhile": "next",
    "tryBody": "next",
    "tryCatch": "next"
  }
}
```

The above sample will perform the following whenever you format:

- Standardize whitespace to 2 spaces.
- Add newlines before and after brackets for function bodies.
- Automatically move the bodies of single-statement `ifElse` blocks to the next line.
  - Same for `doWhile`, `try` body, and `tryCatch` body.

You can also experiment with rules on [the haxe-formatter playground](https://haxecheckstyle.github.io/haxe-formatter-docs/#codesamples.CommonSamples.haxeflixel_style).

VSCode will format whenever you press `Alt+Shift+F`. If you wish to enable automatic formatting, add the following to your `.vscode/settings.json` file (this ensures that formatting is automatically applied before the file
is saved, and whenever you paste snippets):

```
{
  "[haxe]": {
    // Automatically keep Haxe files formatted.
    "editor.formatOnSave": true,
    "editor.formatOnPaste": true,
    "editor.defaultFormatter": "nadako.vshaxe"
  }
}
```

## Formatting JSON and XML

Visual Studio Code provides formatting via [the XML extension](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-xml) and I have personally found it to be sufficient.

Visual Studio Code also has formatting for JSON, however I have not found its default implementation to be sufficient, so I personally use Prettier instead:

1. Ensure the [Prettier extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) is installed.
2. Create a file named `.prettierrc.js` (don't forget the leading dot!).
3. Start adding rules to the Prettier config.

Here are my rules:

```
/**
 * Configuration for JSON file formatting.
 */
module.exports = {
  // Line width before Prettier tries to add new lines.
  printWidth: 80,

  // Indent with 2 spaces.
  tabs: false,
  useTabs: false,
  tabWidth: 2,

  // Use double quotes.
  singleQuote: false,
  quoteProps: "preserve",
  parser: "json",

  bracketSpacing: true, // Spacing between brackets in object literals.
  trailingComma: "none", // No trailing commas.
  semi: false, // No semicolons at ends of statements.
};
```

Note also Prettier's rules for [formatting multi-line objects](https://prettier.io/docs/en/rationale.html#multi-line-objects).
To summarize, if the first property of an object is on the same line as the curly brace, it will be reformatted to one line, but if the first property is on a different line, it wil be formatted to one property per line. This is useful for keeping short objects collapsed and larger objects expanded.

#
