---
title: "Creating my blog with Hugo"
date: "2024-05-31T12:56:41+10:00"
ShowToc: true
TocOpen: true
# description:
# summary:
draft: true
---

## Introduction

I've decided to make a website/blog where I can talk about security and other bits of technology I find interesting. As I near the end of my university studies, I want to start creating content to cement my learning and also provide some value to others. This is a deep interest of mine, and I think it would be very beneficial to share my insights and experiences with a broader audience.

## Why Hugo?

After exploring various options, I've decided to use Hugo, a static site generator written in Golang, which is super fast at building websites. Here are some key reasons for choosing Hugo:

1. **No Backend Database**: Everything in Hugo is written in Markdown, configured with YAML, and templated with the Go templating language. This simplicity reduces complexity and potential points of failure.
2. **Edge Deployment**: Hugo sites can be deployed on the edge using a CDN such as Netlify. This ensures fast content delivery to users, no matter where they are.
3. **Cost-Effective**: Given the expected usage of my blog for the foreseeable future, Hugo is the most cost-effective option. It avoids the overhead associated with CMS options like WordPress.
4. **Security**: CMS platforms like WordPress are notoriously slow, clunky, and prone to security vulnerabilities (especially PHP-based ones). Hugo minimizes the attack surface of the website because, during the CI/CD build process, a new post is converted from Markdown to static HTML and CSS. There is no database to enumerate and no room for injection attacks.
5. **Control Over Content**: Using Hugo instead of website builders like SquareSpace gives me more control over my content and the overall structure of my site.

## Getting Started with Hugo

If you would like to install Hugo and play around, here is a quick start guide:

### Installing Hugo

First, ensure that Go is installed on your system by following the instructions at [Go Installation Guide](https://go.dev/doc/install).

Then, install Hugo using the following commands:

#### On Debian-based Systems

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install hugo
```

#### Compatability Issues on Debian-based Systems

I've encountered compatibility issues with the Debian-based packages as they are often behind in their software versions. If you're having compatibility issues, download the latest release from the [Hugo GitHub release page](https://github.com/gohugoio/hugo/releases).

Download the relevant file (for me it was `hugo_extended_0.126.2_linux-amd64.deb`). You definitely want to install the extended version to take advantage of all the features.

Also, download the checksum file, for me it was: `hugo_0.126.2_checksums.txt`.

To ensure the integrity of the downloaded file, verify the file hash against the checksum. Here are the commands to do this:

1. **Download the Hugo .deb file and checksum file:**

```bash
wget https://github.com/gohugoio/hugo/releases/download/v0.126.2/hugo_extended_0.126.2_linux-amd64.deb
wget https://github.com/gohugoio/hugo/releases/download/v0.126.2/hugo_0.126.2_checksums.txt
```

2. **Calculate the SHA256 hash of the downloaded .deb file:**

```bash
sha256sum hugo_extended_0.126.2_linux-amd64.deb
```

3. **Check the calculated hash against the checksum file:**

```bash
grep hugo_extended_0.126.2_linux-amd64.deb hugo_0.126.2_checksums.txt
```

If the output of sha256sum matches the hash listed in the checksum file, the download is verified.

4. **Install the downloaded Hugo package:**

```bash
sudo dpkg -i hugo_extended_0.126.2_linux-amd64.deb
```

This ensures you have the latest version of Hugo with all the extended features.

### Creating a New Hugo Site

Create a new Hugo site using the YAML format (avoiding TOML for simplicity):

```bash
hugo new site MyNewSite --format yaml
```

### Running Your New Site

Navigate to your new site's directory and start the Hugo server:

```bash
cd MyNewSite
hugo server
```

Just like that, you have a Hugo development server running a local live website. You can now start customizing your site and adding content.

### Themes and deployment

You can access a ton of prebuilt themes for Hugo at [Hugo Themes](https://themes.gohugo.io/). These themes can give your site a professional look with minimal effort.

To deploy your site, follow the instructions provided at [Hugo Hosting and Deployment](https://gohugo.io/hosting-and-deployment/). This guide covers various hosting options and the steps needed to get your site live.

### Further Documentation

For more detailed information and advanced usage, refer to the [Hugo Documentation](https://gohugo.io/documentation/).

## Final Thoughts

Creating a blog with Hugo is a straightforward and efficient way to share your knowledge and interests with the world. By leveraging the power of static site generation, you can build a fast, secure, and easily maintainable website. I hope this guide helps you get started on your own Hugo journey!

And that's about it.

Signing off,

_Kobe_
