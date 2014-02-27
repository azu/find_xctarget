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

## Use Case

* [travis-ci/travis](https://github.com/travis-ci/travis "travis-ci/travis")

Generate `.travis.yml`

``` sh
$ travis init objective-c --script "`~/path/to/find-xctarget`" --before-script "gem install xcpretty" --rvm 1.9.3
```

* Enable Travis CI
* Generator .travis.yml

``` yml
language: objective-c
script: xcodebuild -workspace ArsScale.xcworkspace -scheme 'ArsScale' -sdk iphonesimulator ONLY_ACTIVE_ARCH=YES clean build test | xcpretty -c
before_script: gem install xcpretty
rvm: 1.9.3
```