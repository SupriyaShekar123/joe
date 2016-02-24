![](http://i.imgur.com/y8g506n.png?1)

# joe

A `.gitignore` magician in your command line. Joe generates `.gitignore` files from the command line for you.

![](http://i.imgur.com/ghmJLUP.gif)

## Features

- Written in uncomplicated Python
- Easy to [install](https://github.com/karan/joe#installation)
- Stupidly [easy to use](https://github.com/karan/joe#usage)
- Supports all Github-supported [`.gitignore` files](https://github.com/karan/joe#list-all-available-files)
- Works on Mac, Linux and Windows
- Supports other version control systems (`.hgignore`)

## Installation

### Option 1: Homebrew

```bash
$ brew update
$ brew tap karan/karan
$ brew install gitignore
```

### Option 2: [Pip](https://pypi.python.org/pypi/joe)

```bash
$ pip install joe
```

### Option 3: From source

```bash
$ git clone --recursive git@github.com:karan/joe.git
$ cd joe/
$ python setup.py install
```

## Usage

After install, make sure to run `joe update`. This will download all `.gitignore` files in `~/joe-data/` folder.

### Basic usage

```bash
$ joe java    # outputs .gitignore file for java to stdout
```

To update your `.gitignore` files at any time, simply run:

```bash
$ joe update
```

### Overwrite existing `.gitignore` file

```bash
$ joe java > .gitignore    # saves a new .gitignore file for java
```

### Append to existing `.gitignore` file

```bash
$ joe java >> .gitignore    # appends to an existing .gitignore file
```

### Multiple languages

```bash
$ joe java node osx > .gitignore    # saves a new .gitignore file for multiple languages
```

### Create and append to a global .gitignore file

You can also use joe to append to a global .gitignore. These can be helpful when you want to ignore files generated by an IDE, OS, or otherwise.

```bash
$ git config --global core.excludesfile ~/.gitignore # Optional if you have not yet created a global .gitignore
$ joe OSX SublimeText >> ~/.gitignore
```

### List all available files

```bash
$ joe ls    # OR `joe list`
```

Output:

> actionscript, ada, agda, android, anjuta, appceleratortitanium, archives, archlinuxpackages, autotools, bricxcc, c, c++, cakephp, cfwheels, chefcookbook, clojure, cloud9, cmake, codeigniter, codekit, commonlisp, composer, concrete5, coq, craftcms, cvs, dart, darteditor, delphi, dm, dreamweaver, drupal, eagle, eclipse, eiffelstudio, elisp, elixir, emacs, ensime, episerver, erlang, espresso, expressionengine, extjs, fancy, finale, flexbuilder, forcedotcom, fortran, fuelphp, gcov, gitbook, go, gradle, grails, gwt, haskell, idris, igorpro, ipythonnotebook, java, jboss, jdeveloper, jekyll, jetbrains, joomla, jython, kate, kdevelop4, kohana, labview, laravel, lazarus, leiningen, lemonstand, libreoffice, lilypond, linux, lithium, lua, lyx, magento, matlab, maven, mercurial, mercury, metaprogrammingsystem, meteor, microsoftoffice, modelsim, momentics, monodevelop, nanoc, netbeans, nim, ninja, node, notepadpp, objective-c, ocaml, opa, opencart, oracleforms, osx, packer, perl, phalcon, playframework, plone, prestashop, processing, python, qooxdoo, qt, r, rails, redcar, redis, rhodesrhomobile, ros, ruby, rust, sass, sbt, scala, scons, scrivener, sdcc, seamgen, sketchup, slickedit, stella, sublimetext, sugarcrm, svn, swift, symfony, symphonycms, tags, tex, textmate, textpattern, tortoisegit, turbogears2, typo3, umbraco, unity, vagrant, vim, virtualenv, visualstudio, vvvv, waf, webmethods, windows, wordpress, xcode, xilinxise, xojo, yeoman, yii, zendframework, zephir

### BONUS ROUND: Alternate version control software

Joe isn't **just** a generator for `.gitignore` files. You can use it and its output wherever a SCM is used.

```bash
$ joe java > .hgignore
```

## Contributing

#### Bug Reports & Feature Requests

Please use the [issue tracker](https://github.com/karan/joe/issues) to report any bugs or file feature requests.

#### Developing

PRs are welcome. To begin developing, do this:

```bash
# make virtual env
$ git clone --recursive git@github.com:karan/joe.git
$ cd joe/
$ python joe/joe.py java
```

#### `tool.sh`

This is a handly script that automates a lot of developing steps.


```bash
USAGE:
  $ tool.sh [-h|--help] COMMAND

EXAMPLES:
  $ tool.sh readme    Generate README.rst from README.md
  $ tool.sh test      Upload release to testpypi
  $ tool.sh prod      Upload release to prod pypi
```

Make sure you have a file `.pypirc` in `~/` in the following format:

    [distutils]
    index-servers =
        pypi
        pypitest

    [pypi]
    repository: https://pypi.python.org/pypi
    username: <<>>
    password: <<>>

    [pypitest]
    repository: https://testpypi.python.org/pypi
    username: <<>>
    password: <<>>
