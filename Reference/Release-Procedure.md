---
title: Release Procedure
layout: default
---

## To make a new release:
vX.Y.P denotes the previous version, vX.Y.Z denotes the new version.

1. Ensure the branch builds
2. Update src/version.sh
3. Commit src/version.sh
4. `git tag vX.Y.Z`
5. `git push --tags`
6. Update the download link and SHA1 on the [website](https://github.com/inspircd/inspircd.github.com)
7. Generate a changelog for the [website](https://github.com/inspircd/inspircd.github.com) using `git shortlog --no-merges --pretty=short vX.Y.P..vX.Y.Z`
8. Create a new post on the [website](https://github.com/inspircd/inspircd.github.com) using `rake post`
9. Commit the new post
10. Update topic in [#InspIRCd](irc://irc.chatspike.net/inspircd)
