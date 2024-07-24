This repo contains my reading notes, code snippets, and other resources related to computer science. I am trying to keep it as organized as possible but please note that for now, it is a personal project and might not fit everyone's needs. Some notes can be Turkish, some can be English and some can be both. Some of them even uses a language that only I can understand. :D

This repo is live at [gecicidegisken.github.io/notes](https://gecicidegisken.github.io/notes)

## Note Structure
Every note has a front matter that contains metadata about the note. Here is an example front matter:
```
---
title : 
feed: show
date : 15-04-2021
tags: ["tag1", "tag2"]
---
```

- `title` : Title of the note
- `feed` : If you want to hide the note from the feed, set it to `hide`
- `date` : Date of the note in dd-mm-yyyy format


## Adding a note
- Add a new note in `_notes` folder. 

## Referencing a note
- You can reference a note by using the following syntax:
```
[[note.title]]
```

## Theme 
-  Thanks [Jekyll Garden](https://jekyll-garden.github.io/)

## Run locally

```bash
$ bundle install
$ bundle exec jekyll serve
```
