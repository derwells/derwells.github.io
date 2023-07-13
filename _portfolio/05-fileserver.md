---
title: "Multithreaded Fileserver in C from Scratch"
excerpt: "Built a multithreaded fileserver using the `pthread` library in C. Served as the capstone project for my operating systems class."
collection: projects
share: False
---

As per project specs, each command has an associated worker thread. Worker threads are grouped by their target filepath `<path>`. Worker threads in a group are organized using hand-over-hand locking. This ensures that older threads in a group must run first before newer threads can.

![](/images/fileserver-idea.png)

## Source code

Check out [this repo](https://github.com/derwells/multithreaded-fileserver).
