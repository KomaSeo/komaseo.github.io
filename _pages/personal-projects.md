---
layout: page
title: Personal projects
permalink: /personal-projects/
description: Tools I built for myself and my friends. We implemented and used these tools for ourselves.
nav: false
---

## Object-Oriented Digital Usage

_2026 – present · Side project_

A tool that limits digital activity to what the task at hand needs, with built-in task management and a feedback loop.
I'm co-designing it with a friend who cares about digital wellbeing, and it is the tool I use every day.

<a class="pp-btn" href="https://github.com/KomaSeo/Digital_Wellbeing_Extensible" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> GitHub</a>

## Value-Based Feed Substitution

_Side project_

Users describe their values in natural language, and the system removes YouTube and Instagram feed items that do not align with them,
replacing each with a video related to those values. I co-designed it with friends interested in digital wellbeing.

<!-- Screenshots are full width and use the original files: the theme's resized webp copies blur the UI text. -->
<figure>
  <img
    src="{{ '/assets/img/personal-projects/value-based-feed-substitution-feed.jpg' | relative_url }}"
    class="img-fluid rounded z-depth-1"
    alt="YouTube home feed with the content filter panel listing an allow or block verdict for each feed item"
    loading="lazy"
    data-zoomable
  >
  <figcaption class="caption">The filter checks each YouTube feed item and hides the ones that conflict with the user's values.</figcaption>
</figure>

<figure>
  <img
    src="{{ '/assets/img/personal-projects/value-based-feed-substitution-settings.png' | relative_url }}"
    class="img-fluid rounded z-depth-1"
    alt="Settings window of the LLM-based filter with a custom prompt describing what to block"
    loading="lazy"
    data-zoomable
  >
  <figcaption class="caption">Users write, in their own words, what the filter should block.</figcaption>
</figure>

The effect was smaller than expected because people still reached for channels they already subscribed to.
The bigger lesson was that the values I hold and what I need to do right now often don't match.
When I play games with friends, the values I follow and the person I want to be are far apart.
This led to Object-Oriented Digital Usage.
