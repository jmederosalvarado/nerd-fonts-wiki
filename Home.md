<h1 align="center">
	<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/nerd-fonts-logo.svg?sanitize=true" alt="Nerd Fonts" />
</h1>


0. [What is it?](#what)
0. [What is the purpose?](#why)
0. [Help](#help)
0. [Additional Resources](#resources)

---


# What

**Nerd Fonts** is a project that attempts to patch as many developer targeted and/or used fonts as possible. The patch is to specifically add a high number of additional glyphs from popular 'iconic fonts' such as [Font Awesome][font-awesome], [Devicons][vorillaz-devicons], [Octicons][octicons], and others.

Specifically in this Repository **Nerd Fonts** provides:
 * A python script to patch any `otf` or `ttf` font desired with several command line options
 * A collection of already patched popular fonts for download
 * A collection of the original un-patched versions of fonts for re-patching purposes and for reference

# Why

Originally created for and a piece of another project named [VimDevIcons][].

[VimDevIcons][] is Vim plugin that displays glyphs based on filetypes or extensions and other specific matches. There was no specific font that contained all of the glyphs that I wanted to use. I started off with combining glyphs from several different fonts as well as adding my own custom glyphs. The font itself began to grow large enough that it made sense to break out as its own project and repository.

Being its own project and repository adds a lot of benefits besides just separation of concerns. It allows others to more easily contribute and use the font without using (or even having knowledge of) [VimDevIcons][] specifically.

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