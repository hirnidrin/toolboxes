# toolboxes

A clone of [ublue-os toolboxes](https://github.com/ublue-os/toolboxes), with some additions for me. All credit goes to [team Universal Blue](https://universal-blue.org/) and contributors - my hat's off to you!

[![gemini-toolbox](https://github.com/hirnidrin/toolboxes/actions/workflows/build-gemini-toolbox.yml/badge.svg)](https://github.com/hirnidrin/toolboxes/actions/workflows/build-gemini-toolbox.yml) [![mybuntu-toolbox](https://github.com/hirnidrin/toolboxes/actions/workflows/build-mybuntu-toolbox.yml/badge.svg)](https://github.com/hirnidrin/toolboxes/actions/workflows/build-mybuntu-toolbox.yml) [![node22-toolbox](https://github.com/hirnidrin/toolboxes/actions/workflows/build-node22-toolbox.yml/badge.svg)](https://github.com/hirnidrin/toolboxes/actions/workflows/build-node22-toolbox.yml)

## Notes

1. This repo holds the full code of the upstream repo. I add 3 toolboxes:
   * `gemini-toolbox` Google Gemini CLI, powered by the [ublue-os wolfi-toolbox](https://github.com/ublue-os/toolboxes/tree/main/toolboxes/wolfi-toolbox) with Node.js 22.
   * `mybuntu-toolbox` The original ubuntu-toolbox with a few [additional Ubuntu packages](toolboxes/mybuntu-toolbox/packages.mybuntu).
   * `node22-toolbox` My Node.js v22 dev env, similar to the Chainguard node:22.11-dev LTS image, based on https://wolfi-dev/.
1. I only build these toolboxes -> available as [packages](https://github.com/hirnidrin?tab=packages&repo_name=toolboxes).
1. I skip building the original toolboxes provided upstream, using a modified `.github/workflows` folder - let's just work with the [ublue-os built original packages](https://github.com/orgs/ublue-os/packages?repo_name=toolboxes) when suitable.

## Local development

To test build a modified toolbox locally before committing to Github, run something like this in the repo base dir:
```
podman build -f toolboxes/node18-toolbox/Containerfile.node18 -t node18:test .
podman image ls
podman run --rm -it localhost/node18:test
```
