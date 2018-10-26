<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Notebooks from Operação Serenata de Amor](#notebooks-from-opera%C3%A7%C3%A3o-serenata-de-amor)
  - [What](#what)
  - [How](#how)
    - [To read](#to-read)
    - [To download the datasets](#to-download-the-datasets)
    - [To collaborate](#to-collaborate)
  - [Reminder](#reminder)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Notebooks from [Operação Serenata de Amor](https://github.com/okfn-brasil/serenata-de-amor)

[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/okfn-brasil/notebooks/master?filepath=notebooks)

## What

[Operação Serenata de Amor](https://github.com/okfn-brasil/serenata-de-amor) has been acknowledged as a great AI project in Brazil and other countries. It has become not only a project to audit public expenses but also a space of sharing and collaboration. During its history, Serenata has had many people devoted to exploring its datasets through experimental notebooks which could possibly become a [Rosie](https://github.com/okfn-brasil/serenata-de-amor/blob/master/rosie/README.md)'s classifier.

These notebooks from multiple authors are rich assets from which people can learn about data science, Python third-party libraries and core functions, as well as gather ideas for their own investigations.

Notebooks have been removed from the main repo, but with this exploratory and educative mindset, the team republishes the notebooks in this repo, also re-opening the space for collaboration and learning. Make yourself at home, you can read notebooks and share your own.

## How

### To read

* You can clone this repo by typing on your console:

```
$ git clone https://github.com/okfn-brasil/notebooks.git
```

* Alternatively you can download all the notebooks clicking the green "Clone or download" button on your right and choosing "Download ZIP".

* Alternatively you can [launch in binder](https://mybinder.org/v2/gh/okfn-brasil/notebooks/master?filepath=notebooks).
> This provides a simple and disposable environment to run and visualize notebooks. Don't use that as your development environment and definitely don't add your credentials on this environment.

* Alternatively you can visualize the notebooks in `read only` mode [using a public version of nbviewer](https://nbviewer.jupyter.org/github/okfn-brasil/notebooks/tree/master/)

### To download the datasets

We use serenata toolbox to download or generate the datasets. To install and use the toolbox just checkout the [toolbox's guide](https://github.com/okfn-brasil/serenata-toolbox#serenata-de-amor-toolbox).

### Deploy in production with docker

#### Prepare Docker Images

- Create the docker images

```bash
docker build -t notebooks .
```

As we create the docker image, it will be stored in local docker images cache

- Tag the image to maintain th version of the docker image

```bash
docker tag notebooks notebooks:1.0
```

*NOTE: By default when we create the docker image its default tag is latest. 0.1 is the version for current release*

- Push docker image to dockerhub

```bash
# Syntax
docker tag notebooks DOCKERHUB_USER_NAME/notebooks:VERSION

# Example
docker tag notebooks okbr/notebooks:0.1

docker login

docker push okbr/notebooks:0.1
```

Now image is ready to deploy on any cloud with the `docker-compose.yml`

#### Deploy on any machine

```bash
docker login

docker pull okbr/notebooks:0.1

docker tag okbr/notebooks:0.1 notebooks

docker-compose up -d
```

*NOTE: Expected to have docker-compose file in the directory where we run above command*

### To collaborate

Fork this repo and clone it. Then commit a new branch with your notebook and PR us. The files will be reviewed by [@jtemporal](https://github.com/jtemporal) and [@rodolfo-viana](https://github.com/rodolfo-viana).

[If you are a newcomer or just confused about what to do, read `getting-started.md`.](https://github.com/okfn-brasil/notebooks/blob/master/getting-started.md)

Please remember to export a `.py` and `.html` to facilitate the review process. There's a sample config file at `notebooks/jupyter_notebook_config.py` to make Jupyter export these files automatically.

## Reminder

The notebooks are available here for educational purposes. So please do not feel ashamed of commenting every step of your analysis, ok? Overusing documentation is better than no documentation at all.
