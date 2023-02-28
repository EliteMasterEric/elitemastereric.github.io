- Clean up formatting article
- How to solve GetThreadContext Failed
- https://www.youtube.com/playlist?list=PLJ690cxlZTgL4i3sjTPRQTyrJ5TTkYJ2_
- https://github.com/newren/git-filter-repo/blob/main/Documentation/converting-from-filter-branch.md#cheat-sheet-conversion-of-examples-from-the-filter-branch-manpage
- <iframe src="https://www.youtube.com/embed/dXBohfjc4WA" width="680" height="480" allowfullscreen></iframe>

- clip.exe for WSL

1. Static Extensions

Static Extensions are when a class, containing static functions, is referenced with the `using` keyword; those functions then become "part of" the type referenced in their first argument, passing the target object to the static function.

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
