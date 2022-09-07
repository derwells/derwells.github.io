---
title: "Tree Crown Detection using FCOS"
excerpt: "Tests the feasibility of using FCOS over RetinaNet on the <a href='https://zenodo.org/record/3765872'>NEON Tree Crowns Dataset</a>. Built on top of the <a href='https://deepforest.readthedocs.io/'>DeepForest package</a>."
teaser: "/images/crownns-merged-bboxes.png"
collection: projects
share: False
---

DeepForest is a Python package for training, evaluating, and using tree-crown detection models in airborne imagery. It's built on top of PyTorch and uses a pre-trained RetinaNet (with a ResNet backbone).

CrowNNs is a quick study on extending the DeepForest library to accommodate other pre-trained object detection models.

Right now, the only new model is FCOS.

## Why FCOS?

RetinaNet is known for introducing a loss function that can better identify densely-packed objects. FCOS, which was released a few years after RetinaNet, uses that same loss function.

## Results

![](/images/crownns-sample.png)

|                     | Precision | Recall |
|---------------------|-----------|--------|
| CrowNNs FCOS        | 0.64      | 0.43   |
| DeepForest          | 0.66      | 0.79   |
| lidR Package (2016) | 0.34      | 0.47   |

Just like DeepForest, training and evaluation are done on the NEON Tree Crowns Dataset. Results are from training on an NVIDIA 1660 Super. 


## Insights

![](/images/crownns-merged-bboxes.png)

- A lot of errors from merged bounding boxes
- Model detects objects that look almost like trees from above (i.e. shrubs)
- Model worked much better in select forest sites

## Source code

Refer to [this repo](https://github.com/derwells/crowNNs).
