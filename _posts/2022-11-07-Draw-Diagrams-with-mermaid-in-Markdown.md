---
title: Draw Diagrams with mermaid in Markdown
author: frank
date: 2022-11-07 22:51:00 +0800
categories: [Programming,Markdown]
tags: [markdown]     # TAG names should always be lowercase
render_with_liquid: false
---
## 1. About Mermaid

>**Mermaid lets you create diagrams and visualizations using text and code.**   
>It is a JavaScript based diagramming and charting tool that renders Markdown-inspired text definitions to create and modify diagrams dynamically.

## 2. Why we use Mermaid to draw Diagrams?

### 2.1 Diagrams is a useful tools to explain complex issue
It is easy to overlook diagrams when you’re working at a non-corporation. Diagrams are often used in corporate companies with many teams, departments, engineers, outsourced resources, and complicated legal obligations.

Yet, we still draw diagrams on whiteboards when we’re onboarding new teammates, discussing new architecture ideas, or presenting the roadmaps of our projects.

That’s because, sometimes, it’s nearly impossible to explain things with words.

### 2.2 it takes effort to learn different diagram-drawing tools
Developers often appreciate a well-drawn graph for explaining software or infrastructure architecture but they’re very reluctant to draw one themselves. The most common reason for this is the tooling required to draw a diagram.

There are dozens if not hundreds of diagram-drawing tools out there with essentially similar but practically different interfaces. It takes an effort to learn this new UI, draw what you want to draw, export to a common format, insert the exported file into your documentation.

### 2.3 Mermaid's approach benefits us in terms of maintainability
It is quite a pain when you need to move elements all the time to make space for the new ones you’re adding. Even being able to automate this rearrangement process would be an amazing time saver.

What makes Mermaid interesting is the fact that it lets you define diagrams in a text-based, markdown-friendly way. This, in turn, makes it super easy to maintain and version-control these diagrams.

Since Mermaid is text-based, the diff in Git is much more clear in terms of what is changing and much easier to keep track of.

## 3. Exploring the Live Editor
If you’re feeling too lazy to set Mermaid up and experiment, you can start with its [live editor](https://mermaid-js.github.io/mermaid-live-editor). It is very simple and intuitive to explore what your diagrams would look like.

The tool also lets you download your final creation as an image file so if you only need to sketch something quickly and post it somewhere, you’ll love it.

If you’re using Visual Studio Code, **Markdown Preview Mermaid Support** is a decent plugin to visualize your Mermaid graphs and markdown files within VS Code.

## 4. Customizing the Style of Your Diagrams

You can add %%{init: [options]}%% in the first line of mermaid diagram to config mermaid details

- [Directives](https://mermaid-js.github.io/mermaid/#/directives)

Directives gives a diagram author the capability to alter the appearance of a diagram before rendering by changing the applied configuration.
- [Theming](https://mermaid-js.github.io/mermaid/#/theming)

With Version 8.7.0 Mermaid comes out with a system for dynamic and integrated configuration of themes. The intent is to increase the customizability and ease of styling for mermaid diagrams.

The theme can be altered by changing the root level variable theme variable in the configuration. To change it for the whole site you must use the initialize call. To do it for just for a single diagram you can use the %%init%% directive
- [Accessibility](https://mermaid-js.github.io/mermaid/#/accessibility)

Now with Mermaid library in much wider use, we have started to work towards more accessible features, based on the feedback from the community.

To begin with, we have added a new feature to Mermaid library, which is to support accessibility options, Accessibility Title and Accessibility Description.

## 5. Userful Links
https://mermaid-js.github.io/mermaid/#/README   
https://support.typora.io/Draw-Diagrams-With-Markdown/
https://www.redgregory.com/notion/2022/1/17/how-to-get-started-with-mermaid-in-notion
