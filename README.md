# Feri

<img src="https://raw.githubusercontent.com/nightmode/feri/master/images/feri-the-ferret.png" width="420" height="453" align="right" alt="">

An easy to use build tool for web files.

Incrementally clean, build, and watch with little to no configuration required.

## Navigation

* [Features](#features)
* [Core Concepts](#core-concepts)
  * [One Source, One Destination](#one-source-one-destination)
  * [File Extension Based](#file-extension-based)
  * [Include Files](#include-files)
  * [Customizable](#customizable)
* [Install](#install)
* [Upgrade](#upgrade)
* [Command Line](#command-line)
* [Quickstart Guide](#quickstart-guide)
* [Advanced](#advanced)
  * [Custom Config File](docs/advanced/custom-config-file.md#feri---custom-config-file)
  * [Custom Build Task](docs/advanced/custom-build-task.md#feri---custom-build-task)
  * [Unique File Types](docs/advanced/unique-file-types.md#feri---unique-file-types)
  * [Feri Extension](docs/advanced/feri-extension.md#feri---feri-extension)
  * [Edge Cases](docs/advanced/edge-cases.md#feri---edge-cases)
  * [API](docs/advanced/api/index.md#feri---api)
* [Donate](#donate)

## Features

* Clean, Build, and Watch
* Command Line and API
* Concatenate
* GIF, JPG, PNG, SVG, and WEBP
* HTML, CSS, and JavaScript
* Linux, macOS, and Windows
* Markdown
* [Multilingual](docs/multilingual.md#feri---multilingual)

## Core Concepts

### One Source, One Destination

A single source directory which builds/compiles/minifies into a single destination directory.

**Clean**: Destination files that do not have a source equivalent are removed during cleaning.

**Build**: If a source file is missing a destination equivalent, build the file. If a source file is newer than a destination equivalent, build the file.

**Watch**: Run clean and build tasks in reaction to file system changes.

### File Extension Based

A single plan of action for each file type. CSS files are minified. JPG files are losslessly optimized. Markdown files are compiled, then minified, and so on. Each extension can have its own unique build process but all files with that extension are treated equally.

### Include Files
Any file prefixed with an underscore `_` is considered an include file. Include files do not get directly published from source to destination. Instead, include file contents are only published when a file that can leverage includes is published.

### Customizable

Although capable as is, Feri is designed to be extremely customizable. Using the API or a custom config file allows you to not only change options but even replace core functions.

## Install

Make sure you have [Node](https://nodejs.org/en/) version 12 or greater. Depending on your operating system, you may also need to install python or other tools used by dependencies that need to be compiled.

Install Feri globally as a command line tool, accessible from anywhere.

```
npm install -g feri
```

Install Feri locally in your project's [node_modules](https://nodejs.org/api/modules.html#modules_loading_from_node_modules_folders) folder for API use and/or command line use from within your project only.

```
npm install feri
```

Either process above may display warnings about optional dependencies. These warnings can be safely ignored as those dependencies were not needed for your particular OS.

## Upgrade

You can always upgrade to the latest version of Feri by re-running the global or local install commands.

If you are unsure if an upgrade is available, run the following for a global install.

```
feri --version
```

Or the following for a local install.

```
npx feri --version
```

The above commands will provide additional upgrade information if a newer version is available. Otherwise, just the currently installed version will be listed.

### Upgrade from Version 3

Two potentially critical things to be aware of.

* The dependency `livereload` has been replaced by a new extension server.
* Many dependencies have been removed.
    * If you still want to work with CoffeeScript, EJS, Jade, JSX, Less, Pug, Sass, and/or Stylus, you'll need to create your own custom build task.

Custom config files using the boolean `feri.config.option.livereload` should be changed to `feri.config.option.extensions`.

API use for anything `livereload` related should be changed to an `extension` or `extensions` equivalent depending on where you are in the plumbing.

Command line options like `--livereload` and `--nolivereload` have new equivalents like `--extensions` and `--noextensions`.

## Command Line

If installed globally, you can see what command line options are available with:

```
feri --help
```

Or locally with:

```
npx feri --help
```

More information is available in the [command line](docs/command-line.md#feri---command-line) documentation.

## Quickstart Guide

Assuming Feri is installed globally, the quickest way to start a new project is to use the init command.

```
feri --init
```

This will create a `source` and `dest` folder along with a custom config file. To make sure everything works, place some files in the `source` folder. Now run `feri` from the directory where you can see the source and destination folders. After a short time, your published files should appear in the `dest` folder.

You'll need to run `feri` everytime you want to clean and/or build new files. Once you are comfortable with that pattern, try running the following command instead.

```
feri --watch
```

Now Feri will stay active, watching your source folder for changes and automatically run the appropriate clean or build tasks depending on activity in the source folder. Neat!

## Advanced

Advanced topics for those that like to tinker.

### Custom Config File

Create a [custom config file](docs/advanced/custom-config-file.md#feri---custom-config-file) to set your preferred options, add custom build tasks, or leverage the API.

### Custom Build Task

Feri thinks you should be able to grab nearly any npm module and make a [custom build task](docs/advanced/custom-build-task.md#feri---custom-build-task) out of it without too much effort. Are `.snazzy` files the latest way to write CSS? No need to wait for a plugin. Use the latest tech, right away.

### Unique File Types

Feri comes with built-in support for [unique file types](docs/advanced/unique-file-types.md#feri---unique-file-types) such as `br`, `concat`, `gz`, and `jss`.


### Feri Extension

Reload a web browser tab when files change with the [Feri Extension](docs/advanced/feri-extension.md#feri---feri-extension) for Chrome, Edge, and Firefox.

### Edge Cases

Some [edge cases](docs/advanced/edge-cases.md#feri---edge-cases) you may want to be aware of.

### API

Leverage or even replace anything behind the scenes with [full access](docs/advanced/api/index.md#feri---api) to the [API](docs/advanced/api/index.md#feri---api).

## Donate

Buy me [Bubble Tea](https://ko-fi.com/kai_nightmode). Support my work and get the ability to send me private messages on Ko-fi. ^_^

## License

MIT © [Kai Nightmode](https://twitter.com/kai_nightmode)

The MIT license does NOT apply to the name `Feri` or any of the images in this repository. Those items are strictly copyrighted to Kai Nightmode.