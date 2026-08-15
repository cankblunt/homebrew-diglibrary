# Homebrew tap for DigLibrary

[DigLibrary](https://cankblunt.github.io/diglibrary/) identifies your albums,
tells you whether a FLAC is really lossless, and renames and tags them in a way
you can undo. macOS, free, MIT.

```sh
brew trust --tap cankblunt/diglibrary
brew install cankblunt/diglibrary/diglibrary
diglibrary
```

## The first line, and why it is there

Homebrew will not load a formula from a tap it does not know, and **it is right
not to**: a formula is a stranger's Ruby about to run on your machine. Without
that line the second one stops with `Refusing to load formula … from untrusted
tap`.

So read the formula before you trust it — it is one short file,
[`Formula/diglibrary.rb`](Formula/diglibrary.rb), and it does nothing but build
a virtualenv and install the same package the Python index serves. If you would
rather weigh the project first, that is written up too:
[how to check any of this yourself](https://cankblunt.github.io/diglibrary/verify.html).

The second line taps and installs in one go, so there is no separate `brew tap`.

## What it brings

`ffmpeg` arrives as a dependency, which is the point of installing it this way:
it is not a Python package, so nothing `pip` or `pipx` can do will bring it, and
it is what the Quality screen measures with. Nothing has to be reopened
afterwards either — the command is on your path when the install returns.

`chromaprint` is optional and deliberately not a dependency; it is needed only
for identifying an album by its sound. Add it when you want that:

```sh
brew install chromaprint
```

## Installing by name instead

`pipx install diglibrary` works and is the same application — it is the route
the front page gives, because it asks you to trust nobody. The
[three-line walkthrough](https://github.com/cankblunt/diglibrary#getting-started)
starts from a Mac with nothing installed on it.

## About this repository

The formula here is a copy. It is written, reviewed and versioned in the
application's own repository under `packaging/homebrew/`, and a release refuses
to go out if the two have drifted apart.
