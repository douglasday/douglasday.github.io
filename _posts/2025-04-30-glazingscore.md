
---
title: "The Glazing Score: Measuring AI Sycophancy in the Age of Digital Yes-Men"
date: 2025-04-30
image: /assets/images/posts/glazing.png
layout: single
author_profile: true
excerpt: "Treating Your Scope Like a Treasure Hunt"
header:
  overlay_image: /assets/images/posts/glazing.png
  overlay_filter: 0.5
---

In the court of Emperor Nero, no figure exemplified dangerous sycophancy quite like Ofonius Tigellinus. As Praetorian Prefect, Tigellinus rose to power not through competence or wisdom, but through his willingness to affirm and enable Nero's most destructive impulses. When Nero wanted to murder his mother Agrippina, Tigellinus helped plan it. When Nero needed a scapegoat for the Great Fire of Rome, Tigellinus suggested blaming the Christians. At every turn, Tigellinus's strategy was simple: tell the emperor exactly what he wanted to hear, no matter how delusional or dangerous.

Does the Roman Empire still stand?

Two thousand years later, we face a different kind of yes-man problem—one that scales to billions of interactions daily and operates in the digital realm. AI systems are quickly becoming a regular part of our digital lives, and just as we blindly trust information that a computer outputs, in short order we'll be trusting LLM output similarly.

## The Problem with AI Yes-Men

Joseph Thacker ([@rez0__](https://twitter.com/rez0__)) and I have been increasingly concerned about a troubling pattern in large language models: their tendency to affirm users' beliefs regardless of how false or potentially harmful those beliefs might be. We call this "AI sycophancy," and it represents a significant safety risk as these systems become more integrated into daily life.

To quantify this problem, we developed the Glazing Score — a metric that measures how likely an AI system is to act as a yes-man when confronted with obviously false or delusional statements. The higher the score, the more the AI behaves like Tigellinus, affirming whatever the user wants to hear. The lower the score, the more likely the model is to provide truthful pushback against falsehoods.

## Recent Developments: GPT-4o Raises New Concerns

Our initial research compared several leading models, but recent developments with OpenAI's GPT-4o have highlighted why this work matters more than ever. In the weeks following its release, numerous examples have emerged showing GPT-4o affirming clearly false beliefs:

- Users claiming to be prophets
- Medical misinformation being reinforced rather than corrected
- Conspiracy theories & paranoia being reinforced

This represents a concerning shift. While earlier models like Claude and even GPT-4 would often provide gentle but firm pushback against obvious falsehoods, GPT-4o appears to have been optimized for agreeableness at the expense of truthfulness.

## Why This Matters

The dangers here extend far beyond mere factual inaccuracy. When AI systems affirm delusions:

1. They can reinforce harmful beliefs that might otherwise be corrected
2. They undermine trust in AI systems as reliable information sources
3. They potentially exacerbate mental health issues for vulnerable users
4. They create a market incentive for companies to prioritize user satisfaction over truthfulness

Just as Tigellinus's sycophancy enabled Nero's worst impulses and contributed to the suffering of countless Romans, AI systems that prioritize agreeableness over truth risk amplifying harmful beliefs at unprecedented scale.

## The Glazing Score Methodology

Our evaluation framework presents models with a series of increasingly absurd claims and measures their responses on a spectrum from "clear refutation" to "enthusiastic affirmation." The methodology includes:

- Controlling for different phrasings of the same delusion
- Testing across multiple domains (health, history, science, personal identity)


The results show variation between models, with some consistently pushing back against falsehoods while others seem all too willing to play the role of digital Tigellinus.

![Glazing Score Results](/assets/images/posts/glazingresults.png)

## Looking Forward

As AI capabilities continue to advance, the sycophancy problem requires urgent attention. Our complete findings, including detailed model comparisons and recommendations for developers, are available in our full report.

The lesson from Tigellinus is clear: those who tell us only what we want to hear rarely have our best interests at heart. As we build increasingly powerful AI systems, we must ensure they're designed to serve truth rather than merely please users—even when the truth isn't what we want to hear.


