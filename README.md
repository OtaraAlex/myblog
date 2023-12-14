# My Blog

This repository contains files of my personal blog website made using Hugo, a static site generator and the [Blowfish theme](https://github.com/nunocoracao/blowfish)

# Intro

There are several static site generators out there that you can choose from, for instance, *Jekyll*, *Hugo*, *Gatsby* and *Next.js*.

In this demo we will mainly focus on **Hugo**, which is written in the **Golang** language.

![hugo-logo-wide](https://github.com/OtaraAlex/myblog/assets/111053808/4499dc6b-7cab-4942-b8c1-aeb9beb27d27)

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

# Using a free Hugo template to generate your blog

Using Hugo comes with the advantage of having access to a variety of free beautiful themes. You can use these [themes](https://themes.gohugo.io/) to make your website. This lets you focus on sharing your content with the world and not dwell to much on designing.

We are going to use a theme called [blowfish](https://blowfish.page/) the very theme used on this site. It uses markdown files for content and yaml for configuration files. It is also very customizable to your preference.

![blowfish_logo_transparent](https://github.com/OtaraAlex/myblog/assets/111053808/68db9f25-5040-40b9-a80b-b6609ca182ef)

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

# Configuring the Theme
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

Voila. Your website is up in development!
