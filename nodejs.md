# NodeJS on M1

Node > 15.3.x provides Arm64 support as seen in the [release notes for 15.5.1](https://github.com/nodejs/node/blob/master/doc/changelogs/CHANGELOG_V15.md#15.5.1).   The main commit that adds the notes is [0fbade38ef](https://github.com/nodejs/node/commit/0fbade38ef)

Node 15.3.x+ supports Arm64.  Which means < 15.3.x will need intel architecture support if it is to be used.  I'm a fan of [nvm](https://github.com/nvm-sh/nvm) which is what is referenced below.  You know you are installing earlier versions of node on Arm64 architecture as it is insanely slow.  No idea if it completes or works after but here is the solution. 

## Installing Node Intel Versions on M1

```sh
# switch zsh to x86 arch
arch -x86_64 zsh
# install pre 15.3.x node version
nvm install 12.20
# switch back to Arm64 arch
arch -arm64 zsh
```
Tested working with old Angular and React projects.

## Checking the Arch

```sh
node -p process.arch

# output is
# arm64
# or
# x64
```