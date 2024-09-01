# Random Quote Android and iOS App Bazel Workspace
Monorepo of a Random Quote for Android and iOS App

## Purpose

This project aims to demonstrate the viability of using Bazel as a build management tool. While Bazel is an excellent choice for managing builds, it is particularly recommended for larger teams that frequently reuse modules and require collaborative workflows. 

The development of this project was guided by a YouTube playlist, which can be found [here](https://www.youtube.com/playlist?list=PL23Revp-82LK5Xvy_iQYScLZ6zIyBGZmX).

## Commands

### iOS

#### Generating XCode Project to develop

```
bazel run //ios-random-quote:xcodeproj
```

#### Running App

```
bazel build //ios-random-quote:iosapp
bazel run //ios-random-quote:iosapp
```

#### Testing App

```
bazel build //ios-random-quote:iostests
bazel test //ios-random-quote:iosapp
```