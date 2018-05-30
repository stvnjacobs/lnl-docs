---

# Linode Docs
## Contributing Fixes and New Documentation

[https://linode.com/docs](https://linode.com/docs/)

---

## Installing Dependencies

```
$ brew install hugo
```

[Installation docs](https://gohugo.io/getting-started/installing)

+++

## Maintaining your own version

1. Fork the repository
2. Clone your forked repository
```sh
$ git clone git@github.com/$user/docs.git
```

---

## Start the Local Development Environment

```
$ cd docs
$ hugo server
```

---

## Project Layout

```
$ git clone git@github.com:stvnjacobs/docs.git
Cloning into 'docs'...
remote: Counting objects: 43115, done.
remote: Compressing objects: 100% (28/28), done.
remote: Total 43115 (delta 25), reused 21 (delta 14), pack-reused 43073
Receiving objects: 100% (43115/43115), 293.67 MiB | 8.74 MiB/s, done.
Resolving deltas: 100% (29522/29522), done.
Checking out files: 100% (3355/3355), done.
```
```
$ cd docs/
$ git remote add upstream git@github.com:Linode/docs.git
$ git remote -v
origin	git@github.com:stvnjacobs/docs.git (fetch)
origin	git@github.com:stvnjacobs/docs.git (push)
upstream	git@github.com:Linode/docs.git (fetch)
upstream	git@github.com:Linode/docs.git (push)
$ git pull upstream master
```

```
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

## Project Layout
```
~/.../Linode/docs $ exa -TFraL1
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

## Submitting a Fix

## Creating a New Post

```
$ exa -TFraL1 archetypes/
archetypes/
├── default.md
└── content.md
```
