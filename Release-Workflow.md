<h1 align="center">
	<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/nerd-fonts-logo.png" alt="Nerd Fonts" />
</h1>

## Release Workflow

### `Merge latest PRs`
- Merge latest Pull Requests into `master` that are for the latest milestone
- Pull Requests and Bug Fixes go directly into `master` after basic testing

### `Run release script`
- Execute `release.sh <version>`

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

### `Update readme`
- Update the `readme.md`
  - If a new font was added, add it to the table of [Patched Fonts][]
  * Update the "counts" in the [Features Section][]
    * You can get this information by simply passing a second param to the "all patcher": `./gotta-patch-em-all-font-patcher\!.sh "" info`
      * "`X` already patched font families" -> Give exact number from 'typefaces' line
      * "Over `X` unique combinations/variations..." -> round down to nearest hundred from 'variation' line
      * "Over `X` glyphs/icons combined" -> manual process for now (@todo)
  * Update the "counts" in the [Combinations Section][]
    * Again, get this info from the "all patcher"
  * Update the `font-patcher` help output section under "Patch Your Own Font" if needed

`Create release on GitHub`
- Create new release on GitHub and paste latest release details from `changelog.md`

### `Run upload script`
- Execute `upload-archives.sh` to upload font archives to the latest release

### `Verify uploaded files`
- Verify font archives are showing for latest release

<!-- links -->

[pulls]: https://github.com/ryanoasis/nerd-fonts/pulls
[Features Section]: https://github.com/ryanoasis/nerd-fonts/blob/master/readme.md#features
[Combinations Section]: https://github.com/ryanoasis/nerd-fonts/blob/master/readme.md#combinations
[Patched Fonts]: https://github.com/ryanoasis/nerd-fonts/blob/master/readme.md#patched-fonts