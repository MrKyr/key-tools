## key-tools: Musical key analysis tools

(C) Copyright 2013 Mark Hills <mark@xwax.org>

Includes source code from KeyFinder which is (C) Copyright 2011-2013
Ibrahim Sha'ath and used under the GPLv3 license.

See the COPYING file for licensing terms.

This software is distributed from the following site:

  - http://www.pogo.org.uk/~mark/key-tools/

The build is controlled via Makefile variables. In general
you should be able to build using:

```bash
$ make
$ make install
```

To change the target prefix, for example:

```bash
$ make install PREFIX=/opt/key-tools
```

The Makefile picks up additional variables from a .config file
in the source directory. You will prefer to use this if you want
to control build flags for testing and debugging.

---

### Fixes

* Fixed _id3v2_: invalid option `-R`, replaced with `-l`

---

### Examples

_Mark has written a great key scanner:_

```
key-tag (C) Copyright 2013 Mark Hills <mark@xwax.org>

Usage: key-tag [options] <file>
Tag an audio file with musical key

  -f   Overwrite an existing key in the file tags
  -t   Output the traditional key instead of position on circle of fifths
  -n   Display key only, don't tag
  -h   Display this help message and exit
```

The key-tag script in key-tools works on one file at a time.

To batch tag in the current directory do this

```bash
  $ find ./ -type f -print0 | xargs -0 -n1 key-tag
```

If you want to scan annother directory replace ./ with the folder you want to scan.

If you have a multicore machine try this, it will run 4 instances in parallel:

```bash
  $ find ./ -type f -print0 | xargs -0 -n1 -P4 key-tag
```
