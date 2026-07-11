# C1XTZ's App Updater

I originally built this so users wouldn't have to manually redownload my apps for every update. Since I wasn't planning on managing multiple apps at first, I made the mistake of hardcoding the updater directly into each app's main file. That meant any time I tweaked the updater, I had to push a separate update for every single app.

To fix that, I came up with this: the updater is now bundled with my apps and checks this repo to update itself. Basically, it's an updater for the updater.

### Current Features

- **`Updater.checkVersion()`** checks if the app has a newer release on GitHub, either automatically (usually called via `onShowWindow`) every 8 hours or on demand via the button.
- **`Updater.applyUpdate()`** downloads and installs a pending update.
- **Self-updating**
  - `universal.lua` compares itself (and any other files listed in the app's `manifest.ini` under `[XTZ_UPDATER]`, e.g. `communities.lua`) against this repo's `versions.json`.
  - Only runs once the app itself is confirmed up to date, to avoid issues with `Updater.checkVersion()`
- **`Updater.drawUI()`** draws a "Update" settings tab (current version, check/install button, last-checked time, status message. example image below.)
- **`Communities.checkForUpdate()` - [Smartphone Only](https://github.com/C1XTZ/ac-smartphone)** syncs the community list and images against the latest data on GitHub. Same idea as the self updating updater, allows data changes without needing a full app update.

<p align="center">
<img src="https://raw.githubusercontent.com/C1XTZ/ac-xtzupdater/master/.github/img/updater.png">
</p>

# License

**All original source code** in this repository such as `.lua` scripts, build scripts, and any other code files, is licensed under the **GNU GPL v3.0 License**.

### What you can do:

- Modify the code
- Use the code privately and commercially
- Distribute the code (including in other projects)

### What you are required to do:

- Make the source code public (which means you cannot obfuscate the code in any way)
- Maintain the same license for any forks/modifications you do
- State what you have changed (this includes a simple "I changed the images and numbers")

### What you don't get:

- Liability
- Warranty

This may seem like a lot, but the general gist is: if you're going to use it, make sure people know where it's from, or if you're going to modify it, the modifications are public. The easiest way to do this is to create a [Fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks) of the repo/file you want to use/modify

Any questions or suggestions feel free to message me here, on Discord or on Twitter  
You'll find me under **[@c1xtz](https://discord.com/users/856601560728207371)** and **[@C1XTZ](https://twitter.com/C1XTZ)** respectively
