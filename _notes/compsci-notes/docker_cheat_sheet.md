---
title: "docker cheat sheet"
feed: show
date: 26-07-2024
tags: [docker, container]
summary: Docker cheat sheet
---

**Work In Progress**

### build an image from a Dockerfile

```bash
docker build -t <image-name> <path-to-dockerfile>
```

### run container

```bash
docker run <image-name>
```

#### some run flags

- Flags come first, followed by the image name

- `--rm` **remove container after it exits**

  Automatically remove the container when it exits.

- `-it` **interactive terminal**

  Run the container in interactive mode. This flag is used to keep the container running and open a terminal to interact with it.

- `-m` **limit memory usage**

  Set a hard limit to the maximum physical memory a container can utilize (with a minimum of 6 MB).

  The value of memory-limit should be a positive integer followed by the suffix b, k, m, or g (short for bytes, kilobytes, megabytes, or gigabytes).

- `-e` **set environment variables**
  Set an environment variable in the container. \
   `docker run -e MYVAR=foo`

- `-v` **bind mount a volume**

  Bind mount a volume to the container. \
   `docker run -v /host/path:/container/path`
