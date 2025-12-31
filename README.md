# Bowie - Hugo theme

Bowie is a minimal and clean theme for hugo with a markdown-ish UI.

Forked from [Archie Theme](https://github.com/athul/archie)

## Demo

[Check the Demo](https://bowie.github.io/bowie/) hosted on GitHub Pages :smile: .
You can find the source code to that in the `site` branch of this repository

![](/images/theme.png)
![](/images/archie-dark.png)

## Feature
- Google Analytics Script
- Callouts
- Tags
- Search
- Auto Dark Mode(based on system theme)
- Dark/Light Mode toggle
- tl:dr; frontamatter
- Table of contents
- Cache busting for CSS files
- Disqus Comments
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

## Config Options

### Custom CSS
Custom CSS files can be included though the `customcss` config parameter.

Note: CSS files should be placed under the `assets` directory e.g. `assets/css/first.css`.

```toml
[params]
	customcss = ["css/first.css", "css/second.css"]
```

### Callouts

There are five different types of callout, including this themes original callout and a custom one as well. These callouts are compatible with both light and dark theme modes. 

![Screenshot from 2025-01-04 19-22-43](https://github.com/user-attachments/assets/bcaf7c3c-2339-449f-8bcb-8a2906d7ddcf)


#### Original

This steup is to ensure backwards compatibility for previous callouts.

```markdown                                                                                                                                                                                                    
{{< callout emoji="⚡️" text="Original callout." >}}
```

#### Alert
```markdown
{{< callout type="alert" text="This is an alert callout." >}}
```

#### Custom

This include the ability to set your own callout emoji, title, and css style element.

```markdown
{{< callout type="custom" emoji="⚡️" title="Custom callout" text="This is custom text for a custom callout." style="background-color: transparent; border: 3px solid #d340e0;" >}}
```

#### Tip

```markdown
{{< callout type="tip" text="This is a tip callout." >}}
```

#### Warning

```markdown
{{< callout type="warning" text="This is a warning callout." >}}
```

### Search

Archie ships with an opt-in search page backed by a Hugo-generated JSON index.

1. Create a search page:

```yaml
---
title: "Search"
layout: "search"
outputs:
  - html
  - json
---
```

2. Add the page to your main menu if you want it linked in the header:

```toml
[[menu.main]]
name = "Search"
url = "/search/"
weight = 5
```

The generated search page indexes the same content surface as the home page when
`params.mainSections` is set. Otherwise it falls back to all regular pages,
excluding hidden content and the search page itself.

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
