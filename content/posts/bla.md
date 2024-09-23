+++
title = 'Example Post'
date = 2023-01-15T09:00:00-07:00
draft = false
tags = ['meta']
+++

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

> quote to inflate the word count

*italicize text for a slant*

**bold a bold claim**

`monospace code because robots speak in monotone`

```js
name: Deploy Hugo site to Neocities

on:
  # Runs on pushes targeting the default branch
  push:
    branches:
      - main

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "deploy-to-neocities"
  cancel-in-progress: false

# Default to bash
defaults:
  run:
    shell: bash

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    env:
      HUGO_VERSION: 0.134.3
    steps:
      - name: Install Hugo CLI
        run: |
          wget -O ${{ runner.temp }}/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
          && sudo dpkg -i ${{ runner.temp }}/hugo.deb          
      # - name: Install Dart Sass
      #   run: sudo snap install dart-sass
      - name: Checkout
        uses: actions/checkout@v4
        with:
          submodules: recursive
          fetch-depth: 0
      - name: Install Node.js dependencies
        run: "[[ -f package-lock.json || -f npm-shrinkwrap.json ]] && npm ci || true"
      - name: Build with Hugo
        env:
          # For maximum backward compatibility with Hugo modules
          HUGO_ENVIRONMENT: production
          HUGO_ENV: production
        run: |
          hugo \
            --gc \
            --minify \
            --baseURL "${{ steps.pages.outputs.base_url }}/"
      - name: Archive artifact
        uses: actions/upload-artifact@v4
        with:
          name: site
          path: public
  # Deployment job
  deploy:
    runs-on: ubuntu-latest
    environment: neocities
    needs: build
    steps:
      - name: Download artifact
        uses: actions/download-artifact@v4
        with:
          name: site
          path: public
      - name: Deploy to neocities
        uses: bcomnes/deploy-to-neocities@v2
        with:
          api_token: ${{ secrets.NEOCITIES_API_TOKEN }}
          cleanup: true
          dist_dir: public
```

