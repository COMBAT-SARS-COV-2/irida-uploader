# IRIDA Uploader


##Features
* Command Line interface for Linux and Windows
* Single Directory Upload
* Miseq sequencing run parser

## Upcoming Features
* Automated uploads
* File upload checksum validation
* Post-processing tasks
* GUI
* Pause and resume uploads

# Getting Started

## Download / Install / Setup

### Download

The IRIDA MiSeq Uploader can be run on any operating system that supports Python.

You can download the source code on [GitHub]().

TODO: You can download pre-built packages for Windows from our [GitHub releases page](https://github.com/phac-nml/irida-miseq-uploader/releases/latest).

### Installation

#### Windows

Run an installer (links above) and follow along with the install wizard.

You will need to configure your uploader before running. See [Configuration](configuration.md) for details

#### Linux

Make sure Python 3 is installed

    $ python3 --version

If python3 is not installed, install with

    $ sudo apt-get install python3

Install pip:

    $ sudo apt-get install python3-pip

### virtualenv usage  

Install virtualenv and setuptools

    $ pip install virtualenv
    $ pip install setuptools

If you already have these packages installed, ensure they are up to date

    $ pip install virtualenv -U
    $ pip install setuptools -U

Download the source code

    $ git clone https://github.com/phac-nml/irida-miseq-uploader
    $ cd irida-miseq-uploader

Build a virtualenv and install the dependencies automatically with `make`:

    $ make
    
You will need to configure your uploader before running.

### Configuration

You will need to configure IRIDA and the uploader to upload files.

[How to configure](configuration.md)

If you do not create a configuration file, IRIDA uploader will create one for you with default values the first time it try's to upload.

You will need to edit this file with your IRIDA credentials, and the parser that matches your data.

#### Choose a Parser

The config file has a `parser` field that you can use to parse different directory structures

We currently support the following:

`directory` : [Generic Directory](parsers/directory.md)

`miseq` : [Miseq](parsers/miseq.md)

## Starting an upload

You can upload with the following commands

### Windows:

Open a Command Prompt terminal and use the `iridauploader` command to upload

`C:\Users\username> iridauploader \path\to\my\samples\`

### Linux:

Use the the `irida-uploader.sh` script included with the source code to upload.

`./irida-uploader.sh /path/to/the/sequencing/run/`


# Problems?

### Problems uploading?
Check the [Errors Page](errors.md) for help with common errors.

### Found a bug or have an idea for a feature?
Create an issue on our [GitHub](todo: link to github)

# Developers

Want to create a parser for a sequencer that we don't yet support or have an idea for an IRIDA related project?

[Requirements for new parsers](developers/parsers.md)

[Information on the IRIDA python API](developers/api.md)

[Object Model Reference](developers/objects.md)