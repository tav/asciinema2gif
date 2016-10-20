## asciinema2gif

Generate animated GIFs from [asciinema terminal recordings].

![Demo](http://tav.espians.com/asciinema/demo.gif)

### Motivation

The [`asciinema`] tool is a wonderful way to record and share terminal sessions.
Unfortunately, it's not [currently possible] to embed the output in places like
README files on GitHub repos. This tool provides a solution for that.

### Usage

```bash
asciinema2gif [options] <asciinema_id|asciinema_api_url>

  options:
    -s <size>, --size <size>      One of 'small', 'medium', 'big'
    -p <speed>, --speed <speed>   Any integer (whole number) to multiply regular speed by
    -t <theme>, --theme <theme>   One of 'asciinema', 'tango', 'solarized-dark', 'solarized-light', 'monokai'
    -o <file>, --output <file>    File to write to (defaults to 'asciicast.gif' in current directory)
    -h, --help                    Show this help.
```

Examples:

```bash
$ asciinema2gif --size small --speed 2 --theme solarized-dark 8332
```

An `asciicast.gif` file will then be generated for you to embed and share.

```bash
$ asciinema2gif --theme solarized-light -o "${HOME}/Desktop/another.gif" https://asciinema.org/api/asciicasts/8332
```

In this case an `another.gif` file will be generated on your Desktop. Using the full URL is useful if you want to get an asciicast not from the official website.

#### URL Format

`asciinema2gif` works by visiting the given webpage, starting the asciicast, screenshotting it repeatedly, and finally stitching it together. The `/api/asciicasts/` format of an asciinema website (e.g. https://asciinema.org/api/asciicasts/8332), as opposed to the main `/a/` format (e.g. https://asciinema.org/a/8332), makes this operation easier (see [usage](#usage)), hence why it is a requirement.

### Requirements

#### OS X

```bash
# Requires Homebrew installed. Find it at http://brew.sh/.
# This command will install asciinema2gif and all dependencies.
brew install asciinema2gif
```

#### Ubuntu

```bash
apt-get install imagemagick gifsicle npm
npm install --global phantomjs2
```

### Credits

* [@blueyed], Daniel Hahler
* [@iblech], Ingo Blechschmidt
* [@tav]
* [@VojtechVitek], Vojtech Vitek
* [@wong2], Wang Dàpéng — **maintainer**
* [@vitorgalvao], Vítor Galvão

### License

Public domain.

—
Enjoy, tav <<tav@espians.com>>


[`asciinema`]: https://asciinema.org/
[asciinema terminal recordings]: https://asciinema.org/
[currently possible]: https://github.com/asciinema/asciinema.org/issues/152

[@blueyed]: https://github.com/blueyed
[@iblech]: https://github.com/iblech
[@tav]: https://github.com/tav
[@VojtechVitek]: https://github.com/VojtechVitek
[@wong2]: https://github.com/wong2
[@vitorgalvao]: https://github.com/vitorgalvao
