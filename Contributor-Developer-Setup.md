<h1 align="center">
	<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/nerd-fonts-logo.svg?sanitize=true" alt="Nerd Fonts" />
</h1>

0. [Prerequisites](#prerequisites)
    1. [Required](#required)
    2. [Highly Recommended](#highly-recommended)
0. [Base Nerd Fonts Development](#base-nerd-fonts-development)
    1. [OSX](#osx)
    2. [Linux](#linux)
    3. [Windows 7](#windows-7)
    4. [Windows 10](#windows-10)
0. [Hack font specific](#hack-font-specific-development)
0. [Sanity Tests](#sanity-tests)
0. [Troubleshooting](#troubleshooting)
0. [Resources](#resources)

---

* The basics of what you need to get up and running :)

# Prerequisites

## Required

* Git
* FontForge
* FontForge python bindings
* Python 2 and/or Python 3

## Highly Recommended

* ShellCheck
* Pyflakes (PEP8 compliance)
* [Pandoc][Pandoc-installing]

# Base Nerd Fonts Development

* What you need to contribute to the _core_ of Nerd Fonts

## OSX

todo

## Linux

* Download and install Python if not already installed: http://docs.python-guide.org/en/latest/starting/install/linux/
  * check `python --version`
  * latest 2.x or 3.x should be fine
* Download and install FontForge: http://fontforge.github.io/en-US/downloads/gnulinux-dl/
  * version should be at least `20141231`
  * verify version: `fontforge --version 2>&1 | grep libfontforge | awk '{print $NF}'`
* Download and install FontForge module (FontForge Python bindings)
  * e.g. on Linux Debian or Ubuntu: `sudo apt install python-fontforge` or `sudo apt install python3-fontforge`

## Windows 7

### Prerequisites

* Download and install FontForge: http://fontforge.github.io/en-US/downloads/windows-dl/

### Setup for Python 2

#### Open a terminal with Administrator priviledges

#### cd into FontForge installation directory

For example:
```sh
cd "C:\Program Files (x86)\FontForgeBuilds"
```

#### Run fontforge console batch file

```sh
fontforge-console.bat
```

#### install configparser

```sh
ffpython -m pip install configparser
```
#### Test out Nerd Fonts `font-patcher` script

```sh
ffpython C:\Path\to\nerd-fonts\font-patcher
```

Output should yield similar to:
```sh
...
font-patcher: error: too few arguments
```

## Windows 10

### Prerequisites

* Download and install Python (latest 2.x or 3.x should be fine): https://www.python.org/downloads/windows/
* Download and install FontForge: http://fontforge.github.io/en-US/downloads/windows-dl/
* Download and install Cygwin: https://cygwin.com/install.html or setup WSL ?

### Setup for Python 2

TODO

# Hack font specific Development

* What you need to contribute to the _Hack specific portion_ of Nerd Fonts

## OSX

todo

## Windows

* Download and install ttfautohint: https://www.freetype.org/ttfautohint/

## Linux

* FreeType
* Harfbuzz
* ttfautohint
* fonttools

### Build from source with Script from Hack Repo

- Pros: A lot easier and faster
- Cons: Not as much fine grained control

```sh
pip install fonttools
curl https://raw.githubusercontent.com/source-foundry/Hack/master/tools/scripts/install/ttfautohint-build.sh --output ~/ttfautohint-build.sh
chmod 770 ~/ttfautohint-build.sh
cd ~
sudo ./ttfautohint-build.sh
# Add the bin to your path
```

### Build each dependency individually ad hoc

- Pros: More control and better understanding of what is getting installed and setup
- Cons: more tedious

#### fonttools

```sh
pip install fonttools
```

#### Build FreeType from source

```sh
wget http://downloads.sourceforge.net/project/freetype/freetype2/2.7/freetype-2.7.tar.gz
tar -zxf freetype-2.7.tar.gz
cd freetype-2.7
./configure
make
sudo make install
```

#### Build Harfbuzz from source

```sh
wget http://www.freedesktop.org/software/harfbuzz/release/harfbuzz-1.3.4.tar.bz2
tar -xjf harfbuzz-1.3.4.tar.bz2
cd harfbuzz-1.3.4
./configure
make
sudo make install
```

#### g++ (if needed)

* if you ran into an issue where a compiler is needed you will probably have to start over with the config but first run: `make distclean`

```sh
sudo apt install g++
```

#### Build ttfautohint from source

```sh
wget http://download.savannah.gnu.org/releases/freetype/ttfautohint-1.6.tar.gz
tar -zxf ttfautohint-1.6.tar.gz
cd ttfautohint-1.6
./configure --with-qt=no --with-doc=no
make
sudo make install
```
##### C++11 compiler

* if you get an error during `make` for ttfautohint: `configure: error: *** A compiler with support for C++11 language features is required.`

Then install compiler such as `g++` (shown above) then re-run configure & make, etc

#### Verify the version

```sh
ttfautohint --version
ttfautohint 1.6
```

## Sanity Tests

### Adhoc test autohint

```sh
# cd into Nerd Fonts root directory
ttfautohint -l 4 -r 80 -G 350 -x 0 -H 181 -D latn -f latn -w G -W -t -X "" -I -m "bin/scripts/Hack/Hack-Regular-TA.txt" src/unpatched-fonts/Hack/Regular/Hack-Regular.ttf temp/Hack-Nerd-Font-autohinted.ttf
```

### We can run post build processing fixes on Hack

```sh
# cd into Nerd Fonts root directory
./font-patcher temp/Hack-Nerd-Font-autohinted.ttf
# spot check font, open in FontForge, etc.
```

## Troubleshooting

`ttfautohint: unrecognized option '-H'`

cause: Too old of a version of ttfautohint, works but doesn't have -H option

```
checking for HARFBUZZ... no
configure: error: Package requirements (harfbuzz >= 0.9.19) were not met:

No package 'harfbuzz' found

Consider adjusting the PKG_CONFIG_PATH environment variable if you
installed software in a non-standard prefix.

Alternatively, you may set the environment variables HARFBUZZ_CFLAGS
and HARFBUZZ_LIBS to avoid the need to call pkg-config.
See the pkg-config man page for more details.
```

cause: harfbuzz not installed or not installed correctly

```
tashaper.h:29:19: fatal error: hb-ft.h: No such file or directory
 #include <hb-ft.h>
                   ^
compilation terminated.
```

cause: harfbuzz not installed or not installed correctly

```
ttfautohint: undefined symbol: hb_ft_font_create
```

cause: harfbuzz not installed or not installed correctly


## Resources

* http://www.freetype.org/ttfautohint/doc/ttfautohint.html
* https://www.freetype.org/ttfautohint/doc/ttfautohint.html#compilation-and-installation


<!-- Reference Links -->

[Pandoc-installing]:http://pandoc.org/installing.html

