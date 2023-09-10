---
title: Create Your Blog with Hugo's Static Site Generator
slug: static_sites
summary: In this post we go over the ease of creating a site using SSGs
description: In this post we go over the ease of creating a site using Markdown
date: 2023-09-09T16:08:27+03:00
categories: [Technical]
tags: [Static Site Generators, Hugo, Blowfish]
draft: false
---

Greetings 👋. In this blog post we will cover;

 * What a static site generator is
 * Intro to Hugo
 * Using a free Hugo template to generate your blog

Alright, let’s get right into it!

## What is a static site generator?

A static site generator or SSG is defined as being

 *"A script which takes in data, content and templates, processes them, and outputs a folder full of all the resultant pages and assets."*

Now to break down this definition we can travel back in time before the era of SSG. In a `traditional` web server, when a user visits a page the server builds the content of that specific page using the underlying stack like PHP by fetching data from either the database or an API. The server then returns this result to the users browser and voila you have a website. These kinds of websites are referred to as `dynamic` websites. In contrast we have static websites that have `stable` content i.e the content viewed by all the users is the same (`static`).

Static site generators therefore take the data provided to them in this case a blog like this one written in either markdown, yaml or any specific format and parse it into a static website.

<!-- ![ssg-host-flow](https://github.com/OtaraAlex/portfolio_website/assets/111053808/53a9fdc2-5ce4-421e-85a6-a2f3fd7e5e79) -->

## Why use a site generator?

There are a couple of reasons but just to mention a few

 * **Static sites are fast**. Since they don’t require a database and they pre-build all the pages, users can access content blazingly fast.
 * **Ease of deployment**. Since these sites are static they essentially don’t need a complicated sever setup
 * **They are very cost effective**. The server resources used are minimal since there is no database and the content is already prebuilt.
 * **Version Control**. Since the entire site is a combination of files and folders, you can leverage GIT to keep track of changes and collaborate with others.

## Intro to Hugo

There are several static site generators out there that you can choose from like *Jekyll*, *Hugo*, *Gatsby* and *Next.js*.

In this blog post we will mainly focus on **Hugo**, which is written in the **Golang** language.

<!-- ![hugo-logo-wide](https://github.com/OtaraAlex/portfolio_website/assets/111053808/18d68bcb-694d-4b44-98d4-6be06f66db12) -->

For the purposes of this demo we will be using a linux machine. I will attach alternative guidelines for different platforms.

To get started, install Hugo as below

``````
sudo apt install hugo
``````

For installation on Windows or MacOS follow the guide [here](https://gohugo.io/installation/).

After successfully installing Hugo you will have access to the hugo command in your terminal with which you can create your first site

``````
hugo new site mywebsite
``````

This command will create a directory, `mywebsite`, in the root directory.

## Using a free Hugo template to generate your blog

Using Hugo comes with the advantage of having access to a variety of free beautiful themes. You can use these [themes](https://themes.gohugo.io/) to make your website. This lets you focus on sharing your content with the world and not dwell to much on designing.

We are going to use a theme called [blowfish](https://blowfish.page/) the very theme used on this site. It uses markdown files for content and yaml for configuration files. It is also very customizable to your preference.

<!-- ![blowfish_logo](https://github.com/OtaraAlex/portfolio_website/assets/111053808/6dca4945-748a-4209-87ad-b047a878ea80) -->

To install this theme we will set it up a submodule in our hugo generated website.

``````
cd mywebsite
git init
git submodule add -b main https://github.com/nunocoracao/blowfish.git themes/blowfish
``````

We are doing this mainly so that we can pull changes from the main blowfish repository in case they ever make important changes to the theme using.

``````
git submodule update --remote --merge
``````

## Configuring the Theme
Blowfish does not constrain you on how to organize your content. An example of how to structure your content is as follows

``````
.
├── assets
│   └── img
│       └── author.jpg
├── config
│   └── _default
├── content
│   ├── _index.md
│   ├── about.md
│   └── posts
│       ├── _index.md
│       ├── first-post.md
│       └── another-post
│           ├── aardvark.jpg
│           └── index.md
└── themes
    └── blowfish
``````   

There are numerous ways you can edit the theme to suit your needs read this [documentation](https://blowfish.page/docs/getting-started/) to find out how.

Run this command locally to view your site.

``````
hugo server
``````

## Conclusion
In this article we covered what static site generators are, went over examples and specifically targeted Hugo. 

We got to see how to use a free Hugo theme to implement a blog website and finally we served the website locally. It should be noted that from here you can easily deploy your website with Netlify for free in just a few simple [steps](https://docs.netlify.com/integrations/frameworks/hugo/).

Voila! You have now set up a website with little to no coding.

Reach me on email or any of my social media handles if you have any questions or just want a chat :)
