# find-xctarget

Generator test command for Xcode project.

## Example

``` sh
$ ls
ArsScale             ArsScale.xcodeproj   ArsScale.xcworkspace ArsScaleTests        Podfile              Podfile.lock         Pods                 build                readme.md
```

`find-xctarget` ouput :

```sh
$ find-xctarget
xcodebuild -workspace ArsScale.xcworkspace -scheme 'ArsScale' -sdk iphonesimulator ONLY_ACTIVE_ARCH=YES clean build test | xcpretty -c
```
