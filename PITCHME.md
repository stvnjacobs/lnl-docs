---

# Linode Docs
## Contributing Fixes and New Documentation

https://linode.com/docs/

---

The Linode Docs currently total 1011 at the time of writing.

```txt
$ find . -type f -name '*.md' | grep -v '_index.md' | wc -l
1011
```


---

## Maintaining your own version

### Step 1

#### Fork the repository

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

+++

### Step 3

#### Add the Linode Docs repo as a remote repository

This will allow you to pull in changes made to the main repository.

```txt
$ cd docs/

$ git remote add upstream git@github.com:Linode/docs.git
```

You can confirm this with the following:

```txt
$ git remote -v
origin	git@github.com:stvnjacobs/docs.git (fetch)
origin	git@github.com:stvnjacobs/docs.git (push)
upstream	git@github.com:Linode/docs.git (fetch)
upstream	git@github.com:Linode/docs.git (push)

$ git pull upstream master
```

+++

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

+++

### docs/

This directory contains all the content files that are used to compose our documentation.
If you are creating a new doc, or editing an existing one, this is where you will be working from.

+++

### archetypes/

Hugo has what they call archetypes.


+++

### ci/

The Linode Docs have a test suite that is run as part of a continuous integration pipeleine.
It test for thing such as:
- Presence of required metadata
- File naming and formatting conventions
- Ensuring there are no broken links
- Ensuring there all linked images are present

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
$ exa -TFraL1 archetypes/
archetypes/
├── default.md
└── content.md
```
