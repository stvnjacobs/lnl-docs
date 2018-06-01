---

# Linode Docs
## Contributing Fixes and New Documentation

https://linode.com/docs/

---

The Linode Docs currently have a total of

  **1011**

articles at the time of me writing this.

The topics covered include:
- The Linode platform
- Software targeted at Linux servers
- Deployment tools

Note:
and more

---

## Ways to contribute

_from easiest to hardest_

- Correct typos and silly mistakes
- Update existing docs with better alternatives
- Write a doc

---

## Getting everything in order

- The Linode Docs are incredibly easy to get up and running yourself

_Warning: There is going to be some git._

+++

### Step 1

#### Fork the repository

![Github Fork Button](http://static.stj.io/img/lnl-docs-fork.png)

+++

### Step 2

#### Clone your forked repository

```txt
$ git clone git@github.com:stvnjacobs/docs.git
Cloning into 'docs'...
remote: Counting objects: 43115, done.
remote: Compressing objects: 100% (28/28), done.
remote: Total 43115 (delta 25), reused 21 (delta 14), pack-reused 43073
Receiving objects: 100% (43115/43115), 293.67 MiB | 8.74 MiB/s, done.
Resolving deltas: 100% (29522/29522), done.
Checking out files: 100% (3355/3355), done.
```

@[1]

+++

### Step 3

#### Add the Linode Docs repo as a remote repository


```txt
$ cd docs/

$ git remote add upstream git@github.com:Linode/docs.git
```

@[1]
@[3]

This will allow you to pull in changes made to the main repository.

Note:
Git is set up to be a distributed system.

GitHub just happens to be the "main source of truth" for Linode's docs repo.

By forking the repository, you have created your own copy, hosted on GitHub.

By cloning your fork, you are replicating that copy to your local computer.

But to make changes to our docs, all changes will need go through the Linode/docs repository.

By adding a "remote", we are letting git know that there is another copy of the repository.

We can pull in any changes that are made this repository.

Upstreap is only a convention.

+++

### Confirmation

You can confirm that `Linode/docs` has been linked with the following:

```txt
$ git remote -v
origin	git@github.com:stvnjacobs/docs.git (fetch)
origin	git@github.com:stvnjacobs/docs.git (push)
upstream	git@github.com:Linode/docs.git (fetch)
upstream	git@github.com:Linode/docs.git (push)

$ git pull upstream master
```

@[1](List linked remote repositories.)
@[2-5]
@[7](`Already up to date.`)

Note:
Unless someone made a change in the last few minutes, since you configured the remote,
the `git pull upstream master` should return `Already up to date.`

---

## Project Layout

```txt
./
├── themes/
├── README.md
├── netlify.toml
├── docs/
├── CONTRIBUTING.md
├── content -> docs
├── config.toml
├── CODE_OF_CONDUCT.md
├── ci/
├── archetypes/
├── .vale.ini
├── .travis.yml
├── .gitignore
└── .git/
```

@[5,7]
@[10]
@[11]

---

## docs/

- Contains all the content files used to compose our documentation.

If you are creating a new doc, or editing an existing one, this is where you will be working from.

Note:
Open the GitHub link and show the docs folder

https://github.com/linode/docs/tree/master/docs

https://github.com/linode/docs/blob/master/docs/applications/big-data/big-data-in-the-linode-cloud-streaming-data-processing-with-apache-storm.md

https://linode.com/docs/applications/big-data/big-data-in-the-linode-cloud-streaming-data-processing-with-apache-storm/

We are jumping to archetypes, and skipping CI.
We have to write a post first.

---

## archetypes/

Hugo has what they call archetypes.

They are pre-formatted "templates" for various kinds of posts.

Note:
We only write docs, so there isn't much variation, here.

What it gives us, though, is uniformity.

It also let's us set a standard for what metadata is required for new docs.

Show the frontmatter

https://github.com/linode/docs/tree/master/archetypes

+++

### Frontmatter

```yaml
author:
    name: Karthik Shiraly
    email: docs@linode.com
description: 'Deploy Storm cluster on Linode cloud for real-time analytics on streaming datasets.'
keywords: ["storm", "analytics", "big data", "zookeeper"]
license: '[CC BY-ND 4.0](http://creativecommons.org/licenses/by-nd/4.0/)'
published: 2016-10-25
modified: 2017-06-21
modified_by:
    name: Phil Zona
title: 'Big Data in the Linode Cloud: Streaming Data Processing with Apache Storm'
contributor:
    name: Karthik Shiraly
    link: https://github.com/pathbreak
external_resources:
- '[Apache Storm project website](http://storm.apache.org/)'
- '[Apache Storm documentation](https://storm.apache.org/releases/current/index.html)'
- '[Storm - Distributed and Fault-Tolerant Real-time Computation](http://www.infoq.com/presentations/Storm-Introduction)'
image: https://www.linode.com/docs/assets/big_data_linode_cloud.png
```

https://raw.githubusercontent.com/linode/docs/master/docs/applications/big-data/big-data-in-the-linode-cloud-streaming-data-processing-with-apache-storm.md

@[1-3](Author data)
@[4](A short description)
@[1-19]

Note:
Not pictured
- Front matter is seperated by `---`
---

## Post Layout

A post is laid out into two main parts.

- Front matter (meta infomration)
- Content


Note:
Create a post

---

### ci/

The Linode Docs have a test suite that is run as part of a continuous integration pipeleine.
It test for thing such as:
- Presence of required metadata
- File naming and formatting conventions
- Ensuring there are no broken links
- Ensuring there all linked images are present


```txt
$ git branch
* master

$ git fetch upstream

$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/config/smart-fractions
  remotes/origin/fix/postgres-pgadmin-link
  remotes/origin/master
  remotes/upstream/cwlinode-patch-1
  remotes/upstream/freebsd_minecraft
  remotes/upstream/install-nginx-ubuntu
  remotes/upstream/master
  remotes/upstream/migrate
  remotes/upstream/nginx-basic-graphic
```

@[1]
@[2]
@[4]
@[6]
@[7]
@[8-11]
@[12-17]

---

## Installing Dependencies

```txt
$ brew install hugo
```

[Installation docs](https://gohugo.io/getting-started/installing)

## Start the Local Development Environment

```txt
$ cd docs
$ hugo server
```

---

## Submitting a Fix

---

### Small Fixes and Typos

![Docs Header Edit Link](http://static.stj.io/img/lnl-docs-edit-link.png)

---

## Creating a New Post

```txt
archetypes/
├── default.md
└── content.md
```
