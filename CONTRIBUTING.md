# Contributing

## Building the Docker image

Building the Docker image requires [GNU
make](https://www.gnu.org/software/make/).

Here is a list of available targets:

| Target       | Description                       |
| ---          | ---                               |
| `make build` | Build the image.                  |
| `make push`  | Upload the image to Docker Hub.   |
| `make login` | Log into Docker Hub.              |
| `make ci`    | Target for Continous Integration. |

Pass `NAMESPACE` to prefix the image with a Docker Hub namespace. The default is
`DOCKER_USERNAME`.

The `login` target is provided for non-interactive use and looks for
`DOCKER_USERNAME` and `DOCKER_PASSWORD`.

## Upgrading upstream

```sh
scripts/upgrade.sh $version # 2.0.0
git push
```

## Releasing

```sh
$EDITOR README.md
git commit --all --message="Update README.md"
$EDITOR CHANGELOG.md
git commit --all --message="Update CHANGELOG.md"
scripts/release.sh
git push --all --follow-tags
github-release $version
```

See [github-release](https://github.com/cjolowicz/scripts/blob/master/github/github-release.sh).
