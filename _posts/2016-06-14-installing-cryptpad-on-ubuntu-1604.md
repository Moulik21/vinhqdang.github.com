---
layout: post
title: "Installing Cryptpad on Ubuntu 16.04"
description: ""
category: tutorial
tags: [ubuntu,cryptpad,collaborative editing]
---
{% include JB/setup %}

# Introduction

Cryptpad is an open-source real-time collaborative editing service, which is available at [https://github.com/xwiki-labs/cryptpad]()

# Installation

In order to install Cryptpad on Ubuntu 16.04, you need to install:

1. [NodeJS](https://nodejs.org/en/)
2. [MongoDB](https://www.mongodb.com/download-center#community)
3. Cryptpad

## Install NodeJS

The tutorial of installing NodeJS via package manager is available at [https://nodejs.org/en/download/package-manager/](). However, after installing, you might be noticed that Ubuntu does not recognize ``node`` command.

```{bash}
node --version
node: command not found
```

If you are sure that ``nodejs`` is installed, you could do

```{bash}
which nodejs
/usr/bin/nodejs

# link nodejs as node
sudo ln -s /usr/bin/nodejs /usr/bin/node
```

## Install MongoDB

You could follow [this instruction](https://rohan-paul.github.io/mongodb_in_ubuntu/2015/09/03/How_to_Install_MongoDB_Iin_Ubuntu-15.04.html). Note that, at the time of writing, following the instruction will let you own MongoDB 3.0.12, not the latest one.

After installing MongoDB, you could follow [my old blog post](http://vinhdq.blogspot.fr/2014/12/getting-started-with-cryptpad-in-ubuntu.html) to add collection and user to MongoDB.

## Install cryptpad

Just follow the instruction at [homepage of Cryptpad](https://github.com/xwiki-labs/cryptpad) to install cryptpad. In my case, ``bower`` is required.

After installed Cryptpad, you should modify the ``config.js`` file:

- comment two lines which start with ``storage: './storage/.lvl',`` and ``levelPath: ..``
- uncomment the line ``storage: './storage/mongo',``
- uncomment the line ``mongoCollectionName: 'cryptpad',``
- uncomment and modify the line start with ``mongoUri :`` as instructed in the above mentioned blog post.
- In command line, type ``npm install mongodb``
- In command line again, ``node ./server.js``
- Now, point your browser to ``localhost:3000``


It should be done like this.
