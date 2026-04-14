---
layout: post
title: "Contributing to Micromass Athenæum"
subtitle: "How to clone the repo, build locally, open issues, make pull requests, and write new posts"
date: 2026-04-14
categories: [misc]
tags: [github, contributing, workflow]
reading_time: 8
author: "Frosty"
tldr: Everything you need to go from zero to merged pull request, cloning the repo, running Jekyll locally, filing issues, opening PRs, and writing your first post.
---

Whether you want to fix a typo, write a new post, or suggest a feature, this guide walks you through the full contribution workflow for Micromass Athenæum.

## 1. Clone the Repo and Build Locally

First, make sure you have Ruby and Bundler installed. Then:

```bash
git clone https://github.com/microfrosty/math-server.github.io.git
cd math-server.github.io
gem install bundler
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000` in your browser. Jekyll will watch for file changes and rebuild automatically — just refresh the page to see your edits.

---

## 2. Open an Issue

Issues are how we track bugs, content requests, and feature ideas.

1. Go to the [Issues tab](https://github.com/microfrosty/math-server.github.io/issues) on GitHub.
2. Click **New issue**.
3. Give it a clear title (e.g. *"Add post on the Banach–Tarski paradox"* or *"Fix broken MathJax on mobile"*).
4. Fill in the description — what the problem is, or what you'd like to see.
5. Submit.

Issues are automatically added to the project board via a GitHub Actions workflow, so no manual triage needed — it'll appear in the backlog the moment you file it.

---

## 3. Make a Pull Request

Never commit directly to `main`. The workflow is:

```bash
# 1. Create a branch
git checkout -b my-feature-or-post

# 2. Make your changes
# ...

# 3. Commit
git add .
git commit -m "Add post: contributing guide"

# 4. Push
git push origin my-feature-or-post
```

Then on GitHub:

1. You'll see a prompt to **Compare & pull request** - click it.
2. Write a short description of what you changed and why.
3. Link any related issue by writing `Closes #42` (or whatever the issue number is) in the description. This will automatically close the issue when the PR is merged.
4. Submit the PR and wait for review.

---

## 4. Write a New Post

All posts live in `_posts/` and must be named `YYYY-MM-DD-your-slug.md`.

### Pick the right front matter for your category

**Exploration or Misc post:**
```yaml
---
layout: post
title: "Your Title"
subtitle: "Optional subtitle"
date: 2026-04-14
categories: [exploration]   # or [misc]
tags: [tag1, tag2]
reading_time: 6
author: "Your Name"
tldr: "One sentence summary."
---
```

**Learning post:**
```yaml
---
layout: post
title: "Your Title"
subtitle: "Optional subtitle"
date: 2026-04-14
categories: [learning]
math_category: calculus     # see slugs below
tags: [calculus, limits]
reading_time: 8
author: "Your Name"
tldr: "One sentence summary."
---
```

**Book review:**
```yaml
---
layout: post
title: "Review: Proofs from THE BOOK"
date: 2026-04-14
categories: [books]
book_title: "Proofs from THE BOOK"
book_author: "Martin Aigner & Günter Ziegler"
book_year: 1998
book_publisher: "Springer"
rating: 5
author: "Your Name"
tldr: "One sentence summary."
---
```

### Available `math_category` slugs

`calculus` · `linear-algebra` · `number-theory` · `topology` · `probability-statistics` · `abstract-algebra` · `real-analysis` · `discrete-mathematics`

### Writing math

Inline: `$e^{i\pi} + 1 = 0$`

Display:
```
$$
\int_{-\infty}^{\infty} e^{-x^2}\,dx = \sqrt{\pi}
$$
```

Pre-defined macros: `\R` `\N` `\Z` `\Q` `\C` `\eps` `\d`

---

Once your post looks good locally, follow the PR steps above and it'll be reviewed and merged into the site.