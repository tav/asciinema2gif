## asciinema2gif

Generate animated GIFs from [asciinema terminal recordings].

![Demo](http://tav.espians.com/asciinema/demo.gif)

### Motivation

The [`asciinema`] tool is a wonderful way to record and share terminal sessions.
Unfortunately, it's not [currently possible] to embed the output in places like
README files on GitHub repos. This tool provides a solution for that.

### Usage

```bash
asciinema2gif [options] <asciinema_number|asciinema_api_url>

  options:
    -s <size>, --size <size>      One of 'small', 'medium', 'big'
    -t <theme>, --theme <theme>   One of 'tango', 'solarized-dark', 'solarized-light'
    -o <file>, --output <file>    File to write to (defaults to 'asciicast.gif' in current directory)
    -h, --help                    Show this help.
```

Examples:

```bash
$ asciinema2gif --size small --theme solarized-dark 8332
```

An `asciicast.gif` file will then be generated for you to embed and share.

```bash
$ asciinema2gif --theme solarized-light -o "${HOME}/Desktop/another.gif" https://asciinema.org/api/asciicasts/8332
```

In this case an `another.gif` file will be generated on your Desktop. Using the full URL is useful if you want to get an asciicast not from the official website.

### Requirements

#### OS X

```bash
# requires Homebrew installed. Find it at http://brew.sh/
brew install imagemagick gifsicle phantomjs
```

#### Ubuntu

```bash
apt-get install imagemagick gifsicle npm
npm install phantomjs2
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
