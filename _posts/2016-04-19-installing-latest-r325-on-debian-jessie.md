---
layout: post
title: "Installing latest R(3.2.5) on Debian Jessie"
description: ""
category: 
tags: []
---
{% include JB/setup %}

Installing R on Ubuntu/Debian is quite painful, especially when you want to install the latest version. I have no clue why this situation stills for a long time, but this is a way to work around.

On terminal:

```bash
# Appends the CRAN repository to your sources.list file 
# You could replace jessie-cran3 by the newer one
# Find the correct value at https://cloud.r-project.org/
sudo sh -c 'echo "deb http://cran.rstudio.com/bin/linux/debian jessie-cran3/" >> /etc/apt/sources.list'

# Adds the CRAN GPG key, which is used to sign the R packages for security.
sudo apt-key adv --keyserver subkeys.pgp.net --recv-key 381BA480
sudo apt-get update
sudo apt-get install r-base r-base-dev
```

Installing [h2o](h2o.ai):

```bash
# to retrieve curl-config
# otherwise you may have a problem with RCurl
sudo apt-get install libcurl4-gnutls-dev
```

```R
install.packages ("h2o")
```
