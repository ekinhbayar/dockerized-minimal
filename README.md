## Dockerized Minimal theme

This repository contains an nginx Dockerfile and the Minimal Jekyll theme for GitHub Pages, to be served by self hosting it with Docker.

### Installation

- Pull the repository:

```
git clone https://github.com/ekinhbayar/dockerized-minimal.git
```

- Modify `_config.yml`

### Usage

- Run:

```
docker run --rm \
        -v "$(pwd):/src" \
        -w /src \
        ruby:2.3 \
        sh -c 'bundle install \
            --path vendor/bundle \
            && exec jekyll build --watch'
```

- Check if all is well in `/web` then build the docker image:

```
docker build -t blog-title .
```

- Serve:

```
docker run -d \
        -p 80:80 \
        -v "$(pwd)/web:/usr/share/nginx/html" \
        blog-title

```

- Profit!


---

#### To Do
- Improve external links
- Travis
- gemspecs
