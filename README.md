# Micromass Athenæum

A Jekyll-based mathematics blog with four main sections: **Exploration**, **Learning**, **Books**, and **Misc**.

## Features

- 🧮 **Full LaTeX rendering** via [MathJax 3](https://www.mathjax.org/) — inline `$...$` and display `$$...$$` math
- 📚 Eight math topic categories in the Learning section
- 📖 Book reviews with rating and metadata cards
- 🌑 Dark editorial theme with Playfair Display typography
- 📱 Responsive mobile layout

## Getting Started

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000`.

## Writing Posts

Create a file in `_posts/` named `YYYY-MM-DD-slug.md`.

### Front matter for a Learning post

```yaml
---
layout: post
title: "Your Title"
subtitle: "Optional subtitle"
date: 2024-01-01
categories: [learning]
math_category: calculus   # slug from _config.yml math_categories
tags: [calculus, limits]
reading_time: 8           # in minutes
tldr: "One-sentence summary"
---
```

### Front matter for a Book review

```yaml
---
layout: post
title: "Review: Book Title"
date: 2024-01-01
categories: [books]
book_title: "Full Book Title"
book_author: "Author Name"
book_year: 1979
book_publisher: "Publisher"
rating: 5
---
```

### Using LaTeX

Inline math: `$e^{i\pi} + 1 = 0$`

Display math:
```
$$
\int_{-\infty}^{\infty} e^{-x^2}\,dx = \sqrt{\pi}
$$
```

Pre-defined macros (set in `_layouts/default.html`):
- `\R` → ℝ, `\N` → ℕ, `\Z` → ℤ, `\Q` → ℚ, `\C` → ℂ
- `\eps` → ε (varepsilon)
- `\d` → roman d (for differentials)

## Section Categories

| Section | `categories` value |
|---|---|
| Exploration | `[exploration]` |
| Learning | `[learning]` |
| Books | `[books]` |
| Misc | `[misc]` |

## Math Topic Slugs (for `math_category`)

`calculus` · `linear-algebra` · `number-theory` · `topology` · `probability-statistics` · `abstract-algebra` · `real-analysis` · `discrete-mathematics`

## Structure

```
math-server/
├── _config.yml
├── _layouts/
│   ├── default.html   # base layout with MathJax
│   ├── post.html      # article layout
│   └── page.html      # section index layout
├── _includes/
│   ├── header.html
│   ├── footer.html
│   └── post-card.html
├── _posts/            # all blog posts
├── assets/
│   ├── css/main.css
│   └── js/main.js
├── exploration/index.html
├── learning/index.html
├── books/index.html
├── misc/index.html
└── index.html
```
