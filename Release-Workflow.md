<h1 align="center">
	<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/nerd-fonts-logo.svg?sanitize=true" alt="Nerd Fonts" />
</h1>

## Release Workflow

### `Merge latest PRs`
- Merge latest Pull Requests into `master` that are for the latest milestone
- Pull Requests and Bug Fixes go directly into `master` after basic testing

### `Run release script`
- Change to scripts dir (@todo fix reliance on dir)
  ```sh
  # todo fixme
  cd bin/scripts
  ```
- Execute script
  ```sh
  ./release.sh <version>
  ```

### `Update changelog`
- Manually update the `changelog.md` with all changes
  - see most recent release for example of the format: https://github.com/ryanoasis/nerd-fonts/releases
  - make sure to credit each Pull Request by referencing the person with @ followed by their GitHub id
  - the following is a template example:
```
## v<version>
### New Features

  - Added xyz (fixes #101)
  - Added ...

### Updates / Improvements

  - Updated xyz (fixes #101) (PR #101 @someone)
  - ...

### Fixes

  - Fixed xyz (fixes #101) (PR #101 @someone)
  - ...
```
- see diff comparison from last release vs master to ensure nothing is missed: `https://github.com/ryanoasis/nerd-fonts/compare/latest-release-branch...master`
  - e.g. https://github.com/ryanoasis/nerd-fonts/compare/1.0.0...master

### `Update the Sankey Diagram (if glyph changes)`

- Navigate to http://sankeymatic.com/build/
- Enter the list of Flows, in the correct format. e.g. `Nerd Fonts [#] Glyph Set Name`
```
Nerd Fonts [7] Powerline Symbols
Nerd Fonts [30] Powerline Extra Symbols
Nerd Fonts [675] Font Awesome
Nerd Fonts [170] Font Awesome Extension
Nerd Fonts [197] Devicons
Nerd Fonts [228] Weather Icons
Nerd Fonts [53] Seti UI + Custom
Nerd Fonts [172] Octicons
Nerd Fonts [29] Font Linux
Nerd Fonts [5] IEC Power Symbols
Nerd Fonts [8] Pomicons
Nerd Fonts [2119] Material Design
```
- Use the following settings
  - for 'Size, Spacing & Shape:'
    - Use all defaults, except
      - for 'curviness': max "("
      - for 'Vertical Space between Nodes': 20px
      - for 'node width': '20px'
  - for 'Colors:'
    - for 'Node Colors: Use theme:' "A"
  - "Labels & Units..."
    - Use all defaults (used to use 'mono')
    - 'Units: suffix' Use (with a leading space): ' icons'
  - "Advanced"
    - Select "Reverse the graph (flow right-to-left)"
  - Export as 1x (basic) for PNG or just SVG


### `Update readme`
- Update the `readme.md`
  - If a new font was added, add it to the table of [Patched Fonts][]
  - If any new glyphs or glyph sets were added
    - Update individual glyph tables
    - Use an updated Sankey Diagram
  * Update the "counts" in the [Features Section][]
    * You can get this information by simply passing a second param to the "all patcher": `./gotta-patch-em-all-font-patcher\!.sh "" info`
      * "`X` already patched font families" -> Give exact number from 'typefaces' line
      * "Over `X` unique combinations/variations..." -> round down to nearest hundred from 'variation' line
      * "Over `X` glyphs/icons combined" -> manual process for now (@todo)
  * Update the "counts" in the [Combinations Section][]
    * Again, get this info from the "all patcher"
  * Update the `font-patcher` help output section under "Patch Your Own Font" if needed

### `Create release on GitHub`
- verify `master` branch has all changes commited and pushed
  - `git status -s`
- update `master` from remote
  - `git pull origin master`
- create the new branch
  - verify what the version should be by double checking remote branches
    - `git branch -r | grep '[0-9]\+\.[0-9]\+\.[0-9]\+$'`
  - `git checkout -b <semver_based_branch_name>`
- push the new branch
  - `git push -u origin <semver_based_branch_name>`
- create tag
  - "vMAJOR.MINOR.PATCH"
  - i.e. same as branch name but with prefixed with a 'v'
  - e.g. `git tag v1.5.3`
- push latest tags
  - `git push --tags`
- Create new release on GitHub
  - copy and paste latest release details from `changelog.md` into release notes

### `Run upload script`
- Execute `upload-archives.sh` to upload font archives to the latest release
  - with no parameter given it will upload to the 'latest' release via GitHub API

### `Verify uploaded files`
- Verify font archives are showing for latest release

### `Update website (github pages)`
- Checkout branch: [`gh-pages`](https://github.com/ryanoasis/nerd-fonts/tree/gh-pages)
- Update the [download links](https://github.com/ryanoasis/nerd-fonts/blob/gh-pages/_posts/2017-01-03-downloads.md)
  - If there are new fonts add the new links
- Update the [release notes](https://github.com/ryanoasis/nerd-fonts/blob/gh-pages/_posts/2017-01-06-release.md)
  - Insert new release notes from [changelog](https://github.com/ryanoasis/nerd-fonts/blob/master/changelog.md) to the top
  - Remove 'open' attribute from previous release container div

## Ad hoc updating of the Glyph-only fonts
```sh
./font-patcher -ext ttf -out ./src/glyphs/ --complete ./src/glyphs/NerdFontsSymbols\ 1000\ EM\ Nerd\ Font\ Complete\ Blank.sfd
./font-patcher -ext ttf -out ./src/glyphs/ --complete ./src/glyphs/NerdFontsSymbols\ 2048\ EM\ Nerd\ Font\ Complete\ Blank.sfd
```

<!-- links -->

[pulls]: https://github.com/ryanoasis/nerd-fonts/pulls
[Features Section]: https://github.com/ryanoasis/nerd-fonts/blob/master/readme.md#features
[Combinations Section]: https://github.com/ryanoasis/nerd-fonts/blob/master/readme.md#combinations
[Patched Fonts]: https://github.com/ryanoasis/nerd-fonts/blob/master/readme.md#patched-fonts