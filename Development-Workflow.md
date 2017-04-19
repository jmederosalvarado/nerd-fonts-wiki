<h1 align="center">
	<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/nerd-fonts-logo.png" alt="Nerd Fonts" />
</h1>


## KISS Workflow*

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

[GitFlow]: http://nvie.com/posts/a-successful-git-branching-model/
[GitHub Flow]: http://scottchacon.com/2011/08/31/github-flow.html
[gitflow-considered-harmful]: http://endoflineblog.com/gitflow-considered-harmful
[follow-up-to-gitflow-considered-harmful]: http://endoflineblog.com/follow-up-to-gitflow-considered-harmful
[a-succesful-git-branching-model-considered-harmful]: http://barro.github.io/2016/02/a-succesful-git-branching-model-considered-harmful/