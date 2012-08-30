---
layout: post
title: "How to setup Octopress & deploy to GitHub?"
date: 2012-08-30 17:39
comments: true
categories: setup
---

Install Git.
Install Ruby 1.9.3 using either rbenv or RVM.
If ruby --version doesn’t say you’re using Ruby 1.9.3, revisit your rbenv or RVM installation.

Setup Octopress

git clone git://github.com/imathis/octopress.git octopress
cd octopress    # If you use RVM, You'll be asked if you trust the .rvmrc file (say yes).
ruby --version  # Should report Ruby 1.9.3
Next, install dependencies.

gem install bundler
rbenv rehash    # If you use rbenv, rehash to be able to run the bundle command
bundle install
Install the default Octopress theme.

rake install

rake new_post["My First Post"]
rake new_post["My Second Post"]
rake generate
rake watch
rake preview

http://localhost:4000

Deploying to Github Pages
1. create github repository wavejava.github.com, and check http://wavejava.github.com
2. rake setup_github_pages
Ask you for your Github Pages repository url.
Rename the remote pointing to imathis/octopress from ‘origin’ to ‘octopress’
Add your Github Pages repository as the default origin remote.
Switch the active branch from master to source.
Configure your blog’s url according to your repository.
Setup a master branch in the _deploy directory for deployment.

git@github.com:wavejava/wavejava.github.com

3. rake generate
rake deploy

4. commit the source for my blog 
git add .
git commit -m 'your message'
git push origin source

==========
Configuring Octopress
_config.yml : Blog Configuration




