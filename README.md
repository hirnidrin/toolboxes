# toolboxes

A clone of [ublue-os toolboxes](https://github.com/ublue-os/toolboxes), with some additions/modifications for me. All credit goes to [team Universal Blue](https://universal-blue.org/) and contributors - my hat's off to you!

## Notes

1. This repo holds the full code of the upstream repo. My additions/modifications are:
   * `node18-toolbox` Node.js v18 dev env based on https://wolfi-dev/ , similar to Chainguard node:18-dev image.
1. I periodically build my extra toolboxes -> available as [packages](https://github.com/hirnidrin?tab=packages&repo_name=toolboxes).
1. I skip building the originally provided toolboxes using a modified `.github/workflows` folder - let's just work with the [ublue-os built packages](https://github.com/orgs/ublue-os/packages?repo_name=toolboxes).

## Local development

To test build a modified toolbox locally before committing to Github, run something like this in the repo base dir:
```
podman build -f toolboxes/node18-toolbox/Containerfile.node18 -t node18:test .
podman image ls
podman run --rm -it localhost/node18:test
```
