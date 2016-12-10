# Contributor / Developer Setup

* The basics of what you need to get up and running :)

## Prerequisites

### Required

* Git
* FontForge
* FontForge python bindings
* Python 2 and/or Python 3

### Highly Recommended

* ShellCheck
* Pyflakes (PEP8 compliance)

## Hack (Knack) font building prerequisites

### OSX

todo

### Linux

* FreeType
* Harfbuzz
* ttfautohint

#### Build FreeType from source

```
cd freetype-2.7
./configure
make
sudo make install
```

#### Build Harfbuzz from source

```
wget http://www.freedesktop.org/software/harfbuzz/release/harfbuzz-1.3.4.tar.bz2
tar -xjf harfbuzz-1.3.4.tar.bz2
cd harfbuzz-1.3.4
./configure
make
sudo make install
```

#### g++ (if needed)

```
sudo apt install g++
```

#### Build ttfautohint from source

```
cd ttfautohint-1.6
./configure --with-qt=no --with-doc=no
make
sudo make install
```

##### Verify the version

```
ttfautohint --version
ttfautohint 1.6
```

## Sanity Tests

### Adhoc test autohint

```
ttfautohint -l 4 -r 80 -G 350 -x 0 -H 181 -D latn -f latn -w G -W -t -X "" -I -m "bin/scripts/Hack/Hack-Regular-TA.txt" Knack\ Regular\ Nerd\ Font\ Complete.ttf.tmp Knack\ Regular\ Nerd\ Font\ Complete.ttf
```

## Troubleshooting

`ttfautohint: unrecognized option '-H'`

cause: Too old of a version of ttfautohint, works but doesn't have -H option

```shell
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

```shell
tashaper.h:29:19: fatal error: hb-ft.h: No such file or directory
 #include <hb-ft.h>
                   ^
compilation terminated.
```

cause: harfbuzz not installed or not installed correctly

```shell
ttfautohint: undefined symbol: hb_ft_font_create
```

cause: harfbuzz not installed or not installed correctly


## Resources

* http://www.freetype.org/ttfautohint/doc/ttfautohint.html
* https://www.freetype.org/ttfautohint/doc/ttfautohint.html#compilation-and-installation