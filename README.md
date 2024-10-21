# toolboxes

A clone of [ublue-os toolboxes](https://github.com/ublue-os/toolboxes), with some additions for me. All credit goes to [team Universal Blue](https://universal-blue.org/) and contributors - my hat's off to you!

[![mybuntu-toolbox](https://github.com/hirnidrin/toolboxes/actions/workflows/build-mybuntu-toolbox.yml/badge.svg)](https://github.com/hirnidrin/toolboxes/actions/workflows/build-mybuntu-toolbox.yml) [![node18-toolbox](https://github.com/hirnidrin/toolboxes/actions/workflows/build-node18-toolbox.yml/badge.svg)](https://github.com/hirnidrin/toolboxes/actions/workflows/build-node18-toolbox.yml) [![node20-toolbox](https://github.com/hirnidrin/toolboxes/actions/workflows/build-node20-toolbox.yml/badge.svg)](https://github.com/hirnidrin/toolboxes/actions/workflows/build-node20-toolbox.yml)

## Notes

1. This repo holds the full code of the upstream repo. I add two toolboxes:
   * `mybuntu-toolbox` The original ubuntu-toolbox with a few [additional Ubuntu packages](toolboxes/mybuntu-toolbox/packages.mybuntu).
   * `node18-toolbox` My Node.js v18 dev env, similar to the Chainguard node:18-dev image, based on https://wolfi-dev/.
   * `node20-toolbox` My Node.js v20 dev env, similar to the Chainguard node:20-dev image, based on https://wolfi-dev/.
1. I only build these 3 toolboxes -> available as [packages](https://github.com/hirnidrin?tab=packages&repo_name=toolboxes).
1. I skip building the original toolboxes provided upstream, using a modified `.github/workflows` folder - let's just work with the [ublue-os built original packages](https://github.com/orgs/ublue-os/packages?repo_name=toolboxes) when suitable.

## Local development

To test build a modified toolbox locally before committing to Github, run something like this in the repo base dir:
```
podman build -f toolboxes/node18-toolbox/Containerfile.node18 -t node18:test .
podman image ls
podman run --rm -it localhost/node18:test
```
