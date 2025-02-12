# Sync Savings Integration Guide

## Introduction

This repo serves as the integration guide for Distributors that want to use the [UI plugin](https://github.com/SyncSavings/ui-plugin/). It exists to clearly communicate the requirements for those wanting to use the UI Plugin.

## Building and previewing your site locally

### Setup

1. Install Ruby - use [CHRuby] to get version 3.3.5
2. Install [Jekyll]
3. Install [Bundler]

### Running locally

1.  Change your working directory to the root directory of your site.

2.  Run `bundle install`.

3.  Run `bundle exec jekyll serve` to build your site and preview it at `localhost:4000`.

    The built site is stored in the directory `_site`.

## Customization

[Browse the documentation][Just the Docs] to learn more about how to use this theme.

## Licensing and Attribution

This repository is licensed under the [MIT License]. You are generally free to reuse or extend upon this code as you see fit; just include the original copy of the license (which is preserved when you "make a template"). While it's not necessary, we'd love to hear from you if you do use this template, and how we can improve it for future use!

The deployment GitHub Actions workflow is heavily based on GitHub's mixed-party [starter workflows]. A copy of their MIT License is available in [actions/starter-workflows].

----

[^1]: [It can take up to 10 minutes for changes to your site to publish after you push the changes to GitHub](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site).

[CHRuby]: https://github.com/postmodern/chruby
[Jekyll]: https://jekyllrb.com
[Just the Docs]: https://just-the-docs.github.io/just-the-docs/
[Bundler]: https://bundler.io
[MIT License]: https://en.wikipedia.org/wiki/MIT_License
[starter workflows]: https://github.com/actions/starter-workflows/blob/main/pages/jekyll.yml
[actions/starter-workflows]: https://github.com/actions/starter-workflows/blob/main/LICENSE
