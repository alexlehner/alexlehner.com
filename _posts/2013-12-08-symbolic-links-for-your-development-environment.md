---
layout: post
title: Symbolic Links For Your Development Environment
description: "Learn how to speed up your development workflow with Symbolic Links"
category: articles
tags: [git, links, mamp, symbolic, symbolic links]
redirect_from: "/symbolic-links-for-your-development-environment/"
---

If you do any local WordPress theme or plugin development, I think I can save you some precious time. When I was developing and testing WordPress themes I found myself having to manage more than 4 separate installations of WordPress per computer *(I regularly switch between 3)*.

## The Problem

Each time I wanted to update and test the code, I had to do it in several locations. Git, makes most of this simple, but shouldn’t there be a better way?

### Introducing Symbolic Links

Symbolic Links are a method to simulate the duplication of a folder in another directory. This means, any changes to the files will be reflected in all of the linked folders. This is perfect for local development environments as I want consistent themes and plugins accessible between all of my local sites. Here’s how it’s done:

#### Step 1: Create a "master" folder.

You can use any name you want, but keep it short. You can choose to have this be a simple directory with folders named “themes” and “plugins,” or have it be a full WordPress installation. Up to you! I chose to keep it simple.

#### Step 2: Clone and/or Copy all of the plugins and themes that you want installed on all of your sites.

This is where you will be hosting your primary repositories from now on. Make sure that you include any parent themes if you are building a child theme.

#### Step 3: Remove existing themes and plugins folders from wp-content/.

Go through your local WordPress installations and remove the “themes” and “plugins” directories. If you have several local sites, I recommend doing this with a single installation of WordPress first. Note: You are most likely going to need to reconfigure your theme and plugins after this process.

#### Step 4: Open Terminal

Here’s the basic syntax of the command  
`ln -s /Path/to/original/folder New-folder-name`  

Since the source files are within ~/git/master/ for my environment, here’s the best syntax for the task.  

`ln -s ~/git/master/themes ~/git/FOLDERNAME/wp-content/themes`  
`ln -s ~/git/master/plugins ~/git/FOLDERNAME/wp-content/plugins `

*Note: Replace “FOLDERNAME” with the appropriate directory structure for your folder configuration.*

#### Step 5: Test and repeat.

Either through Terminal or Finder, you should be able to see the themes and plugins you installed in the master directory. The same plugins and themes should be available in the WordPress admin interface.  

If all is working, repeat steps 3 - 5 with the rest of your WordPress installations.  

Cheers!  

Alex


