# Utility Scripts

Sometimes it's useful to have scripts that do some tedious process. This is my dumping ground for
those. Often it's as simple as a zsh function or a small wrapper around a complicated command whose
syntax I will never get right on the first try.

I make some pretty big assumptions about things like API keys being set, dependencies being
installed, and generally that the computer is setup like mine. This is only public because it might
be a helpful thing to reference.

## init_repo

* Setup a version controlled folder. Both a local folder and a remote on Github. Run it without
  arguments to apply to the current folder. The repository name is determined by this priority
  order:

  1. The `--name` argument if specified
  2. The directory argument's basename if a directory path is specified
  3. The current directory's basename if neither above is specified

  You can specify `--public` to make it a public repository; otherwise `--private` is the default.
