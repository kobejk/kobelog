---
title: "hello hugo"
date: 2023-03-23T13:48:26+11:00
draft: false
---

Hey, so I've been messing around with web stuff for a while now and I finally decided to put my skills to the test and publish some content online. My main reasons were to have a central place for all the interesting stuff I find, to create a personal documentation space for myself, and to show off what I can do to potential employers.

But, I quickly realized that creating a website from scratch using plain HTML and CSS was going to be a lot of work. So, I checked out some examples online and found out that almost half of all websites run on WordPress. It seemed like the perfect solution since it manages website posts so well.

However, as someone who has some experience with web security, I know that WordPress can have security vulnerabilities if not kept up-to-date. Plus, I noticed that WordPress sites can be a little slow sometimes. 

That's when I stumbled upon Hugo, a website framework built in Golang. Apparently, it's the "world’s fastest framework for building websites". Hugo generates static sites from Markdown, which means there are no dynamic elements or JavaScript on the page. This not only speeds up page loading times, but also reduces the risk of web attacks since there's no way to perform Code Injection.

So how did I do it?

* [[Installing Hugo]](#installing-hugo)
* [[Creating a Hugo site]](#creating-a-hugo-site)
* [[Installing a Theme]](#installing-a-theme)
* [[Viewing the website]](#viewing-the-website)
* [[Creating a post]](#creating-a-post)
* [[Building the website]](#building-the-website)

***

# Installing Hugo

To install hugo, visit the [hugo website](https://gohugo.io/) and click "quickstart". Alternatively, keep reading.

I installed hugo on [WSL2](https://learn.microsoft.com/en-us/windows/wsl/install) so the code instructions will be targeted at Debian based linux distributions.

To install, simply enter the following command in the terminal:

```bash
sudo apt update && sudo apt install hugo
```

Wait for the download to complete, and confirm you have hugo installed with the following command:

```bash
hugo -h
```

If installed correctly, you should see a list of hugo commands populate the screen. If not, refer to the install output and check for errors.

<!-- [[Top]](#hello_HUGO) -->

# Creating a Hugo site

To create a hugo site, enter the following command in the terminal.

```bash
hugo new site name-of-your-site
```

This should create a site folder by the name you entered.

There are other options for creating a site and if interested, you should read the Hugo docs.

<!-- [[Top]](#hello_HUGO) -->

# Installing a theme

In order to view any content on the page, you will first need a theme.

There are over 200 themes on [Hugo Themes](https://themes.gohugo.io/). Simply pick one and follow the instructions for install.

The theme currently being used on this website is the [no-style-please theme](https://themes.gohugo.io/themes/hugo-theme-nostyleplease/). This theme is ported from Jekyll and contains less than 1kb of CSS. The theme is also responsive to system light/dark mode settings.

To install this theme, simply enter the following command in the hugo folder you created earlier:

```bash
git clone https://github.com/Masellum/hugo-theme-nostyleplease.git themes/nostyleplease
```

To use the theme, open the `config.toml` file and add the following line to the end of the file:

```toml
theme = 'nostyleplease'
```

<!-- [[Top]](#hello_HUGO) -->

# Viewing the website

You can view the website by running the development server with the following command:

```bash
hugo server
```

This will create a local server running on `localhost:1313` which shows live edits to your pages. 

**NOTE: This will not show pages marked as drafts. Check the "Creating a post" section to learn how to unmark draft pages.**

# Creating a post

To create a post, enter the following command: 

```bash
hugo new about.md
```

This will create an "about.md" Markdown file in the `/content` directory of the Hugo folder.

Open this file and change `draft = true` to `draft = false`. This will make your page visible on the test server.

Add some content and watch it populate.

# Building the website

Once you have finished writing your content, you can build the site with the following command:

```bash
hugo
```

This will create all the HTML and CSS necessary for the site to function in the `/public` directory of the hugo folder.

Add the files to a hosting provider of your choice and you're good to go.

For a more in-depth explanation on Hugo, read their docs at 
[hugo.io](https://gohugo.io/documentation/).

