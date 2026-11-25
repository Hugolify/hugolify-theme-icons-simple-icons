# Hugolify theme icons: Simple Icons

The [Simple Icons](https://simpleicons.org/) brand logos for
[hugolify-theme-icons](https://github.com/hugolify/hugolify-theme-icons).

## Install

Nothing to do: hugolify-theme-icons imports this module. Brands are reached with
the `brand:` prefix (`brand:github`); the social menu adds it to its own names.

A site that imports hugolify-theme-icons with `ignoreImports: true` (to skip
Lucide) imports this module itself if it shows brands:

```yaml
# config/_default/module.yaml
imports:
  - path: github.com/hugolify/hugolify-theme-icons
    ignoreImports: true
  - path: github.com/hugolify/hugolify-theme-icons-simple-icons
```

## What it does

It mounts the `icons` folder of `github.com/simple-icons/simple-icons` to
`assets/icons/brands/`, where the engine resolves `brand:` names. Brand names are
Simple Icons slugs (`x`, not `twitter`).

`assets/icons/brands/linkedin.svg` is a local file: Simple Icons removed LinkedIn
on legal request in 2022, and this module's own assets take precedence over the
imported ones, so it fills that gap. Committing it re-introduces the trademark
exposure Simple Icons chose to avoid: a deliberate, accepted call.

## Simple Icons version

This module requires Simple Icons commit `c3777a7e48a5` (2026-06-07). Go selects
the highest version required, so a site moves it on its own, from the site:

```sh
hugo mod get github.com/simple-icons/simple-icons@master
```

Never use `@latest`: the highest git tag is the long abandoned `v2.17.1`, while
`master` ships the current brands.

## Documentations

- [Simple icons](https://simpleicons.org/)
- [hugolify-theme-icons](https://github.com/hugolify/hugolify-theme-icons)
- [Hugolify](https://www.hugolify.io/docs/)

## Licensing

Hugolify is free for personal or commercial projects (MIT license). Simple Icons
are released under [CC0](https://github.com/simple-icons/simple-icons/blob/develop/LICENSE.md);
the brands themselves remain their owners' trademarks.
