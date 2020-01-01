---
title: How I learned to Stop Worrying and Love Docker
date: "2020-01-01T22:12:03.284Z"
description: "Sometimes we just need to forget"
---

You've done it. You successfully built your backend!
This is the part where you tell yourself to forget about how you _built_ the damn thing and focus on the UI.

In reality, the mentality of taking anything for _granted_ with a build process is a promise waiting to be broken. In the case of going down the [happy path](https://en.wikipedia.org/wiki/Happy_path) it becomes easy to forget that your package manager is out of date, that you switched to Node 9.x via NVM that _one_ time, or that you're on a completely different machine now. But everything is okay right now because you run your script and the server starts and **now** you have working code....

- How do you avoid worrying about a producing a production build environment while working on your local machine?

- How do you ensure that anyone working with you is on the same environment?

- Can you **isolate** your build issues and resolve them before sharing code?

These might be doubts in your head before you take that next step forward before pushing your code but tools such as [Docker](<https://en.wikipedia.org/wiki/Docker_(software)>) can abstract most of that for you.

By the end of this we should be able to create a database, generate a schema, seed a database, run our API, and run PGAdmin through a single Docker command.

Now this is all great but how do we go about automating this backend stuff with Docker?

<!--
So how do you avoid running into these issues? Forget that, how do you ensure that anyone working with you can avoid these issues? The problem with environments is that they are _broad_ problems and developers seek **isolation**.

In this post I want to talk about Docker, a tool for breaking your app into small containers. -->
