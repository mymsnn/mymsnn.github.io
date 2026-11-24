---
layout: page
title: README
permalink: /readme.html
---

# 好柿花生 — Personal Blog

**好柿花生** is a personal blog for everyday life, memories, observations, and useful things discovered along the way.

Its motto is:

> Be an interesting person. Live an interesting life.

This site is a personal space, not a publication with a fixed schedule or a narrow subject. It keeps things worth remembering: ordinary moments, old stories, personal thoughts, and occasional notes about technology and the internet.

## What This Blog Is About

### Life and Personal Notes

Everyday experiences, small discoveries, reflections, and thoughts that are worth writing down.

### Memories and Stories

Stories about earlier years, old friends, family, familiar places, and the details that make up a personal history.

### Technology and the Internet

Interesting websites, software, open-source projects, digital tools, and practical experiments. These posts are personal notes and observations rather than official documentation.

### Books, Music, and Other Discoveries

Things read, heard, watched, or found online that leave a lasting impression.

There is no requirement to cover every topic, follow trends, or publish on a schedule. Posts are written when there is something worth keeping.

## Site at a Glance

| Item | Details |
| --- | --- |
| Site name | 好柿花生 |
| Motto | 做一个有意思的人 |
| Site type | Personal blog |
| Main language | Chinese |
| Static site generator | Jekyll |
| Theme | Minima |
| Source repository | [mymsnn/mymsnn.github.io](https://github.com/mymsnn/mymsnn.github.io) |

The site keeps the Minima theme as its foundation, with a small number of project-specific layouts, includes, and CSS overrides.

## Technology

- **Jekyll** generates the site from Markdown, Liquid templates, and configuration.
- **Minima** provides the base theme and its standard site structure.
- **jekyll-feed** generates the RSS feed.
- **jekyll-sitemap** generates the sitemap.
- **highlight.js** provides client-side syntax highlighting for selected code languages.
- **Custom Liquid layouts and includes** add the post navigation and sharing elements.

The syntax highlighter is configured to run in the browser. The current page setup explicitly loads language support for Plain Text, PowerShell, and T-SQL, along with the GitHub and SSMS stylesheets.

## Repository Structure

| Path | Purpose |
| --- | --- |
| `_posts/` | Blog posts |
| `assets/images/` | Images used by posts and the site |
| `_layouts/` | Custom page and post layouts |
| `_includes/` | Reusable page components |
| `css/override.css` | Project-specific style overrides |
| `js/highlightjs/` | highlight.js runtime, language files, and styles |
| `_config.yml` | Site settings, theme, plugins, and defaults |
| `.github/PROJECT-RECORD.md` | Internal project history and maintenance notes |

Some files and layouts are supplied by the Minima theme rather than stored directly in this repository.

## Writing a Post

Posts are stored in `_posts/` and use Markdown.

A typical post begins with front matter:

```yaml
---
title: "Your Post Title"
date: 2026-11-24
---
```

Use a filename in the Jekyll post format:

```text
_posts/YYYY-MM-DD-your-post-slug.md
```

Write the article body in Markdown. Use fenced code blocks with a language identifier when including code, for example:

```sql
SELECT * FROM example_table;
```

The site currently assigns the default tag `Other` to posts unless a post defines its own tags.

## Layout and Reading Features

The post layout adds a few features on top of the base theme:

- The post title and publication date appear at the top of the article.
- Sharing links are included with the post.
- Previous and next post navigation appears at the end.
- The archive link is used when there is no adjacent post.

The publication date stays directly below the title. These established reading and navigation elements should be preserved when editing the layout.

## Design and Maintenance Principles

- Keep the site simple and focused on reading.
- Retain Minima as the base theme unless a deliberate theme change is requested.
- Prefer small, targeted improvements over large redesigns.
- Preserve existing posts, images, layouts, navigation, and working features.
- Do not synchronize the fork wholesale with its upstream repository; review and adopt changes selectively.
- Keep project-specific styles in the override stylesheet where practical.
- Record important changes, affected files, commit identifiers, and deployment status in `.github/PROJECT-RECORD.md`.
- Mark deployment as unverified until a successful build or live result has actually been checked.

## Project Philosophy

A personal blog does not need to be busy to be meaningful.

Some posts may record a day, some may preserve a memory, and others may share a useful discovery. The point is to leave a small, honest record of things that might otherwise be forgotten.

Thanks for visiting **好柿花生**.
