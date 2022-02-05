---
layout: post
title: The Right Way To Setup MAMP
category: articles
tags: [MAMP, local, git, apache, php, mysql]
redirect_from: "/a-good-development-environment-part-2-the-right-way-to-setup-mamp/"
---

One of the core apps that brings my development environment together is MAMP. Below I will discuss the best way I have found to configure MAMP.

<figure>
	<a href="{{ site.url }}/images/mamp-front.png"><img src="{{ site.url }}/images/mamp-front.png"></a>
	<figcaption>MAMP Interface</figcaption>
</figure>

Some assumptions:

* You know how to navigate around finder
* You have downloaded and installed MAMP
* You are familiar with the concepts of local development

## Getting Started

Welcome to the world of local development. Look forward to testing your sites without having to work on a production server.

Assuming you followed all of the instructions for MAMP, you probably stuck with the default location for all of your files. Isn’t it a pain to navigate to `Applications/MAMP/htdocs/` every time you want to open up a site locally? Well MAMP makes that super easy to change, but where is the best place? I’ll show you.

### 1. Make a new folder under your user directory for Apache

Open up finder and go to your home folder. It has a variety of default Mac folders such as Desktop, Documents, Downloads, etc. Go ahead and make a folder called “git”. I chose “git” because this is also where I store all of my projects that utilize git. *Note: you can use any folder name, but make sure that it is simple, without spaces. You could be typing it a lot.*

### 2. Change MAMP Apache settings

Launch MAMP, click Preferences, and go to the Apache tab. Then select the new folder you just created.

You may be asked for you Mac password. This is because MAMP is restarting Apache.

### 3. Change Some Other MAMP Settings

<figure>
	<a href="{{ site.url }}/images/mamp-start-stop.png"><img src="{{ site.url }}/images/mamp-start-stop.png"></a>
	<figcaption>MAMP Settings Panel</figcaption>
</figure>

These steps are not absolutely required, but can make your experience much smoother, especially when dealing with WordPress and other web applications heavily relying on Apache, PHP, and MySQL.

Under “Start/Stop”, your screen should have the following lines checked:

* [checked] Start Servers when starting MAMP
* [checked] Stop Servers when quitting MAMP
* [un-checked] Check for MAMP PRO when starting MAMP
* [checked] Open start page at startup
* Start page url: /MAMP/

Under “Ports”, click Set to default Apache and MySQL ports. It should have this configuration:

* Apache Port: 80
* MySQL Port: 3306

Under “PHP”, the defaults are usually fine. They are as follows:

* PHP Version: 5.5.10
* Cache: off

## Start Playing

Now that you have MAMP setup, it is time to test it. All you have to do is bring the various web files you have created and drop them in the git folder. Then you should be able to point your browser to: http://localhost/ and see files within the git directory.

To keep things organized, I recommend you separate your projects via folders. For example I am working on a project for a company called One George. By putting all of the work in a folder called “ onegeorge”, I am easily able to keep my projects organized and have simple URLs. To access that project from a web browser, all I have to do is append the folder name to localhost. For example: http://localhost/onegeorge/

For those tinkering with git, keeping things in this logical folder system will be a core part of your environment.

## Some Notes

There are a million different ways to run a local development environment. I have just found that this is the most efficient for the type of work that I do. Some extra notes I feel are important:

**Command Line Simplicity**

I mentioned using a simple folder name to house all of your website files. This is because the shorter and simpler the folder name is, the easier it is to access on command line. To navigate to the folder via terminal, all you have to enter is `cd ~/git`.

Once you start heavily start using git, this time saver is crucial.

**Navigation Simplicity**

It is very easy to drag and drop the git folder to your sidebar to access it more quickly.