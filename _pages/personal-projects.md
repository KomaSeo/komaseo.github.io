---
layout: page
title: Personal projects
permalink: /personal-projects/
description: Tools I built for myself and my friends. We implemented and used these tools for ourselves. We believe we can improve ourselves by improving the digital environments we use.
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

When I used existing digital wellbeing tools, what they blocked was fixed. It was hard to adapt the block list to what I actually meant to do on my device at that moment,
and because of that, I could never stick with a digital wellbeing app for long.
With this tool, we set out to make long-term digital wellbeing possible. Users define their life rules and to-do list,
and the tool checks at the content level whether what they open fits their current task and their rules.

**How it works**

- **Set life rules.** The user writes the rules they want to live by, such as doing deep writing in the morning.
- **To-do list.** The user's to-dos are grouped and ordered, with deadlines and time estimates.
- **Pick a task.** An AI chooses one task and a time box that fit the deadlines and the user's rules, and says why it picked that task.
- **Work on the task.** The task, its remaining steps, and a timer stay on screen. A to-do can be broken into steps, each with its own estimate.
- **Window check.** While the user works, every app or site they open is checked against the task and its remaining steps.
  On-task windows are allowed, off-task ones are blocked, and if the user needs something anyway, they ask with a reason and the AI decides.

**What I learned**

We do use it every day, but it turned out to have more inconveniences than we expected. A lot of necessary internet use is only indirectly tied to the task.
For example, writing a paper may require opening GitHub to read someone's code, which the AI is highly likely to block.
So we built an "AI court," where the user can argue why they need a blocked site and the AI rules on the appeal.

We also want complex rules but simple choices in the moment. Real life is full of outliers, so we want our usage rules to cover many paths
(what we call a high path complexity objective), such as "On Friday at 8 p.m., if next week's to-dos add up to more than 80 estimated hours, don't take the evening break."
At the same time, we want each moment to involve as few decisions as possible (what we call a low choice complexity objective).
We don't want to spend attention on entering accurate time estimates.

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

- **Write values.** Users describe their values in natural language. As soon as they finish, the system searches for videos related to those values and saves them in advance.
- **Extract.** A browser extension pulls the text and images of each feed item and sends them to a local app for evaluation.
- **Judge.** Each item goes through filters: a word-based blacklist, and an LLM-based filter that follows a block prompt the user writes in their own words.
- **Hide and substitute.** Items judged "block" are hidden from the feed and replaced with the saved value-related videos.
- **Review.** Later, the hidden videos are shown to the user, who evaluates whether each one should have been hidden.

**What I learned**

The effect was smaller than expected because people still reached for channels they already subscribed to.
The bigger lesson was that the values I hold and what I need to do right now often don't match.
When I play games with friends, the values I follow and the person I want to be are far apart.
This led to Object-Oriented Digital Usage: instead of filtering by values, it filters by the task at hand.
