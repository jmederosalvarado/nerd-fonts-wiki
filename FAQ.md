<h1 align="center">
	<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/nerd-fonts-logo.png" alt="Nerd Fonts" />
</h1>


0. [What does it look like?](#what-does-it-look-like)
0. [How do I report issues?](#how-do-i-report-issues)
0. [What are all these variations?](#which-font)
0. [Which one do I want?](#which-font)
 0. [TL;DR](#tldr)
 0. [Explanation](#explanation)

---

## What does it look like?

see [Screenshots](wiki/screenshots)

## How do I report issues? 

see: [Reporting Issues](wiki/how-to-report-issues)

## Which font?

### TL;DR
Pick your font family and then select from the 'complete' folder.
Are you on Windows? Pick one with 'Windows Compatible'
Are you limited to mono fonts (because of your terminal etc)? Pick one with 'Mono'

### Explanation

Once you narrow done your font choice of family (Droid Sans, Inconsolata, etc) and style (bold, italic, etc) you are provided with 3 main folders choices:
 * complete
  * This is most likely the one you want. It includes **all** of the glyphs from all of the glyph sets. Only caution here is that some fonts have glyphs in the _same_ code point so to include everything some had to be moved to alternate code points.
 * alternative
  * This attempts to contain _all permutations_ of the various glyphs. E.g. You want the font with only [Octicons][octicons] or you want the font with just [Font Awesome][font-awesome] and [Devicons][vorillaz-devicons]. The goal is to provide every combination possible in this folder.
 * minimal
  * This contains just the glyphs needed to use [vim-devicons][vim-devicons]. This is mostly provided for historical purposes. This might end up being removed at some point if it ends up causing too much confusion and/or providing little purpose in the grand scheme of things.


[vim-devicons]:https://github.com/ryanoasis/vim-devicons
[vorillaz-devicons]:http://vorillaz.github.io/devicons/
[font-awesome]:https://github.com/FortAwesome/Font-Awesome
[octicons]:https://github.com/github/octicons
[gabrielelana-pomicons]:https://github.com/gabrielelana/pomicons
[Seti-UI]:https://atom.io/themes/seti-ui
[ryanoasis-powerline-extra-symbols]:https://github.com/ryanoasis/powerline-extra-symbols