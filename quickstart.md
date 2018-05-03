---
title: MPEDS Quick Start
permalink: quickstart.html

---

MPEDS is distributed as a Docker container. To run it on your computer, you first need to download and install [Docker](https://www.docker.com). You'll also need to install [Git LFS](https://github.com/git-lfs/git-lfs/wiki/Installation), which allows you to download the large-file classifiers and vectorizers.


After that, clone or download the [Git repository](https://github.com/mpeds/mpeds), navigate to the directory in a terminal, and run `docker-compose run mpeds`

**Example code:**

```
git clone https://github.com/mpeds/mpeds.git
cd mpeds
docker-compose run mpeds
```

This will build and launch two linked Docker containers. The first contains the geotagging service [CLIFF](http://cliff.mediameter.org), which is used to extract information on locations mentioned in the articles. The second container is used to run the main MPEDS program.

The CLIFF container will normally take between 10 and 30 minutes to launch. The main MPEDS container will wait for the CLIFF container to be ready before it launches into a command line prompt. Once the container is ready, MPEDS can be run as a Python package.

To run an example script, type `python example-lexisnexis.py` into the command line prompt. This will generate a file `mpeds-output.csv` which identifies events which contain protest in an example Lexis-Nexis file, then generate data on a set of variables: form, issue, target, social movement organizations, locations, and size.
