FROM nginx:stable-alpine

RUN apk add --update --no-cache openssl

WORKDIR /usr/share/nginx/html
RUN set -x -e; \
    version=2.4.0; \
    wget \
        https://github.com/asciinema/asciinema-player/releases/download/v$version/asciinema-player.css \
        https://github.com/asciinema/asciinema-player/releases/download/v$version/asciinema-player.js; \
    mkdir -p api/asciicasts asciicast;

RUN echo '<html>' \
         '<head><link rel="stylesheet" type="text/css" href="/asciinema-player.css" /></head>' \
         '<body>' \
         '<asciinema-player src="/asciicast/asciicast.json"></asciinema-player>' \
         '<script src="/asciinema-player.js"></script>' \
         '</body>' \
         '</html>' > api/asciicasts/index.html

EXPOSE 80

CMD ["nginx","-g","daemon off;"]

# Building the container:
# docker build -t asciinema2gif .

# Usage:
# - Start the container:
#   docker run -d --rm -p 3080:80 -v $PWD:/usr/share/nginx/html/asciicast --name asciinema2gif asciinema2gif
# - Run asciinema2gif:
#   asciinema2gif http://127.0.0.1:3080/api/asciicasts/
# - Stop the container
#   docker stop asciinema2gif

