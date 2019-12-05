# Build scripts

**DISCLAIMER**: This is only for Debian-based distributions. WSL is **NOT** supported.

## Prerequisites

1. Make a Telegram Bot (@BotFather)

2. Fork this repository.

3. Make a GitHub token with proper permissions for uploading releases to your repositories.

## How to use this repo (non-Jenkins)

1. Clone your fork of this repository.

2. Make your changes in the config.sh script (more information about the flags below). Make sure you commit and push your changes to your fork.

3. If you haven't ever built Android on your PC, open a terminal in the directory you cloned this repository and run `init.sh`

4. If you've already built Android on your PC, run `clean.sh`

5. Export TELEGRAM_CHAT, TELEGRAM_TOKEN and GITHUB_TOKEN to your respective values:

* `TELEGRAM_CHAT` - the ID of the channel/group chat you want the Bot to post your messages to.

* `TELEGRAM_TOKEN` - the token of your Telegram Bot.

* `GITHUB_TOKEN` - your GitHub token (make sure it has permissions to upload releases to your repos)


## How to use this repo (Jenkins)

1. Switch to the "jenkins" user (usually by `su jenkins`)

2. Clone your fork of this repo in your Jenkins home directory (`/var/lib/jenkins`) or any place where your Jenkins user can read/write to.

3. Make your changes in the config.sh script (more information about the flags below). Make sure you commit and push your changes to your fork.

4. Switch to the Jenkins web console.

5. Make a new job with the "Freeflow" type. Do **NOT** put spaces in the name of the job.

6. Set the custom working directory to the directory you cloned this repository.

7. Add a build step for bash.

8. Copy the contents of jenkins.sh to it.

9. Change the values of TELEGRAM_CHAT, TELEGRAM_TOKEN and GITHUB_TOKEN to your respective values:

* `TELEGRAM_CHAT` - the ID of the channel/group chat you want the Bot to post your messages to.

* `TELEGRAM_TOKEN` - the token of your Telegram Bot.

* `GITHUB_TOKEN` - your GitHub token (make sure it has permissions to upload releases to your repos)

## Configuration flags

`GITHUB_USER` - your GitHub username

`GITHUB_EMAIL` - your GitHub email

`device` - your device codename (e.g. `blueline` for Pixel 3)

`ROM` - name of your ROM (e.g. `AOSP`)

`ROM_DIR` - directory where your ROM source will reside (e.g. `/var/lib/jenkins/AOSP`)

`ROM_VERSION` - version of your ROM (e.g. `9.0 Pie`)

`official` - `true` or `1` if you're building an official build, `false` or `0` if you're building an unofficial build

`local_manifest_url` - your local manifest URL (e.g. `https://example.link/local_manifest.xml`)

`manifest_url` - your ROM's manifest repo URL (e.g. `https://android.googlesource.com/platform/manifest`)

`rom_vendor_name` - your ROM's custom vendor name (e.g. `lineage`)

`branch` - branch of the manifest to sync (e.g. `lineage-16.0`)

`bacon` - the package to build (default: `bacon`)

`buildtype` - the build type to build (e.g. `userdebug`). If you don't specify a build type, it defaults to userdebug.

`jenkins` - `true` or `1` - you use Jenkins; `false` or `0` - you don't use Jenkins

`release_repo` - your GitHub username + name of the repo to upload the releases (e.g. `JarlPenguin/releases`)

`timezone` - your timezone (default: `UTC`)
