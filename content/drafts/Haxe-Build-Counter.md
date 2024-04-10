---
layout: post
title: Haxe build counter
date: 2023-2-14
tags:
- development
- vscode
- haxe
---

```haxe
@:build(BuildTracker.build())
class Main {
  public static function main() {}
}
```
```haxe
import haxe.macro.Expr;

class BuildTracker {
  @:persistent static var buildCounter:Int = 0;

  public static build():Array<Field> {
    #if !display // ignore
    buildCounter += 1;
    trace('Performing build #$buildCounter');
    #end

    // We aren't adding or removing fields from the class.
    return null;
  }
}
```