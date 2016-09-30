# usqcd_install
Scripts for installing USQCD software

The philosophy of this script is to make it as easy as possible to compile [currently: my preferred] USQCD software and related software in a variety of environments.

The script is invoked quite simply: `usqcd.sh MACHINE LIBRARY ACTION`

```
MACHINE is one of the files in the machine directory, without the .sh
LIBRARY is one of the software packages specified in the STACK variable in the machine file.
ACTION  is one of
  report      Report information relevant to the LIBRARY.
  get         Go get the package.
  configure   Prepare to complile.
  make        Compile.
  install     Install.
  complete    get, configure, make, and install.
````

There are variables for many imaginable user options that default to values specified in `machine/default.sh`.
This makes it easy to alter the path to, compilation settings for, etc., just one of the libraries or them all at once.

### Table of Contents

- [`usqcd_install`](#usqcd_install)
- [Table of Contents](#table-of-contents)
- [Requirements](#requirements)
- [License](#license)


### Requirements

The requirements are very basic:
- `bash 4+`:  `usqcd.sh` takes substantial advantage of associative arrays, so the shebang therein must point to a `bash` version 4.0 or later.  The script will refuse to run unless this is satisfied.

The other requirements are due to defaults---in principle you can configure your settings so that they aren't needed.  I struggle to imagine when that would be a good idea.

- `git`:  The default for most libraries is to `git clone` the software locally.
- `curl`: Currently, the default method to get the hdf5 source code.
- `autotools`: `libtoolize`, `autoheader`, `aclocal`, `automake`, `autoconf`, `autoreconf`.
- `make`: For compiling!
- `cmake`: (soon!) for configuring QUDA.

### Machine files

A machine file is a file that lives in the `machine` directory of this repo.  It is where you specify what kind of software stack you want to compile, and what settings are needed.

Machine files are welcome!  I'm happy to accept pull requests, so as to build up successful scripts for as many machines as possible.  That makes this script more and more useful.

### Configurable Variables



### LICENSE

I would really appreciate it if you would cite

```
@misc{berkowitz.usqcd.installer,
  author = {Berkowitz, Evan},
  title = {\texttt{usqcd_installer.sh}},
  year = {2016},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/evanberkowitz/usqcd_install}},
  commit = {...}
}
```

or drop me an email / buy me a beer at a conference if these scripts made your life easier.  But, the license is GPLv3.0.

```
usqcd.sh
    Installer suite for USQCD and related packages.
    Copyright (C) 2016  Evan Berkowitz

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.
```