# CueConcurrency Installation

There are three ways to integrate CueConcurrency into your project:
* Use [Cocoapods](http://cocoapods.org/)
* Import CueConcurrency.xcodeproj
* Pick and choose the files you need.

### Cocoapods
If you're already using Cocoapods then this will be very easy, just add `pod "CueConcurrency"` to your Podfile
and type 'pod install':

If you haven't used Cocoapods before, read the installation instructions [here](http://cocoapods.org/#install).

## Get the code

### Git Clone
If you don't care about keeping up to date, just `git clone https://github.com/Cue/CueConcurrency.git`.

### Git Subtree
If you're using git 1.8, you can use `git subtree` for easy inclusion of the CueConcurrency codebase:

~~~~~~~~~~~~.bash
git subtree add --prefix=path/within/repo/for/CueConcurrency --squash \
    git@github.com:Cue/CueConcurrency.git master
~~~~~~~~~~~~

Later, you can upgrade to the latest revision of CueConcurrency with:

~~~~~~~~~~~~.bash
git subtree pull --prefix=path/within/repo/for/CueConcurrency --squash \
    git@github.com:Cue/CueConcurrency.git master
~~~~~~~~~~~~

If you make changes and want to submit a pull request, fork CueConcurrency, and then:

~~~~~~~~~~~~.bash
git subtree pull --prefix=path/within/repo/for/CueConcurrency --squash \
    git@github.com:YourGitUsername/CueConcurrency.git master
~~~~~~~~~~~~

and then submit your pull request from your forked repo.

## Add to your project

Open Finder, navigate to `hookshot.xcodeproj`, and drag it in to your project:

![Drag CueConcurrency in to your project](https://raw.github.com/Cue/CueConcurrency/master/Documentation/Images/DragToProject.png)

should result in something like this:

![After adding CueConcurrency](https://raw.github.com/Cue/CueConcurrency/master/Documentation/Images/ShowInProject.png)

Select the subproject, then choose `Build Settings`.  Search for `c++`

* Ensure `C++ Language Dialect` is `GNU++11` or `C++11`

* Ensure `C++ Standard Library` is `libc++`

Search for `header`

* Add relative or full path to `CueConcurrency/Classes` to `Header Search Paths`

![Header search paths](https://raw.github.com/Cue/hookshot/master/Documentation/Images/HeaderSearchPaths.png)

Select your root project.  For each the target you want to use CueConcurrency with

* Select `Build Phases`

* Open the `Link Binary With Libraries` panel

![Before linking libraries](https://raw.github.com/Cue/hookshot/master/Documentation/Images/BeforeLinkLibraries.png)

* Add `libCueConcurrency.a`

* Add `libc++.dylib`

![Link libraries](https://raw.github.com/Cue/hookshot/master/Documentation/Images/LinkLibraries.png)

You're now ready to start using CueConcurrency!