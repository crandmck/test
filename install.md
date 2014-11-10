# Installing Node.js, Strongloop, and their dependencies

On Windows Node.js requires a number of dependencies to be installed for a fully
functional development environment. These dependencies are not typically found
on Windows, and will most likely require installation. Here's how.


# Python

Python 2.7 (not 3.x, not 2.6.x or before) is required by npm to install packages
with compiled addons (like strong-agent, or websocket support).

Download python 2.7.x from http://python.org:

1. Go to https://www.python.org/downloads/windows/
2. Download latest stable 2.7.x Windows MSI Installer, either x86 or x86-64, as appropriate
3. Run installer, and make sure to add to Path:
  - Accept default "Install for all users"
  - Accept default "c:\Python27" for python files
  - Enable non-default "Add python.exe to Path"

FIXME how to determine 32/64 arch on Windows? in case they don't know :-(


# Git

Git is required by npm to download packages from github. Such packages are
rare, but exist, and installing git will allow them to be installed.

1. Go to http://git-scm.com/download,
2. Download for Windows, currently this is version 1.9.4
3. Run installer
  - Accept default install location
  - Accept or modify Components
  - Accept start menu folder
  - Modify "Adjusting your PATH environment" to "Use Git from Windows Command Prompt"
  - Accept default "Configuring the line ending conversions"


# Visual Studio

Visual Studio 2012 or later is required by npm to install packages with
compiled addons (like strong-agent, or websocket support). gcc, mingw, cygwin, and
other ports of non-Microsoft compilers to Windows are not supported by Node.js.

Note that Visual Studio Express is free, and more than adequate to support Node.js.

For Windows 7 and 8, use Microsoft Visual Studio C++ 2013 for Windows Desktop (Express):

1. Go to: http://www.microsoft.com/en-ca/download/details.aspx?id=43733
2. Select "Download", select "wdexpress_full.exe", and next

Note: if download doesn't start, select the "click here" link, then on the next
download page, select the "click here" link beside "wdexpress_full.exe".

3. Run installer:
  - Accept the default location

Note: this can take a long time, as in go-for-lunch time, not just coffee.


# Node.js

1. Go to http://nodejs.org/download/
2. Download the latest "Windows Installer (.msi)", 32 or 64-bit, as
   appropriate
3. Run it, there are no options


# StrongLoop

Note: After installing the above tools, re-open your command prompts, or
better, restart your machine to make sure configuration has taken effect.

1. Open a command shell by clicking "Start", and typing "cmd" and ENTER into the
   "Search programs and files" box

2. Install slc:
  - `npm install -g strongloop`

Note: warnings related to the installation of node-syslog can be ignored, they are
expected on Windows.

3. Run `slc -v`: you should see a listing of the strongloop components and their
   versions.

Congratulations, you now have strongloop and its dependencies installed, what next?

How about:

- FIXME after strongloop install, what next? Jimmy? Chanda?


# Trouble-shooting

If you encounter any difficulties installing strongloop, do the following and
report the result to support@strongloop.com. If it was an `npm install` that
failed, please attach the `npm-debug.log` file left by npm.

1. Restart Windows, to ensure configuration has taken effect.

2. Verify dependencies are installed:
  - `python --version`: should be 2.7.x
  - `node --version`: should be v0.10.x or v0.12.x (once it is released)
  - `npm --version`: should be 1.x or 2.x (once node v0.12 is released)

FIXME any way to determine what vs++ is installed?
FIXME is there any way to determine what python and msbuild node-gyp has found?

3. Ensure a simple npm package can be installed:

- `npm install -g semver`
- `semver --help`: should print usage message

4. Ensure a simple node compiled addon can be installed:

- `npm install -g buffertools`: should compile and install without errors.


## Tips and tricks

1. If you have multiple versions of python installed, you can select which
on is used by npm for building compiled addons:

  - `npm config set python c:/Python2.7/python`

2. If you have multiple versions of Microsoft Visual Studio installed, you can
select which one is used by npm for building compiled addons:

- `set GYP_MSVS_VERSION=2012`, or
- Append `npm --msvs_version=2012` or `--msvs_version=2013` (as appropriate) to
  the end of npm install commands, for
  example: `npm install -g strongloop --msvs_version=2012`

FIXME above does nothing for me, when I tried 2013 even though I only have 2012
installed, is that expected?



