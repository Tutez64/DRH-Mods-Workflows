# DRH Mod Workflows

The release workflow of [Dungeon Rampage Haxe](https://github.com/Tutez64/Dungeon-Rampage-Haxe) mods. A mod made from [DRH-Mod-Template](https://github.com/Tutez64/DRH-Mod-Template) already calls it; nothing here is copied into a mod.

On a tag `vX.Y.Z` equal to the `version` of its `mod.json`, it runs `--pack-mod` from the latest [DRH Launcher](https://github.com/Tutez64/DRH-Launcher) release and drafts a GitHub release with the mod's zip and index entry. The author tests that zip, publishes the release, then runs `--submit-mod`. The steps are in DRH's [modding document](https://github.com/Tutez64/Dungeon-Rampage-Haxe/blob/master/docs/modding.md#mod-repository).

A mod calls it at the moving tag `v1`:

```yaml
jobs:
  release:
    uses: Tutez64/DRH-Mod-Workflows/.github/workflows/release.yml@v1
```

`v1` moves along the `v1.x.y` releases, so a fix reaches every mod; only a breaking change makes a `v2`.

`with: drhl-version: <tag>` runs that DRH Launcher release instead of the latest, a pre-release to test one.
