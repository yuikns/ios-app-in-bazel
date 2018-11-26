A Simple iIO App Example
=============================

This is a simple example project based on bazel's official site, which could be found in:

+ [Introduction to Bazel: Build an iOS App](https://docs.bazel.build/versions/master/tutorial/ios-app.html)
+ [Apple Rules for Bazel: Examples](https://github.com/bazelbuild/rules_apple/tree/0.2.0)


## FAQ

### `Cocoa/Cocoa.h` File Not Found

A simple example:

```
$ bazel build //examples/macos/HelloToday:AppSources
INFO: Analysed target //examples/macos/HelloToday:AppSources (0 packages loaded).
INFO: Found 1 target...
ERROR: /private/var/tmp/_bazel_yu/e4a1cf296b970230f6c4672140e1bee3/execroot/com_argcv/bazel-out/examples/tutorial/examples/macos/HelloToday/BUILD:15:1: C++ compilation of rule '//examples/macos/HelloToday:AppSources' failed (Exit 1)
In file included from examples/macos/HelloToday/AppSources/ViewController.m:15:
./examples/macos/HelloToday/AppSources/ViewController.h:15:9: fatal error: 'Cocoa/Cocoa.h' file not found
#import <Cocoa/Cocoa.h>
        ^~~~~~~~~~~~~~~
1 error generated.
Target //examples/macos/HelloToday:AppSources failed to build
Use --verbose_failures to see the command lines of failed build steps.
INFO: Elapsed time: 0.302s, Critical Path: 0.13s
FAILED: Build did NOT complete successfully
```

A response could be found [here](https://github.com/bazelbuild/rules_apple/issues/116#issuecomment-338474815)

FIX:

```
$ bazel build --apple_platform_type=macos //examples/macos/HelloToday:AppSources
INFO: Analysed target //examples/macos/HelloToday:AppSources (0 packages loaded).
INFO: Found 1 target...
Target //examples/macos/HelloToday:AppSources up-to-date:
  bazel-out/darwin_x86_64-fastbuild/bin/examples/macos/HelloToday/libAppSources.a
INFO: Elapsed time: 0.183s, Critical Path: 0.01s
INFO: Build completed successfully, 1 total action
```

Actually, since it is not required, we can simple ignore it.




