---
title: "docker cheat sheet"
feed: show
date: 26-07-2024
tags: [docker, container]
summary: Docker cheat sheet
---

**Work In Progress**

#### build an image from a Dockerfile

```bash
docker build -t <image-name> <path-to-dockerfile>
```

#### run container

```bash
docker run <image-name>
```

**flags for run**

`--rm` : Automatically remove the container when it exits.

`-it` : Interactive mode

`-m` : Limit memory usage \
Set a hard limit to the maximum physical memory a container can utilize (with a minimum of 6 MB). \
The value of memory-limit should be a positive integer followed by the suffix b, k, m, or g (short for bytes, kilobytes, megabytes, or gigabytes).

`-e` : Set an environment variable in the container. \
`docker run -e MYVAR=foo`

`-v` : Bind mount a volume to the container.
`docker run -v /host/path:/container/path`
