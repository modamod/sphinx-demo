# Getting started

## What is Sphinx

Sphinx is a tool that makes writing and publishing documentation a lot more easier.
With the way it works, Sphinx helps publishing documentation to different destinations and formats.
It can publish pdf version of your documentation to make it easy to share with customers or thrid party
without having to worry about access, at the same time it keeps your conflurnce pages up todate.

## How to use Sphinx

Sphinx is easy to setup, it requires couple of packages to install and couple of commands to run to be able to start building your documentation.
Sphinx uses a `conf.py` file to configure itself and to know what steps to perform when building your documentaion for the the specified destination.
For example by setting `confluence_server_url` you are telling it where to look for your confluence server and where to send requests to update it.

### Wrting doc files

To be able to use Sphinx to generate your documentation, you need to structure your documentation, the quick start cli will walk you though the basic folder structure.

```bash
sphinx-quickstart

```

the quickstart wizrd should create a folder structure similar to the following

```bash
$ tree ./

./
├── Makefile
├── build
├── make.bat
└── source
    ├── _static
    ├── _templates
    ├── conf.py
    └── index.rst

4 directories, 4 files
```

the enty point to the documentation is the top level `index.rst` file, it is called the master document and servers as a welcome page.
RST files are reStructuredText files it is a special markdown language to help build complex structure documentation. Thanks to `m2r2` extension we won't be using it much through out this demo. The main source will be standard MD files. For more information about reStructuredText check [Sphinx documentation](https://www.sphinx-doc.org/en/master/glossary.html#term-reStructuredText)

### Sphinx is extendable

Sphinx comes baked in with lots of extension, for the sake of this demo we will be using the following extensions

*
