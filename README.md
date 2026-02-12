portal
=

Preparing a build environment
-

You will need a few things to get started first.

Download and install the latest version of Google's Go programming language for your operating system from here: [All releases - The Go Programming Language](https://go.dev/dl)

Download the latest version of Google's Repo tool from here: [repo](https://storage.googleapis.com/git-repo-downloads/repo)

Make it executable, then place it somewhere in your `$PATH`. Doing this on various platforms is outside the scope of these instructions for now.

Verify your version of Repo works:
```
$ repo version
```
For guaranteed compatibility, make sure you're running repo version v2.61.1 or newer.

Next, make a directory to store the portal and navigate to it. For example:
```
$ mkdir -p $HOME/projects/portal
$ cd $HOME/projects/portal
```

Initialize the portal manifest:
```
$ repo init -u https://github.com/FrameworkOSS/portal -b dev
```
If you plan to make contributions upstream or to your own forks, a dev manifest is conveniently provided to checkout over SSH:
```
$ repo init -u https://github.com/FrameworkOSS/portal -b dev -m dev.xml
```
Some repositories may grow in size over time, as is the nature of development. If you don't plan to make any contributions, you can either specify `--partial-clone` to save on bandwidth or you can force the commit depth to X commits with `--depth=X`. You may additionally want to specify `--git-lfs` if you plan on using any features or apps that utilize Git LFS for their source repos.

Sync the portal tree:
```
$ repo sync
```
The default parallel job count is 4, but can be adjusted with `-jX` to slow down or speed up the connection depending on what you need.

Getting started
-

Source the build environment:
```
$ . envsetup
```

(TODO: Finish builder before providing the help text!)
