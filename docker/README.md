# Using docker to record movies

You can use a [docker] container with [asciinema-player] as a server for
asciinema2gif.


## Setting up the container

Requirements:
- docker

To create the container, run the following command inside this directory:

    docker build -t asciinema2gif .

You only have to do that once.


## Using the container

Call:

    asciinema-player-container <json file> [asciinema2gif parameters]

The script will start the container serving the provided recording,
run *asciinema2gif* with the given parameters and then stop the container.


[docker]: https://www.docker.io/
[asciinema-player]: https://github.com/asciinema/asciinema-player
