---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
title: Motivation
permalink:
nav_order: 0
---
# 🧠 Overview

A connectome is a comprehensive map of neural connections in the brain. Significant interest lies in being able to automatically collect full connectomes; accurate and full wirings would facilitate neuroscience research that could improve society's general understanding of brain functionality, with broad ramifications for advancing healthcare and technology.

![Ring neurons](../media/images/connectome.jpg)
***Ring neurons in a fruit fly brain.***

The pipeline to obtain full connectomes (brain wirings) has been steadily approaching full automation. Current SOTA procecsses involving obtaining images of the brain by electron microscopy, which are processed by segmentation models to then build comprehensive 3D models of individual neurons. However, despite the superhuman precision of said models, their outputs of the reconstructed neurons bear errors.

At the [Seung lab](https://seunglab.org/), teams of human proofreaders **manually** find these errors on the connectome of a female Drosophila and correct them through a web interface called Neuroglancer, which allows for both 3D and 2D cross-section visualization of neuron data.

<video width="600" autoplay loop muted playsinline controls preload="auto" style="max-width: 100%; height: auto;" onerror="console.error('Video error:', this.error);">
  <source src="../media/videos/video_1_proofreading.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
***An example of proofreading.***

This is **unscalable**. Proofreaders must tediously analyze the local structure and global context of neurons to assess for errors (typically an accidental merging of neurons or separation of an individual neuron). Even for smaller connectomes, such as that of the female Drosophila, this proves to be a monumental task.

We need **Agents** capable of making human-level observations as well as decisions and applying them through Neuroglancer onto the neurons to help our team. This is no easy task - proofreading aside, the Neuroglancer environment is a challenge to successfully understand and utilize due to its many dynamic visual inputs. While the overall goal is fully automated proofreading, there are several intermediate challenges that agentic approaches must address such as efficiently navigating through neurons, finding errors, and finding synapses, amongst others.

The [Seung lab](https://seunglab.org/)   is opening up this challenge - to develop a proofreading agent - to the general public. In the interest of facilitating development in this field, we have [prepared code](https://github.com/seung-lab/ngl_bench/) that allows for smooth interaction with Neuroglancer, as well as set up a benchmark with a series of challenges leading up to the final end goal of full proofreading.

Happy proofreading!