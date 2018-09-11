# Snyk Documentation

Preview url: https://snyk.github.io/docs/

## Getting set up

1. Pull down the repo
2. In the command line, navigate to the repo's folder and run `bundle install`
3. If there are no errors, run `bundle exec jekyll serve`
4. Go to **http://localhost:4000/docs/** in your browser

Check out the [Markdown-cheatsheet](https://github.com/Snyk/general/wiki/Markdown-cheatsheet) for how to write content.

### Saving drafts

If you want to preview a file but not let the changes show on production, add this line to the YAML front-matter:

```
---
draft: true
---
```

This will add a "draft" label and background colour.

### Hide a title

To not show the title (such as on a landing section), add this line to the YAML front-matter:

```
---
title: ""
---
```

### Add inline code

For inline code, such as a word, use a single backtick.

### Add code blocks

To wrap some code in a code block, use 3 backticks before and after the text.
