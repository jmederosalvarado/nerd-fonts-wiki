<h1 align="center">
	<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/nerd-fonts-logo.svg?sanitize=true" alt="Nerd Fonts" />
</h1>

In general Patched Fonts are not necessary required, because several systems support [font substitution (or fallback)](https://en.wikipedia.org/wiki/Font_substitution)


## Windows

The EUDC feature of Windows can be used to define a fall-back font that will be used for Glyphs that are not found in the current font. This means that a single Nerd Font can be installed on a Windows machine, and the Nerd Font glyphs will then be shown for all other fonts in the system without need for patching other fonts.

Info on EUDC can be found here:
https://msdn.microsoft.com/en-us/library/windows/desktop/dd317836(v=vs.85).aspx

Example usage
```
Windows Registry Editor Version 5.00
;
; More info here: https://msdn.microsoft.com/en-us/library/windows/desktop/dd317836(v=vs.85).aspx
;
[HKEY_CURRENT_USER\EUDC\1252]
"SystemDefaultEUDCFont"="Hack Nerd Font Complete Windows Compatible.ttf"
```

Adapted from @sharkusk's issue, for complete context see: https://github.com/ryanoasis/nerd-fonts/issues/159

## Linux

Leveraging Fontconfig

see: https://github.com/ryanoasis/nerd-fonts/blob/master/10-nerd-font-symbols.conf

# Help

* [FAQ](https://github.com/ryanoasis/nerd-fonts/wiki/FAQ-and-Troubleshooting)
* [Screenshots](wiki/screenshots)
* [Reporting Issues](wiki/Reporting-Issues)


# Resources

* [FontForge](https://fontforge.github.io/)
* [Writing python scripts to change fonts in FontForge](https://fontforge.github.io/en-US/documentation/scripting/python/)
* [Writing python scripts to change fonts in FontForge (old website)](https://fontforge.github.io/python.html)
* [ttfautohint](https://www.freetype.org/ttfautohint/)


[VimDevIcons]:https://github.com/ryanoasis/vim-devicons
[vorillaz-devicons]:http://vorillaz.github.io/devicons/
[font-awesome]:https://github.com/FortAwesome/Font-Awesome
[octicons]:https://github.com/github/octicons
[gabrielelana-pomicons]:https://github.com/gabrielelana/pomicons
[Seti-UI]:https://atom.io/themes/seti-ui
[ryanoasis-powerline-extra-symbols]:https://github.com/ryanoasis/powerline-extra-symbols