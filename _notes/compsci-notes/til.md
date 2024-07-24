---
title : today i learned
feed: show
date : 24-07-2024
tags: 
summary: Several stuff I learned and does not belong to a specific category. Basically a dump
---

- Go has runtime and garbage collection overhead. Data structures, slices, maps, and other objects may use more memory than their raw data size. 
    - This could be why I was exceeding the memory limit when trying to process 200K records.

- heap: a sampling of memory allocations of live objects, monitor current memory usage
    basically this is where OS stores the objects that are used by the program, it later gets garbage collected

-  `os.Open()` does not load the entire file into memory. It only opens the file and provides a file descriptor (*File) that allows you to read from or write to the file. This is for Go, but probably other languages have similar implementations.
