---
title: Speechkit API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://speechkit.io'>Sign Up and get an API key</a>

includes:
  - authentication
  - news_sites
  - get_articles
  - errors

search: true
---

# Introduction

Welcome to the speechkit.io API documentation!

Please read these docs to get a better understanding for how you can use speechkit.io to generate audio from text.

<aside class="notice">
  Speechkit SDKs for ruby, node and iOS are coming soon.
</aside>


## Model orientation/structure

1. `PUBLISHER`: By using speechkit.io you're a publisher, no matter if you're a blogger or a media conglomerate. Your keys belong to what we call a publisher. Every publisher needs to have at least one news site.
2. `NEWS_SITE`: A news site defines every site you run. This is to separate analytics and audio generation etc.
3. `ARTICLES`: Every article belongs to a news site.
