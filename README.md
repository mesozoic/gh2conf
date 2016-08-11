# gh2conf (GitHub-to-Confluence)

A script for publishing a GitHub wiki repository to Confluence.

Assumes you're using Markdown. Does not support other formats yet.

## Quickstart

```
$ pip install gh2conf
$ git clone git@github.com:your/project.wiki.git
$ cd project.wiki
$ vim .gh2conf.yaml
$ python -m gh2conf
```

## Sample Configuration

```yaml
confluence:
  url: https://confluence.yourcorp.com
  username: gh2conf
  password: gh2conf  # if missing, will prompt the user

project:
  # set some defaults for the target space/page
  target:
    space_key: HOWTO
    parent_title: 'User Manual'
  # gh2conf will copy each file in the order you specify
  steps:
    - filename: Home.md
      target:
        parent_title: ''      # empty string means write to space root
        title: 'User Manual'  # this will be the parent page for the others
    - filename: Other-Page.md
    - filename: Yet-Another-Page.md
```
