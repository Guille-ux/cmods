# cmods

[![PyPI - Version](https://img.shields.io/pypi/v/cmods.svg)](https://pypi.org/project/cmods)
[![PyPI - Python Version](https://img.shields.io/pypi/pyversions/cmods.svg)](https://pypi.org/project/cmods)

-----

## Table of Contents

- [Installation](#installation)
- [User Docs](#user-documentation)
    - [Project Initialization](#project-initialization)
    - [Adding and Removing Repositories](#repositories)
    - [Adding and Removing Modules](#modules)
    - [Adding flags](#adding-flags)
    - [Writing the Makefile](#the-makefile)
    - [Building de Project](#building)
- [Dev Docs](#developer-documentation)
    - [About Creating Repositories](#about-creating-repositories)
    - [About Creating Modules](#about-creating-modules)
        - [About Module Structure](#about-module-structure)
        - [About Makefile](#about-makefile)
        - [About names](#names)
- [License](#license)

## Installation

```console
pip install cmods
```

## User-Documentation

### Project-Initialization

to initialize a project with `cmods`, run:

```bash
cmods init
```

### Repositories

#### Adding Repositories
to add a repository, run:
```bash
cmods add-repo <name> <url>
```
where `<name>` is the alias you want to assign to that repository and `<url>`
is the url to the repository.

#### Removing Repositories
to remove a repository, run:
```bash
cmods del-repo <name>
```

where `<repo>` is the alias you assigned to the repository.

### Modules

#### Adding Modules

to add a module, run:
```bash
cmods add-mod <name> <repo>
```

where `<name>` is the name of the module and `<repo>` is the repository to which the module belongs.

#### Removing Modules

to remove a module, run:
```bash
cmods del-mod <name>
```

where `<name>` is the name of the module.

### The-Makefile

writing the makefile you must to include `cmods/cmods.mk` which is the just-in-time generated Makefile.

the rule for building de modules is `cmods_all` so a Makefile would be this
```Makefile
#
# Makefile
#

include cmods/cmods.mk

BUILD_DIR = src/build

all: cmods_all
    ld -o project $(BUILD_DIR)/*.o

```

***Note**:  if you want to set other things like the compiler, you can export that before including `cmods/cmods.mk`*

## Developer-Documentation

### 

## License

`cmods` is distributed under the terms of the [MIT](https://spdx.org/licenses/MIT.html) license.
