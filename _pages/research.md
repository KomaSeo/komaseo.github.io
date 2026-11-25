---
layout: page
title: research
permalink: /research/
description: How people can retain agency over the digital media and AI that shape their behavior and cognition.
nav: true
nav_order: 1

# Projects, newest first. Teaser images go in assets/img/research/<image>.jpg (or .png / .gif);
# a project whose image file is missing is shown without one.
projects:
  - period: 2026 – present
    title: Object-Oriented Digital Usage
    kind: Side project
    image: object-oriented-digital-usage
    description: >-
      A tool that limits digital activity to what the task at hand needs, with built-in task management and a feedback loop.
      I'm co-designing it with a friend who cares about digital wellbeing, and it is the tool I use every day.
    links:
      - name: GitHub
        url: https://github.com/KomaSeo/Digital_Wellbeing_Extensible

  - period: 2024 – 2026
    title: Ethics Training Agents
    kind: Interactive Computing Lab, KAIST
    image: ethics-training-agents
    description: >-
      Multi-agent LLM system that supports group-based ethics education through role-playing and discussion,
      helping students reflect on and explore the ethical implications of technology.
    links:
      - name: arXiv
        url: https://arxiv.org/abs/2609.11529

  - period: 2024 – 2026
    title: Instructor-Informed Multi-Agent AI for Ethics Education
    kind: Interactive Computing Lab, KAIST
    image: instructor-informed-ethics-ai
    description: >-
      Bringing instructors' intentions into multi-agent AI for ethical deliberation, deployed across five engineering courses.
    status: In preparation

  - period: 2024 – 2026
    title: "Speak, Watch, Verify: Older Adults and Mobile Automation Agents"
    kind: Interactive Computing Lab, KAIST
    image: speak-watch-verify
    description: >-
      A mental model of how older adults interact with mobile automation agents the first time they use them.
    status: Under review

  - period: 2024 – 2025
    title: Personalized Micro-Financial Incentives for Digital Wellbeing
    kind: Interactive Computing Lab, KAIST
    image: micro-financial-incentives
    description: >-
      Personalizing small financial incentives to help people change their digital habits.
    status: ACM CHI 2025
    links:
      - name: Publications
        url: /publications/

  - period: "2024"
    title: Value-Based Feed Substitution
    kind: Side project
    image: value-based-feed-substitution
    description: >-
      Users describe their values in natural language, and the system removes YouTube and Instagram feed items that do not align with them,
      replacing each with a video related to those values. Co-designed with friends interested in digital wellbeing.
      The effect was smaller than expected because people still reached for channels they already subscribed to.
      The bigger lesson was that the values I hold and what I need to do right now often don't match. When I play games with friends,
      the values I follow and the person I want to be are far apart. This led to Object-Oriented Digital Usage.

  - period: 2022 – 2023
    title: Comparing Vestibular Stimulation-Based Redirected Walking
    kind: HCIS Lab, GIST
    image: vestibular-redirected-walking
    description: >-
      Comparing electrical, vibrational, and cooling stimuli for redirected walking in virtual reality.
    status: ACM CHI 2023
    links:
      - name: Publications
        url: /publications/

  - period: 2022 – 2023
    title: Bone-Conduction Vibration for Redirected Walking
    kind: HCIS Lab, GIST
    image: bone-conduction-redirected-walking
    description: >-
      Applying bone-conduction vibration to redirected walking for more seamless walking in virtual reality.
    status: IEEE ISMAR 2023, Honorable Mention Award
    links:
      - name: Publications
        url: /publications/
---

## Vision

Digital media and AI systems increasingly shape what we pay attention to, how we make decisions, and how we think.
My research in **positive computing** and **digital wellbeing** asks how people can retain agency over these systems:
not by giving up technology, but by understanding how it affects them and steering it toward what they actually value.

## Directions

### 1. Examining how digital and AI use affects people

People rarely see the effects of their own technology use clearly. I design tools that help people examine how their digital and AI use
shapes their behavior and cognition, so that change starts from their own understanding rather than from generic rules.

### 2. Sharing these effects with the people around them

Technology use is social, and so are its effects. I study how people can share what they learn about their technology use with the people
around them, such as family, friends, classmates, and colleagues, and reflect on it together.

### 3. Building digital environments that prevent harm and fit each situation

There is no single right intervention. I explore how to build digital environments that prevent harm in ways that fit a person's own situation,
building on work in behavior change such as personalized micro-financial incentives for digital wellbeing (CHI 2025).

## Projects

<!-- prettier-ignore-start -->
<style>
  .research-projects .project { display: flex; gap: 1.25rem; align-items: flex-start; padding: 1.25rem 0; border-top: 1px solid var(--global-divider-color); }
  .research-projects .project-teaser { flex: 0 0 200px; }
  .research-projects .project-teaser img { width: 200px; height: 130px; object-fit: cover; border-radius: 0.375rem; border: 1px solid var(--global-divider-color); }
  .research-projects .project-body { flex: 1 1 0; min-width: 0; }
  .research-projects .project-period { font-size: 0.8rem; font-weight: 600; color: var(--global-theme-color); }
  .research-projects .project-title { margin: 0.15rem 0 0.1rem; font-size: 1.05rem; font-weight: 600; }
  .research-projects .project-kind { font-size: 0.85rem; color: var(--global-text-color-light); }
  .research-projects .project-body p { margin: 0.4rem 0 0; font-size: 0.95rem; }
  .research-projects .project-meta { margin-top: 0.4rem; font-size: 0.85rem; }
  .research-projects .project-meta em { color: var(--global-text-color-light); }
  @media (max-width: 576px) {
    .research-projects .project { flex-direction: column; }
    .research-projects .project-teaser, .research-projects .project-teaser img { width: 100%; flex-basis: auto; height: auto; }
  }
</style>
<div class="research-projects">
{% assign teaser_exts = "jpg,png,gif,webp" | split: "," %}
{% for p in page.projects %}
{% assign teaser = "" %}
{% for ext in teaser_exts %}
{% capture teaser_path %}assets/img/research/{{ p.image }}.{{ ext }}{% endcapture %}
{% capture teaser_found %}{% file_exists {{ teaser_path }} %}{% endcapture %}
{% if teaser == "" and teaser_found == "true" %}{% assign teaser = teaser_path %}{% endif %}
{% endfor %}
<div class="project">
{% if teaser != "" %}<div class="project-teaser"><img src="{{ teaser | prepend: '/' | relative_url }}" alt="{{ p.title }}" loading="lazy"></div>{% endif %}
<div class="project-body">
<div class="project-period">{{ p.period }}</div>
<div class="project-title">{{ p.title }}</div>
<div class="project-kind">{{ p.kind }}</div>
<p>{{ p.description }}</p>
{% if p.status or p.links %}<div class="project-meta">{% if p.status %}<em>{{ p.status }}</em>{% endif %}{% for l in p.links %}{% if p.status or forloop.index > 1 %} · {% endif %}<a href="{% if l.url contains '://' %}{{ l.url }}{% else %}{{ l.url | relative_url }}{% endif %}">{{ l.name }}</a>{% endfor %}</div>{% endif %}
</div>
</div>
{% endfor %}
</div>
<!-- prettier-ignore-end -->
