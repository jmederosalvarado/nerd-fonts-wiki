<h1 align="center">
	<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/nerd-fonts-logo.png" alt="Nerd Fonts" />
</h1>


0. [What does it look like?](#what-does-it-look-like)
0. [How do I report issues?](#how-do-i-report-issues)
0. [What are all these variations?](#which-font)
0. [Which one do I want?](#which-font)
 0. [TL;DR](#tldr)
 0. [Explanation](#explanation)
0. [Why do some of the fonts names appear incorrect or appear to have typos?](#why-do-some-of-the-fonts-names-appear-incorrect-or-appear-to-have-typos)
0. [Why isn't my favorite font included (already patched)?](#why-isnt-my-favorite-font-included)

---

## What does it look like?

see [Screenshots](wiki/screenshots)

## How do I report issues? 

see: [Reporting Issues](wiki/reporting-issues)

## Which font?

### TL;DR

0. Pick your font family and then select from the `'complete'` directory.
  * Are you on Windows? Pick a font with the suffix `'Windows Compatible'`
  * Are you limited to mono fonts (because of your terminal, etc)? Pick a font with the suffix `'Mono'`

### Explanation

Once you narrow done your font choice of family (Droid Sans, Inconsolata, etc) and style (bold, italic, etc) you are provided with 3 main folders choices:
 * complete
  * This is most likely the one you want. It includes **all** of the glyphs from all of the glyph sets. Only caution here is that some fonts have glyphs in the _same_ code point so to include everything some had to be moved to alternate code points.
 * alternative
  * This attempts to contain _all permutations_ of the various glyphs. E.g. You want the font with only [Octicons][octicons] or you want the font with just [Font Awesome][font-awesome] and [Devicons][vorillaz-devicons]. The goal is to provide every combination possible in this folder.
 * minimal
  * This contains just the glyphs needed to use [vim-devicons][vim-devicons]. This is mostly provided for historical purposes. This might end up being removed at some point if it ends up causing too much confusion and/or providing little purpose in the grand scheme of things.

## Why do some of the fonts names appear incorrect or appear to have typos?

Some of the patched fonts are _intentionally _renamed due to license restrictions to comply with SIL Open Font License (OFL). In particular the [Reserved Font Names (RFNs)](http://scripts.sil.org/cms/scripts/page.php?item_id=OFL_web_fonts_and_RFNs#14cbfd4a)

## Why isn't my favorite font included?

It is most likely due to the font not being free _or_ due to licensing reasons which prevent distributing or distributing modified versions. E.g., [Consolas][consolas] (proprietary), [Input Mono][input-mono] (license restriction), [PragmataPro][pragmatapro] (not free), etc. 

Most fonts you can freely modify on your own so feel free to try patching them on your own :)

[vim-devicons]:https://github.com/ryanoasis/vim-devicons
[vorillaz-devicons]:http://vorillaz.github.io/devicons/
[font-awesome]:https://github.com/FortAwesome/Font-Awesome
[octicons]:https://github.com/github/octicons
[gabrielelana-pomicons]:https://github.com/gabrielelana/pomicons
[Seti-UI]:https://atom.io/themes/seti-ui
[ryanoasis-powerline-extra-symbols]:https://github.com/ryanoasis/powerline-extra-symbols
[consolas]:https://www.microsoft.com/typography/fonts/family.aspx?FID=300
[input-mono]:http://input.fontbureau.com/download/
[pragmatapro]:http://www.fsd.it/shop/fonts/pragmatapro/
