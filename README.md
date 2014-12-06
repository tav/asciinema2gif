## asciinema2gif

Generate an animated GIF from [asciinema terminal recordings].

### Motivation

The `asciinema` tool is a wonderful way to record and share terminal sessions.  
Unfortunately, it's not [currently possible] to embed the output in places like  
README files on GitHub repos. This tool provides a solution for that.

### Usage

Simply pass in the corresponding API url for the recording, e.g.

```bash
$ ./asciinema2gif https://asciinema.org/api/asciicasts/8332
```

An `asciicast.gif` file will then be generated for you to embed and share.

The API url supports a few customisable parameters you might want to use:

* `?size=`: `small`, `medium`, `big`
* `?theme=`: `tango`, `solarized-dark`, `solarized-light`

### Requirements

**PhantomJS 2**

You need to have PhantomJS 2 installed since there are a number of bugs in  
PhantomJS 1.x:

* https://github.com/ariya/phantomjs/issues/10592
* https://github.com/ariya/phantomjs/issues/12181
* https://github.com/ariya/phantomjs/issues/12697

You can find relatively recent builds of PhantomJS 2 here:

* https://github.com/bprodoehl/phantomjs/releases

Make sure to place the binary on your `PATH` as `phantomjs2`.

**ImageMagick**

OS X:

```bash
$ brew install imagemagick
```

Ubuntu:

```bash
$ apt-get install imagemagick
```

**Gifsicle**

OS X:

```bash
$ brew install gifsicle
```

Ubuntu:

```bash
$ apt-get install gifsicle
```

### License

Public domain.

—  
Enjoy, tav <<tav@espians.com>>


[asciinema terminal recordings]: https://asciinema.org/
[currently possible]: https://github.com/asciinema/asciinema.org/issues/152