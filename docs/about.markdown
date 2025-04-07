---
layout: page
title: Benchmark
permalink: /benchmark/
nav_order: 1
---
# 🏆 Leaderboard

<div class="leaderboard-container">
  <table class="leaderboard">
    <thead>
      <tr>
        <th>Date</th>
        <th>Organization</th>
        <th>Model</th>
        <th>Site</th>
        <th>Score</th>
        <th>Video</th>
      </tr>
    </thead>
    <tbody>
        <tr>
            <td>YYYY-MM-DD</td>
            <td>Example Lab</td>
            <td>Example Model</td>
            <td><a href=" " target="_blank">🔗</a></td>
            <td>000</td>
            <td><a href=" " target="_blank">📽️</a></td>
        </tr>
      
        <tr>
            <td>YYYY-MM-DD</td>
            <td>Example Lab</td>
            <td>Example Model</td>
            <td><a href=" " target="_blank">🔗</a></td>
            <td>000</td>
            <td><a href=" " target="_blank">📽️</a></td>
        </tr>

        <tr>
            <td>YYYY-MM-DD</td>
            <td>Example Lab</td>
            <td>Example Model</td>
            <td><a href=" " target="_blank">🔗</a></td>
            <td>000</td>
            <td><a href=" " target="_blank">📽️</a></td>
        </tr>

        <tr>
            <td>YYYY-MM-DD</td>
            <td>Example Lab</td>
            <td>Example Model</td>
            <td><a href=" " target="_blank">🔗</a></td>
            <td>000</td>
            <td><a href=" " target="_blank">📽️</a></td>
        </tr>
    

    </tbody>
  </table>
</div>

# Challenge Overview

The current goal of automated proofreading is a difficult challenge involving many distinct, intermediate skills. In the interest of facilitating fully autonomous proofreading, we have prepared a series of intermediate challenges that incorporate essential skills for proofreading.

For each sub-challenge, training can be performed on the publicly available data hosted on Flywire. Submissions are currently being evaluated manually; we hope to develop an automated framework for leaderboard submission soon. Please reach out to [raphael_levisse@berkeley.edu](mailto:raphael_levisse@berkeley.edu), [kp0374@princeton.edu](mailto:kp0374@princeton.edu) and [dl2635@princeton.edu](mailto:dl2635@princeton.edu) for additional information.

Submissions will be evaluated on private data not made available to the public.

## Sub-Challenge 1: Navigation

Sub-Challenge 1 is a navigational task: to **achieve the highest z-position for a given neuron**. Your agent, when initialized at an arbitrary XYZ-position on a random neuron, should be able to navigate (via clicking, keyboard interactions, etc.) to the top z-position of the neuron. 

## Evaluation Criteria
- Rotational invariance
    - *Can the highest z-position be obtained regardless of initial angular orientation of the z-axis?*
- Depth understanding
    - *Can your agent successfully identify the highest z-position in visually ambiguous situations?*
- Speed
    - *How efficient is your agent at navigating?*

## Demonstrations

<video width="600" autoplay loop muted playsinline controls preload="auto" style="max-width: 100%; height: auto;" onerror="console.error('Video error:', this.error);">
  <source src="../media/videos/example_high_z.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
***An example of reaching highest z-position.***