---
title : "docker cheat sheet"
feed: show
date : 26-07-2024
tags: [docker, container]
summary: Docker cheat sheet
---

**Work In Progress**

**build an image from a Dockerfile**

```bash
docker build -t <image-name> <path-to-dockerfile>
```

**run container**

```bash
docker run <image-name>
```


**limit memory usage**

`--memory=,`, `-m` → Sets a hard limit to the maximum physical memory a container can utilize (with a minimum of 6 MB).

The value of memory-limit should be a positive integer followed by the suffix b, k, m, or g (short for bytes, kilobytes, megabytes, or gigabytes).

```bash
docker run -m 300M myimage:1.0
```

**give environment variable**
    
    ```bash
    docker run -e MYVAR=foo myimage:1.0
    ```

