---
layout: post
title: Using Static Extensions in Haxe
date: 2022-06-11 00:00 +0000
tags:
- vscode
- haxe
- development
---

Haxe, as a cross-compiled language, has many tools which facilitate modifying how code is generated. This leads to many convenient features which improve readability of code which, in other languages, would be difficult to understand or write. Static extensions are one of these features.

Static extensions are when a class, containing static functions, is referenced with the `using` keyword. Those static functions then become "part of" the type referenced in their first argument, passing the target object to the static function.

Here is an example:

```haxe
// The actual Haxe implementation of StringTools is more complicated
// since it uses compile defines to use more efficient functions on specific platforms, but you get the general idea.
class StringTools {
    public static inline function contains(s:String, value:String):Bool {
        return s.indexOf(value) != -1;
    }
}

// You could do this...
var containsHello:Bool = StringTools.contains(myString, "Hello");

// ...or you could use StringTools as a static extension!
// Include this at the beginning, near your imports.
using StringTools;

// Then 
var containsHello:Bool = myString.contains("Hello");
// This gets replaced at compile time with:
var containsHello:Bool = StringTools.contains(myString, "Hello");
```

This is a very powerful tool, since not only is it more convenient and readable in many cases, 
