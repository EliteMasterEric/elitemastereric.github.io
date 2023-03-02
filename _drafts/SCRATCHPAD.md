- Clean up formatting article
- How to solve GetThreadContext Failed
- https://www.gdcvault.com/play/1023291/Designing-AI-for-Competitive


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
