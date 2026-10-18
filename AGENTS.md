# Agent instructions

This repo is configuration only. A change here reaches every project that
extends it, so keep each preset to what is true of all of them and leave
anything specific to one project in that project.

- Tag a release `vMAJOR.MINOR.PATCH` after changing a preset. A formatting change is a breaking change.
- Check a Biome change with `biome check .` here, then in one project, before tagging.
