---
layout: post
title: "Auto install required packages in R"
description: ""
category: 
tags: [R]
---
{% include JB/setup %}

apt-get install libssl-dev openssl

There are more than one way to do that. The naive way could be

```r
if (!require (package_name)) {
	install.packages (package_name)
}
library (package_name)
```

or you can do more nicely with the package ``pacman``

```r
if (!require("pacman")) install.packages("pacman")
pacman::p_load (package_1, package_2, package_2)
```

However, in Debian Jessie, you will need to install two libraries beforehand

```bash
sudo apt-get install libssl-dev openssl
```

Otherwise the installation of ``pacman`` might face to an error.