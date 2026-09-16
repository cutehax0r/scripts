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

## init_ruby

* Installs a specific Ruby version via `ruby-build` and then installs a set of standard
  gems. Requires `ruby-build` and `chruby` to be installed.

  Usage: `init_ruby [OPTIONS] VERSION`

  Example: `init_ruby 4.0.0` installs Ruby 4.0.0 to `~/.local/share/ruby/4.0.0`
  and installs common gems (rake, pry, sorbet, minitest, rspec, rubocop, rails, etc.).

## demono

* Converts a video or audio file's audio track to mono. If one channel is clearly
  silent or just noise (e.g. you recorded with a single microphone plugged into one
  input of an audio interface), that channel is dropped and the other is used
  as-is; otherwise a standard downmix is performed. Video streams are copied
  untouched. Requires `ffmpeg`/`ffprobe`.

  Usage: `demono [OPTIONS] INPUT OUTPUT`

  Example: `demono screenrec.mp4 screenrec_mono.mp4` makes a copy of `screenrec.mp4` but with the
  loudest track set as the only mono audio channel. The new file is named `screenrec_mono.mp4`.
