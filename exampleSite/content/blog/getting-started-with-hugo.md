+++
title = "Getting Started with Hugo"
date = "2025-03-01"
description = "Why I chose Hugo for my blog and how to get a site up and running in minutes."
tags = [
    "hugo",
    "web",
    "tutorial",
]
+++

Static site generators have come a long way. After trying several options, I settled on Hugo for this blog. Here's why — and how you can get started too.

<!--more-->

## Why Hugo?

There are plenty of static site generators out there — Jekyll, Eleventy, Astro, Next.js — but Hugo stands out for a few reasons:

- **Speed**: Hugo builds are measured in milliseconds. Even sites with thousands of pages build in under a second.
- **Single binary**: No Node.js, no Python, no Ruby. Just one binary and you're good to go.
- **Built-in features**: Syntax highlighting, image processing, taxonomies, and i18n are all included out of the box.
- **Active development**: Hugo has been around since 2013 and is still actively maintained.

## Getting Started

First, install Hugo. On macOS:

```bash
brew install hugo
```

On Linux, grab the binary from the [releases page](https://github.com/gohugoio/hugo/releases) or use your package manager.

Then create a new site:

```bash
hugo new site my-blog
cd my-blog
```

## Adding a Theme

Hugo uses themes to control the look of your site. The Bear Blog theme is a great minimal option:

```bash
git submodule add https://github.com/janraasch/hugo-bearblog themes/hugo-bearblog
echo "theme = 'hugo-bearblog'" >> hugo.toml
```

## Writing Your First Post

Create a new post:

```bash
hugo new content/blog/hello-world.md
```

This creates a Markdown file with front matter. Edit it, add your content, and preview your site:

```bash
hugo server -D
```

Open `http://localhost:1313` in your browser and you'll see your site live with hot reloading.

## Deploying to Netlify

Deploying a Hugo site to Netlify is straightforward. Push your code to GitHub, connect the repo to Netlify, and set the build command to `hugo --minify`. Netlify handles the rest — builds, CDN, HTTPS, all of it.

Add a `netlify.toml` to your project root to pin the Hugo version:

```toml
[build]
  publish = "public"
  command = "hugo --minify"

[build.environment]
  HUGO_VERSION = "0.135.0"
```

That's it. Every push to your main branch triggers a fresh build and deploy.

## What's Next

Hugo has a lot of depth beyond the basics — custom shortcodes, data templates, multiple output formats, and more. But you don't need any of that to get started. A theme, some Markdown files, and a deploy target are all it takes.
