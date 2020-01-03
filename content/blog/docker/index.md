---
title: How I learned to Stop Worrying and Love Docker
date: "2020-01-01T22:12:03.284Z"
description: "Sometimes it's a lot easier than it looks"
---

You've done it. You successfully built your backend!
This is the part where you tell yourself to forget about how you _built_ the damn thing and focus on the UI.

In reality, the mentality of taking anything for _granted_ with a build process is a promise waiting to be broken. In the case of going down the [happy path](https://en.wikipedia.org/wiki/Happy_path) it becomes easy to forget that your package manager is out of date, that you switched to Node 9.x via NVM that _one_ time, or that you're on a completely different machine now.

Some questions you might be asking yourself when going back to an old project.

- How do I avoid worrying about a reproducing a production build environment again when working on local?

- Can I **isolate** my build issues and resolve them before sharing code?

- How do I ensure that anyone working with me is on the same environment when they pull/fork?

These might be doubts in your head before you take that next step forward before pushing your code but tools such as [Docker](<https://en.wikipedia.org/wiki/Docker_(software)>) can abstract most of that for you.

By the end of this we should be able to create a database, generate a schema, seed the DB, initialize our server, and run PGAdmin to connect it all through a single Docker command.

**Sounds pretty neat so what do I need to know?**

First thing that you're going to want to do is [install docker](https://docs.docker.com/install/). Your instructions might differ depending on which OS you're on. Once that's done, in your terminal type:

`docker version`

you should see something like this:

![docker-version](./docker-version.png)

Docker itself is a broad topic to properly cover so for the sake of brevity and the scope of this post we'll be distilling things down to: [images](https://docs.docker.com/engine/reference/commandline/images/), [Dockerfiles](https://docs.docker.com/engine/reference/builder/) and [docker-compose](https://docs.docker.com/compose/).

For a higher level overview on Docker here's an excellent [article](https://towardsdatascience.com/learn-enough-docker-to-be-useful-b7ba70caeb4b) by [Jeff Hale](https://twitter.com/discdiver) that helps abstract some of the notions about Docker.

## So whats image anyway?

The easiest way to understand what an image is, is to go ahead and type `docker run hello-world` in your terminal. You should be prompted with the following:

![hello-world](./hello-world.png)

Most of this is looks like useless information but in reality there's a couple of key concepts being handed to us here.

```
To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.
```

<!--
So how do you avoid running into these issues? Forget that, how do you ensure that anyone working with you can avoid these issues? The problem with environments is that they are _broad_ problems and developers seek **isolation**.

In this post I want to talk about Docker, a tool for breaking your app into small containers. -->
