---
layout: page
title: Personal projects
permalink: /personal-projects/
description: Tools I built for myself and my friends. We implemented and used these tools for ourselves.
nav: false
---

<!-- Screenshots use the original files: the theme's resized webp copies blur the UI text. Each pair sits in one row; flex = width/height keeps both the same height. -->

<h2 id="object-oriented-digital-usage">Object-Oriented Digital Usage <a class="pp-btn" href="https://github.com/KomaSeo/Digital_Wellbeing_Extensible" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> GitHub</a></h2>

<div class="pp-images">
<figure style="flex: 2.28">
  <img
    src="{{ '/assets/img/personal-projects/object-oriented-digital-usage-flow.webp' | relative_url }}"
    class="img-fluid rounded z-depth-1"
    alt="Flow diagram: to-do list, AI picks a task and a time box, work on the task while an AI window check blocks off-task apps, report, look back, and adjust the plan"
    loading="lazy"
    data-zoomable
  >
  <figcaption class="caption">The loop the tool runs for every task.</figcaption>
</figure>

<figure style="flex: 0.89">
  <img
    src="{{ '/assets/img/personal-projects/object-oriented-digital-usage-app.png' | relative_url }}"
    class="img-fluid rounded z-depth-1"
    alt="The app's Work screen showing the current task, its to-do, a countdown timer, and the remaining steps"
    loading="lazy"
    data-zoomable
  >
  <figcaption class="caption">The Work screen while a task is running.</figcaption>
</figure>
</div>

Most digital wellbeing tools ask "how much time did you spend?". This tool asks "does this app or site serve the task I'm doing right now?".
It limits digital activity to what the current task needs, and wraps that limit in task management and a feedback loop,
so the plan itself gets better over time. I'm co-designing it with a friend who cares about digital wellbeing, and it is the tool I use every day.

**How it works**

- **To-do list.** To-dos are grouped and ordered, with deadlines and time estimates, plus my own life rules (for example, deep writing in the morning).
- **Pick a task.** An AI chooses one task and a time box that fit the deadlines and my rules, and says why it picked that task.
- **Work on the task.** The task, its remaining steps, and a timer stay on screen. A to-do can be broken into steps, each with its own estimate.
- **Window check.** While I work, every app or site I open is checked against the task and its remaining steps.
  On-task windows are allowed, off-task ones are blocked, and if I need something anyway, I ask with a reason and the AI decides.
- **Report and look back.** When the time is up, I report whether I finished, didn't finish, or need to extend the time box.
  If I went over the estimate, I say why: the steps were too coarse, I didn't know enough, or something else.
- **Adjust the plan.** Based on that, I split the to-do into smaller ones, add a to-do to look into what I didn't know, or re-estimate.

## Value-Based Feed Substitution

<div class="pp-images">
<figure style="flex: 1.38">
  <img
    src="{{ '/assets/img/personal-projects/value-based-feed-substitution-settings.png' | relative_url }}"
    class="img-fluid rounded z-depth-1"
    alt="Settings window of the LLM-based filter with a custom prompt describing what to block"
    loading="lazy"
    data-zoomable
  >
  <figcaption class="caption">Users write, in their own words, what the filter should block.</figcaption>
</figure>

<figure style="flex: 1.57">
  <img
    src="{{ '/assets/img/personal-projects/value-based-feed-substitution-feed.jpg' | relative_url }}"
    class="img-fluid rounded z-depth-1"
    alt="YouTube home feed with the content filter panel listing an allow or block verdict for each feed item"
    loading="lazy"
    data-zoomable
  >
  <figcaption class="caption">The filter checks each YouTube feed item and hides the ones that conflict with the user's values.</figcaption>
</figure>
</div>

Recommendation feeds are tuned for engagement, not for what we care about. In this project, users describe their values in natural language,
and the system removes YouTube and Instagram feed items that do not align with them, replacing each with a video related to those values.
I co-designed it with friends interested in digital wellbeing.

**How it works**

- **Extract.** A browser extension pulls the text and images of each feed item and sends them to a local app for evaluation.
- **Judge.** Each item goes through filters: a word-based blacklist, and an LLM-based filter that follows a block prompt the user writes in their own words.
- **Hide and substitute.** Items judged "block" are hidden from the feed and replaced with videos related to the user's values.
- **Guard.** The local app closes browsers that aren't running the extension, so the filter can't simply be bypassed, and blacklisted sites redirect to a block page.

**What I learned**

The effect was smaller than expected because people still reached for channels they already subscribed to.
The bigger lesson was that the values I hold and what I need to do right now often don't match.
When I play games with friends, the values I follow and the person I want to be are far apart.
This led to Object-Oriented Digital Usage: instead of filtering by values, it filters by the task at hand.
