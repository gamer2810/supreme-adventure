---
title: Making a Progressive Web App with Google AI Studio
date: July 3, 2025 10:57 PM
categories:
  - webdev
tags:
  - pwa
  - fe
  - gh-pages
  - react
  - google
  - api
description: This project details the end-to-end process of building a
  Progressive Web App (PWA) using React, leveraging Google APIs for features
  like secure user login and data backup to Google Drive, managing local data
  efficiently with IndexedDB, and integrating Google Analytics for insights. The
  PWA is then seamlessly hosted on GitHub Pages, demonstrating a complete
  deployment pipeline for modern web applications.
toc: true
comments: true
math: false
image: false
---
Hey everyone!

I recently spent some time diving deep into [Google's AI Studio](https://aistudio.google.com/). While it certainly has its quirks with some technical choices and occasionally outdated or conflicting API code, I managed to develop a PWA with it. Along the way, I made a point of tackling new technologies to see how the AI model approached them, which was a fascinating learning experience in itself. These are the topics I found particularly helpful on my coding journey:

* PWA and How They Work: How to create a PWA with service worker. How to adapt it to enable installation on mobile device.
* Google Login: Implement secure Google login on React with gapi-script.
* Google Drive APIs for Data Backup: Enables users to back up their shopping list data as a .csv file directly to their personal Google Drive, giving them ownership and accessibility of their information.
* IndexedDB for Local Data Management: This browser-based database allows for local storage and retrieval of shopping list data, contributing to a responsive and reliable application even without an internet connection.
* Google Analytics Integration: I integrated Google Analytics to gather anonymous metrics on how users engage with the PWA, providing data-driven insights for future enhancements.
* Google AI Studio & Development: This project was built *with* Google AI Studio. My exploration involved seeing how the AI model helped navigate development, especially for integrating complex features or generating code snippets.
* Hosting React App on GitHub: I utilized GitHub Pages for hosting, which is actually free and quite easy following this [guide](https://github.com/gitname/react-gh-pages).

### So, What Can This PWA Actually Do?

I built this PWA to be useful for managing your everyday shopping. Here are some of its core features:

* Manage Your Shopping List: Easily add, edit, and remove items to keep your shopping list organized and up-to-date.

* Record Shopping Trips: Log your purchases by selecting items from your list, adding any unplanned items, noting the total amount spent, and optionally attaching a receipt image for reference.

* Detailed Spending Reports: Access daily, weekly, and monthly reports that summarize your total expenditure and provide a clear breakdown of planned versus unplanned items, helping you track and manage your budget.

* Local Data Storage with IndexedDB: Benefit from fast loading times and offline access, as your data is securely stored directly on your device.

* Secure Google Login & Drive Backup: Sign in conveniently with your Google account, and rest assured that your shopping data is backed up to your Google Drive as a .csv file, giving you full control.

* PWA for Mobile Installation & Persistence: Install the application directly to your mobile device's home screen for quick access, enjoying a native-app like experience with local data persistence.

---

Check out the PWA here: <https://shopping.k3k.dev/>

Happy shopping (and coding)!
