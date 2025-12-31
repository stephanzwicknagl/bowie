# Bowie - Hugo theme

Bowie is a minimal and clean theme for hugo with a markdown-ish UI.

Forked from [Archie Theme](https://github.com/athul/archie)

## Demo

[Check the Demo](https://bowie.github.io/bowie/) hosted on GitHub Pages :smile: .
You can find the source code to that in the `site` branch of this repository

![](/images/theme.png)
![](/images/archie-dark.png)

## Feature

- Homepage featuring introduction section and list of main content linking outside
- Shortcode for embedding pdfs: `{{< pdfReader "file.pdf" >}}`

## Installation

In your Hugo website directory, create a new folder named theme and clone the repo

```bash
mkdir themes
cd themes
git clone https://github.com/stephanzwicknagl/bowie.git
```

Edit the `config.toml` file with `theme="bowie"`
For more information read the official [setup guide](https://gohugo.io/installation/) of Hugo.

If you encounter any issues with Google Analytics, update Hugo to v0.125.0 or
later and make sure your using the latest version of the theme.

## Writing Posts

Create a new `.md` file in the *content/posts* folder

```yml
---
title: Title of the post
description:
date:
link: (optional)
tldr: (optional)
draft: true/false (optional)
tags: [tag names] (optional)
toc: true/false (optional)
---
```

----

## Config of the Demo Site

```toml
baseURL = "https://example.com"
languageCode = "en-us"
title = "Bowie"
theme="bowie"
copyright = "© Stepan Zwicknagl"
pygmentsstyle = "monokai"
pygmentscodefences = true
pygmentscodefencesguesssyntax = true

[params]
    mode="auto"
    useCDN=false
    subtitle = "Minimal and Clean [blog theme for Hugo](https://github.com/stephanzwicknagl/bowie)"
    mainSectonsTitle = "Latest Posts and Contributions"

[[params.social]]
name = "GitHub"
icon = "github"
url = "https://github.com/stephanzwicknagl/bowie"

[[menu.main]]
name = "Home"
url = "/"
weight = 1

[[menu.main]]
name = "All posts"
url = "/posts"
weight = 2

[[menu.main]]
name = "About"
url = "/about"
weight = 3

[[menu.main]]
name = "Tags"
url = "/tags"
weight = 4
```
