<h1 align="center">
	<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/nerd-fonts-logo.png" alt="Nerd Fonts" />
</h1>

## KISS Workflow*

> This describes the overall workflow and release methodology for the Nerd Fonts project. For specifics see the [Development Guide][]

### Goals

- Keep contributor(s) barrier to entry as low as possible
- _"[Release early, release often][Release-early-release-often]"_
- [KISS (Keep it simple, stupid)][KISS]

### Overview

- `master` is basically the stable dev or nightly branch
- Pull Requests are simply merged in (not rebased)
- There are no squashing requirements at the moment
- Each release will have a tag and a branch
  - Tags will follow format of: `vMAJOR.MINOR.PATCH`
  - Braches will follow format of: `MAJOR.MINOR.PATCH`

### Workflow

1. Pull Requests and Bug Fixes go directly into `master` after basic testing
2. Releases are built and 'released' about once a month
   1. Items/Issues ready at this time (i.e. in `master`) get added in the release
   2. Items/Issues not ready at this time do get to be in the official release


_*Based on [GitFlow][], [GitHub Flow][] and [a][gitflow-considered-harmful] [few][follow-up-to-gitflow-considered-harmful] [others][a-succesful-git-branching-model-considered-harmful] workflows_

<!-- links -->

[Development Guide]: https://github.com/ryanoasis/nerd-fonts/wiki/Development-Guide

[Release-early-release-often]: https://en.wikipedia.org/wiki/Release_early,_release_often
[KISS]: https://en.wikipedia.org/wiki/KISS_principle

[GitFlow]: http://nvie.com/posts/a-successful-git-branching-model/
[GitHub Flow]: http://scottchacon.com/2011/08/31/github-flow.html
[gitflow-considered-harmful]: http://endoflineblog.com/gitflow-considered-harmful
[follow-up-to-gitflow-considered-harmful]: http://endoflineblog.com/follow-up-to-gitflow-considered-harmful
[a-succesful-git-branching-model-considered-harmful]: http://barro.github.io/2016/02/a-succesful-git-branching-model-considered-harmful/