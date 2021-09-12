# goreleaser-example

> refer to https://goreleaser.com/quick-start/

## Environmental preparation

* go
* github
* git
* [goreleaser](https://github.com/goreleaser/goreleaser/releases)

## How to achieve release

### github

create repo `goreleaser-example`

### git

`git init`

### go

`go mod init github.com/jaronnie/goreleaser-example`

### goreleaser

`goreleaser init`

You can verify your `.goreleaser.yml` is valid by running the [check](https://goreleaser.com/cmd/goreleaser_check/) command:

`goreleaser check`

In order to release to GitHub, you'll need to export a `GITHUB_TOKEN` environment variable, which should contain a valid GitHub token with the `repo` scope. It will be used to deploy releases to your GitHub repository. You can create a new github token [here](https://github.com/settings/tokens/new).

`export GITHUB_TOKEN="YOUR_GH_TOKEN"`

```shell
git tag -a v0.0.1 -m "First release"
git push origin v0.0.1
```

Now you can run GoReleaser at the root of your repository:

`goreleaser release`

