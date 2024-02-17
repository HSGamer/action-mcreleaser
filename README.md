# action-mcreleaser
Github Action to publish artifacts to multiple Minecraft-related platforms using [MCReleaser](https://github.com/HSGamer/MCReleaser)

## Inputs

### `files`

* Required: `true`

* A file or wildcard pattern to upload
* It's splited into primary and secondary files
* If a single line is provided, the first file will be the primary one, others will be secondary
* If multiple line is provided, the first line is for primary files, others are for secondary files

### `platforms`

* Required: `false`
* Default: `all`

* The platforms where the artifacts will be uploaded to

## Usage

```
- name: Release
  uses: HSGamer/action-mcreleaser@main
  with:
    files: |
      build/libs/MyPlugin-*.jar
      *.jar
    platforms: all
  env:
    GITHUB_TOKEN: ${{ github.token }}

    MODRINTH_TOKEN: ${{ secrets.MODRINTH_TOKEN }}
    MODRINTH_PROJECT: AABBCC
    MODRINTH_LOADERS: folia

    HANGAR_KEY: ${{ secrets.HANGAR_KEY }}
    HANGAR_PROJECT: AABBCC
    HANGAR_PLATFORM: paper
```

> Check [Environment Variables](https://github.com/HSGamer/MCReleaser#environment-variables) for available variables to put in `env`

## Example

* [`MoreFoWorld`](https://github.com/Folia-Inquisitors/MoreFoWorld/blob/82c7982aa1e784e8fe26ebc1dd0fc121d367062c/.github/workflows/gradle-release.yml#L34-L50)
