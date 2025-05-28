# Pidgin Windev

This MSYS2/Cygwin tool creates a build environment for Pidgin on Windows,
automating the manual steps described in the [official
documentation](http://developer.pidgin.im/wiki/BuildingWinPidgin).

![Screenshot](pidgin-windev.png)

## License and copyright

Copyright (c) 2012-2016 Renato Silva.
Copyright (C) 2024-2025 Pidgin Developers
Licensed under the terms of the [3-clause BSD license](LICENSE).

# Usage

To use this script you need to have a posix like shell. Some examples are
[MSYS2](https://www.msys2.org/) and [Cygwin](https://www.cygwin.com/).

Creating a build environment is as simple as running the command with a
destination directory:

```sh
./pidgin-windev.sh <directory name>
```

> Note: This will take a considerable amount of time to run.

This will download the sources of everything into
`<directory name>/downloads`. It will extract evertying into
`<directory name>/win32-dev` and extract the current Pidgin release into
`<directory name>/pidgin-<version>`.

When it has completed you can then "activate" the build directory by running

```sh
eval $(./pidgin-windev.sh <directory name> --path)
```

This will update the `PATH` environment variable for you.

You can now move to the Pidgin directory and build with
`make -f Makefile.mingw`.

