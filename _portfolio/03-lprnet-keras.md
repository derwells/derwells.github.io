---
title: "Keras Implementation of LPRNet"
excerpt: "Implemented the <a href='https://arxiv.org/abs/1806.10447'>LPRNet paper</a> as a capstone project."
collection: projects
share: False
---

[LPRNet](https://arxiv.org/abs/1806.10447) is a neural network for Automatic License Plate Recognition (ALPR) on small, edge devices. As an exercise and a capstone for finishing Chollet's [DLWP](https://tanthiamhuat.files.wordpress.com/2018/03/deeplearningwithpython.pdf), I tried implementing the LPRNet paper using Keras. In addition, Keras can compile to TFLite, making it suitable for edge deployments.

To keep the project short, I validated my implementation by ensuring it learns on the CCPD-Base dataset (smaller subset of the paper's dataset)Training was done on a single NVIDIA 1660 Super.

## Source code

Check out [this repo](https://github.com/derwells/LPRNet).
