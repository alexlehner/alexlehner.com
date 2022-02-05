---
layout: post
title: Local git and Jekyll tip
category: articles
tags: [git, jekyll, terminal]
---

A couple of weeks ago this site was rebuilt using [Jekyll](http://jekyllrb.com/) and moved to [Github Pages](https://pages.github.com/). If you want to learn more about Jekyll + Github, checkout the [Github site](https://help.github.com/articles/using-jekyll-with-pages).

I kept running into an issue with needing a different `site.url` configuration for my local environment and my production (in this case GitHub) environment. Fortunately Jekyll makes this easy to overcome by allowing you to have multiple config files. Here's how:

## Make a new config file

Start by making and saving a new file called `_config-dev.yml`. This file will be used to trump any declarations we need to for our local environment. It also could be named [zaphodBeeblebrox](http://en.wikipedia.org/wiki/Zaphod_Beeblebrox "Wikipedia:Zaphod Beeblebrox").yml for all it really mattered. For now just include the following:

~~~ ruby
url:              http://localhost:4000
~~~

## Relaunch Jekyll

Traditionally your command to start Jekyll looks something like this: 

~~~ ruby
jekyll serve -w
~~~

This by default looks for the `_config.yml` in your site folder and rebuilds your site as you make changes to the files. Instead, launch Jekyll with the following:

~~~ ruby
jekyll serve -w --config _config.yml,_config-dev.yml
~~~

## Test

Jekyll does a good job of telling you if your syntax is messed up somewhere. If you don't get any errors on launch, you should be able to see your site at [http://localhost:4000/](http://localhost:4000/).

## Add config file to .gitignore (optional)

The `_config-dev.yml` file isn't going to hurt anything by having it in your Github repo. By default Github Pages won't even notice it. I would recommend you add it to your .gitignore file anyway. One less file in your git repo to keep track of and confuse potential forkers. [Need help?](https://help.github.com/articles/ignoring-files "Github Help: Ignoring files")

---

I hope this quick tip helps someone out. If you have any questions, ping me on twitter ([@alexjlehner](https://twitter.com/AlexJLehner "Alex on Twitter")) or [email me](mailto:alex@lifelikegeek.com).
