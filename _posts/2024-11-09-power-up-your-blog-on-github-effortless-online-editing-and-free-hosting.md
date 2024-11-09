---
media_subpath: assets/img/uploads/
title: "Power Up Your Blog on GitHub: Effortless Online Editing and Free Hosting"
date: November 9, 2024 3:46 PM
categories:
  - guide
tags:
  - jekyll
  - cms
  - decap
  - blog
description: Deploy your own blog with the ability to add/edit content straight
  from the web with GitHub, Jekyll and DecapCMS.
toc: true
comments: true
---
## Why Add a CMS to Your Jekyll Blog on GitHub?

When I first considered hosting my own blog, I faced a few key challenges that many others might relate to. Here’s what drove me to look for a better solution:

* Hosting a dynamic website can be expensive. I wanted a budget-friendly option for hosting. Many traditional website setups require costly infrastructure to support dynamic content. However, using Jekyll and GitHub Pages provides an ideal alternative: a static blog that is not only reliable but also completely free to host.
* The need for effortless, cross-device content editing. While apps like Obsidian are excellent for note-taking and writing, they come with limitations. For instance, syncing content across multiple devices isn’t as smooth or automatic as I’d like. I was searching for a web-based experience, similar to Notion, where I could easily add and edit content from any device without worrying about syncing issues.

This guide will walk you through how to set up your Jekyll blog on GitHub Pages and transform it into a user-friendly, interactive editing experience with a CMS. It’s the best of both worlds: free hosting and the flexibility to manage your content from anywhere.

This guide will walk you through these steps:

1. Setting up your own Jekyll blog (you can skip this if you already have one).
2. Configuring DecapCMS to manage your content seamlessly.
3. Setting up a custom domain for a personalized web address.

## Setting up your own Jekyll blog

The easy way:

https://chirpy.cotes.page/posts/getting-started/#option-1-using-the-starter-recommended

The hard way: 

https://docs.github.com/en/pages/quickstart

## Configuring DecapCMS
Following these steps will give you an online website where you can create/edit your blog post using a web browser. Each addition/modification will automatically result in a commit against your repository.

1. Setup a GitHub application that redirects to Netlify
2. Setup a Netlify project that points to your `username.github.io` domain
3. Setup the admin page in your Jekyll project
