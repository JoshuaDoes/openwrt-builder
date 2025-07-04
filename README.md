# OpenWRT Builder
Because I felt like it, honestly. I put a little more time into this than I anticipated, so I hope it helps you too!

## Simple usage with similar vibes to building AOSP
| Command | Usage |
| --- | --- |
| `. build/envsetup` OR `source build/envsetup` | Imports the build environment into your shell to provide commands. |
| `sync` | Installs/updates the latest OpenWRT snapshot source tree, updates your local feeds which contain git repos, and generates your local feed list. |
| `sync release` OR `sync $TAG` | Switches to the latest release tag, or optionally a specified tag/branch, and runs a sync. |
| `sync snapshot` | Switches back to the snapshot branch and runs a sync. |
| `lunch` OR `targets` | Lists available lunch targets including symlinks in an alphabetical order. |
| `lunch $TARGET` OR `target $TARGET` | Prepares the build environment to compile for `$TARGET`. Ingests all configs found under `configs`. |
| `target` | Displays all details about the current lunch target (as printed elsewhere throughout the build). |
| `make` OR `firmware` | Compiles the OpenWRT firmware for your lunch target. Optionally passes args through to the underlying call to make, including OpenWRT make commands from the root of the tree. See below for automatic sysupgrade sideloads. |
| `package $PACKAGE` | Compiles the specified package for your lunch target. |
| `sysupgrade` | Calls a script at `sysupgrade/$ID` to sideload the provided `$FIRMWARE` image. See [examples/sysupgrade](examples/sysupgrade) for how to prepare this script. |
| `clean` | Removes all built files from `$OUT` and `$OUTPKG`. Removes the entire out folder with no target for lunch. |

## Example usage
```
#Required to import the build environment into your current shell.
source build/envsetup

#Required for the first time to get the OpenWRT source so the commands will be useful.
sync

#If you would prefer to use the latest release tag, now is the time to switch to it.
sync release

#Required to select a lunch target.
lunch netgear_r6020

#Required for the first time to update and install your package feeds.
#Optional, but will ensure `make download` in OpenWRT source tree to avoid networking during a build.
sync

# Make an entire firmware and copy it out.
make

# Sideload the most recently built firmware, or build a fresh firmware to sideload it if one isn't found.
sysupgrade

# Build a specific package and copy it out, i.e. one that your local feed might provide.
package luci-theme-material3
```

## Configurable for developer environments
Check out the [examples](examples) to get started. It's an exercise for the reader to know what to do from here!

## LICENSE
The source code for OpenWRT Builder is released under the GNU Affero General Public License Version 3. See [LICENSE](LICENSE) for more details.

## Donations
All donations are appreciated and help me stay awake at night to work on this more. Even if it's not much, it helps more than not in the long run! You can even become a sponsor of me if you're okay with a recurring monthly charge.

[![GitHub Sponsors](https://img.shields.io/github/sponsors/JoshuaDoes?style=for-the-badge&labelColor=%23FAFAFA&color=%231C1C1C)](https://github.com/sponsors/JoshuaDoes)
