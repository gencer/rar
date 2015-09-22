# RAR

RAR is a Ruby wrapper for the command-line application `rar`, also known as
WinRAR for Windows. A free evaluation copy can be obtained from [RarLab](http://rarlab.com).

[![Build Status](https://travis-ci.org/mkroman/rar.svg)](https://travis-ci.org/mkroman/rar)
[![Dependency Status](https://gemnasium.com/mkroman/rar.svg)](https://gemnasium.com/mkroman/rar)

## Installation

WinRAR must be installed for this gem to work.

### Installing WinRAR for Mac

* [Download the installer](http://www.techspot.com/downloads/5169-winrar-for-mac.html) files and extract.
* Copy the file titled 'rar' into a folder that's in your `$PATH` such as `/usr/local/bin`. If you're not sure what folders are in your path, run `echo $PATH`.
* Open a new terminal window and test installation by running `rar`. If you see information about WinRAR, it installed correctly.


### Install the gem

`gem install rar`

And you're all set. Extra dependencies will automatically be installed.

## Usage

### Creating an archive

Creating an archive and adding arbitrary files to it is simple!

``` ruby
require 'rar'

archive = RAR::Archive.new 'archive.rar'

archive.add_file 'some-file.txt'
archive.add_file 'some-other-file.jpg'

archive.create!
```

### Adding command-line options

RAR provides a mapping of verbosely named options for ease of use.

``` ruby
archive = RAR::Archive.new 'archive.rar', volume_size: 15_000_000

archive.add_file 'some-file.txt'
archive.add_file 'some-large-file.bin'

archive.create!
```

This example splits the archive into multiple volumes with a size of 15MB.

To see more options, take a look at the documentation.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## History

__v0.1__

+ Initial release.
