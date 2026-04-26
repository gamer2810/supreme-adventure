---
title: Showcase Steam Profile on your website!
date: February 12, 2025 1:24 PM
categories:
  - web-development
tags:
  - steam
  - embed
  - javascript
  - widget
  - tutorial
description: Are you a gamer who wants to proudly display your Steam profile on
  your website? I made a lightweight, customizable widget that brings your Steam
  identity to life on any web page!
toc: true
comments: true
math: false
image: /assets/img/uploads/steam-miniprofile.png
mermaid: true
---
## Introduction

Steam MiniProfile is a sleek, embeddable widget that fetches and displays your Steam profile information in real-time. With just a few lines of code, you can showcase your Steam avatar, username, current online status, recent games, and more—right on your website!

This widget is perfect for gaming communities, streamers, or anyone who wants to add a personal touch to their website by integrating their Steam presence seamlessly.

## Features at a Glance

* 🎮 **Real-Time Steam Data** – The widget fetches your profile info directly from Steam, ensuring it's always up to date.
* ✨ **Customizable UI** – Adjust colors, layout, and design elements to match your website's aesthetic.
* ⚡ **Lightweight & Fast** – Built for performance, the widget is optimized to load quickly without affecting page speed.
* 🔧 **Easy Integration** – Just drop the widget on your website and configure it with your Steam ID.
* 🔍 **Supports Public Profiles** – Works with any Steam account that has a public profile.

## How It Works


```mermaid
sequenceDiagram
User->>+gamer2810.github.io: Get Steam Miniprofile
loop Every 5 minutes
    Note right of Pipedream: Glitch shutdowns the CORS Server<br>every 5 minutes, so we schedule a request<br> every 5 mins to wake it up, ensuring response time
    Pipedream->>CORS Server: Wake up
end
gamer2810.github.io->>-User: Return loading miniprofile
Note right of User: Wait for real profile to load
gamer2810.github.io->>+CORS Server: Get real profile HTML
Note right of CORS Server: https://glitch.com/~steam-miniprofile-cors
CORS Server->>+Steam: Get real profile HTML
Steam->>-CORS Server: Requested HTML
CORS Server->>-gamer2810.github.io:Profile HTML with CORS headers
gamer2810.github.io-->User: Replace loading miniprofile with real HTML
```

## Get Started

Ready? Head over to the GitHub repository to grab the code and set it up in minutes:

➡️ **[GitHub Repo: gamer2810/steam-miniprofile](https://github.com/gamer2810/steam-miniprofile)**

Join the growing community of gamers showcasing their Steam profiles effortlessly. If you have any feature requests or encounter any issues, feel free to open an issue on GitHub!

Happy gaming! 🎮
