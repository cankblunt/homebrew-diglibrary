# Homebrew tap for DigLibrary

[DigLibrary](https://github.com/cankblunt/diglibrary) identifies your albums,
tells you whether a FLAC is really lossless, and renames and tags them in a way
you can undo. macOS, free, MIT.

```sh
brew tap cankblunt/diglibrary
brew install diglibrary
diglibrary
```

`ffmpeg` arrives as a dependency, which is the point of installing it this way:
it is not a Python package, so nothing `pip` or `pipx` does can bring it, and it
is what the Quality screen measures with.

`chromaprint` is optional and deliberately not a dependency — it is only needed
for identifying an album by its sound. Add it when you want that:

```sh
brew install chromaprint
```

Installing by name from the package index works too, and is the same
application: see the [three-line walkthrough](https://github.com/cankblunt/diglibrary#getting-started).

The formula in this repository is a copy. It is written, reviewed and versioned
in the application's own repository, under `packaging/homebrew/`.
