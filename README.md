# OpenWRT Builder
Because I felt like it, honestly. I put a little more time into this than I anticipated, so I hope it helps you too!

## Simple usage with similar vibes to building AOSP
| Command | Usage |
| --- | --- |
| `. build/envsetup` \|\| `source build/envsetup` | Imports the build environment into your shell to provide commands. |
| `sync` | Installs/updates the latest OpenWRT snapshot source tree, updates your local feeds that contain git repos, and generates your local feed list. |
| `lunch` | Lists available lunch targets. |
| `lunch $TARGET` | Prepares the build environment to compile for `$TARGET`. |
| `make` | Compiles the OpenWRT firmware for your lunch target. Optionally passes args through to the underlying call to make. See below for automatic sysupgrade sideloads. |
| `package $PACKAGE` | Compiles the specified package for your lunch target. |

## Configurable for developer environments
Check out the [examples](examples) to get started. It's an exercise for the reader to know what to do from here!

## LICENSE
The source code for OpenWRT Builder is released under the GNU Affero General Public License Version 3. See [LICENSE](LICENSE) for more details.

## Donations
All donations are appreciated and help me stay awake at night to work on this more. Even if it's not much, it helps more than not in the long run! You can even become a sponsor of me if you're okay with a recurring monthly charge.

![GitHub Sponsors](https://img.shields.io/github/sponsors/JoshuaDoes?style=for-the-badge&labelColor=%23FAFAFA&color=%231C1C1C)
