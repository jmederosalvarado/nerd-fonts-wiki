<h1 align="center">
	<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/nerd-fonts-logo.png" alt="Nerd Fonts" />
</h1>


0. [What does it look like?](#what-does-it-look-like)
0. [How do I report issues?](#how-do-i-report-issues)
0. [What are all these variations?](#which-font)
0. [Which font do I want?](#which-font)
   - [TL;DR](#tldr)
   - [Explanation](#explanation)
0. [Why do the glyphs look small, squished, or not full width?](#why-do-the-glyphs-look-small-squished-or-not-full-width)
0. [Why do some of the fonts names appear incorrect or appear to have typos?](#why-do-some-of-the-fonts-names-appear-incorrect-or-appear-to-have-typos)
0. [What do these acronym variations in the font name mean: `LG`, `L`, `M`, `S`, `DZ`, `SZ`?](#what-do-these-acronym-variations-in-the-font-name-mean-lg-l-m-s-dz-sz)
0. [Why isn't my favorite font included (already patched)?](#why-isnt-my-favorite-font-included)
0. [Error: munmap_chunk(): invalid pointer](#munmap_chunk-invalid-pointer)
0. [segmentation fault running patcher](#segmentation-fault-running-python-patcher)

---

## What does it look like?

see [Screenshots](wiki/screenshots)

## How do I report issues? 

see: [Reporting Issues](wiki/reporting-issues)

## Which font?

### TL;DR

* Pick your font family and then select from the `'complete'` directory.
  * If you are on Windows pick a font with the `'Windows Compatible'` suffix.
    * This includes specific tweaks to ensure the font works on Windows, in particular monospace identification and font name length limitations
  * If you are limited to monospaced fonts (because of your terminal, etc) then pick a font with the `'Mono'` suffix.
    * This denotes that the Nerd Font glyphs will be monospaced not necessarily that the entire font will be monospaced

### Explanation

Once you narrow down your font choice of family (`Droid Sans`, `Inconsolata`, etc) and style (`bold`, `italic`, etc) you have 2 main choices:

#### `Option 1: Download already patched font`

 * download an already patched font from the `complete` folder
   * This is most likely the one you want. It includes **all** of the glyphs from all of the glyph sets. Only caution here is that some fonts have glyphs in the _same_ code point so to include everything some had to be moved to alternate code points.

#### `Option 2: Patch your own font`

 * patch your own variations with the various options provided by the font patcher (see each font's readme for full list of combinations available)
   * This is the option you want if the font you use is _not_ already included or you want maximum control of what's included
   * This contains a list of _all permutations_ of the various glyphs. E.g. You want the font with only [Octicons][octicons] or you want the font with just [Font Awesome][font-awesome] and [Devicons][vorillaz-devicons]. The goal is to provide every combination possible in this folder.

## Why do the glyphs look small, squished, or not full width?

Make sure your terminal supports double-width (aka full width ambiguous characters). Some terminal emulators (such as URxvt) do not work well or at all with such characters. If this is the case you will have to use the single-width (monospace) version of a given font _or_ use a different terminal emulator.

For URxvt specific help or things to try see the wiki page [Terminal Emulators URxvt](https://github.com/ryanoasis/nerd-fonts/wiki/Terminal-Emulators#urxvt)

Issue references: [#155][issue-155], [#37][issue-37]

## Why do some of the fonts names appear incorrect or appear to have typos?

Some of the patched fonts are _intentionally _renamed due to license restrictions to comply with SIL Open Font License (OFL). In particular the [Reserved Font Names (RFNs)](http://scripts.sil.org/cms/scripts/page.php?item_id=OFL_web_fonts_and_RFNs#14cbfd4a)

## What do these acronym variations in the font name mean: `LG`, `L`, `M`, `S`, `DZ`, `SZ`?

- LG - Line Gap
- L - Large
- M - Medium
- S - Small
- DZ - Dotted Zero
- SZ - Slashed Zero

This particularly applies to Meslo at the moment:

> Meslo has changed it’s name to Meslo LG which now includes three variants: 
small, medium and large.
>
> LG stands for Line Gap, so there’s one variant for smaller vertical line spacing, 
more towards Apple’s Menlo, a normal line gap (which equals Meslo v0.1) and 
a large gap, which is more than twice the space of Apple’s Menlo.
>
> In addition to Regular, there’s Italic, Bold and Bold Italic font styles 
included for each LG variant.

source: https://github.com/andreberg/Meslo-Font


## Why isn't my favorite font included?

It is most likely due to the font not being free _or_ due to licensing reasons which prevent distributing or distributing modified versions. 

E.g.

* [Input Mono][input-mono] (license restriction)
  * Possibly coming with external hosting :)
* [PragmataPro][pragmatapro] (not free)
* [Consolas][consolas] (proprietary)


Most fonts you can freely modify on your own so feel free to try patching them on your own :)

## munmap_chunk(): invalid pointer

### Issue

`[Font Patcher Py3] Error in python3': munmap_chunk(): invalid pointer`

For the original details on the solution: [comment on #129][issue-129-1]

Original Issue Reference: [`#129`][issue-129]

### Solutions

- `Option 1:` Downgrade Python to `3.5.2-3` and FontForge to `20161012-2` [`ref`][issue-129-a]
- `Option 2:` Update to the latest FontForge version (issue has been fixed in recent versions) [`ref`][issue-129-b]
- `Option 3:` Install `aur/python35` instead of downgrading Python [`ref`][issue-129-c]

## segmentation fault running python patcher

### Issue

`segmentation fault`

For the original details on the solution: [comment on #8][issue-8-1]

Original Issue Reference: [`#8`][issue-8]

### Solutions

- `Option 1:` Update FontForge and/or Python 2.x on macOS (OSX)
- `Option 2:` Patch font on Linux

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

[issue-155]:https://github.com/ryanoasis/nerd-fonts/issues/155
[issue-129]:https://github.com/ryanoasis/nerd-fonts/issues/129
[issue-129-1]:https://github.com/ryanoasis/nerd-fonts/issues/129#issuecomment-279142777
[issue-129-a]:https://github.com/fontforge/fontforge/issues/2992#issuecomment-272713810
[issue-129-b]:https://github.com/fontforge/fontforge/issues/2992#issuecomment-274091254
[issue-129-c]:https://github.com/fontforge/fontforge/pull/3046
[issue-37]:https://github.com/ryanoasis/nerd-fonts/issues/37
[issue-8]:https://github.com/ryanoasis/nerd-fonts/issues/8
[issue-8-1]:https://github.com/ryanoasis/nerd-fonts/issues/8#issuecomment-106804334
