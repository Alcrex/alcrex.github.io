---
layout: post
title: Building My Personal Website with GitHub Pages and Hexo
date: 2025-12-17 03:13:10 +0800
tags: Hexo
---
# Background

Before I entered university, I came across a content creator on Bilibili known as _“数字游牧人”_. Through his videos, I began to understand what frontend and backend development really are. I was also impressed by his beautifully designed personal blog:  
[SamuelQZQ Blog | Digital Nomad](https://www.qzq.at/)

As I moved my cursor across the page, the visual feedback and subtle interactions immediately caught my attention. Those visible, responsive details made me realize that building a website to present myself in this way was something I truly wanted to do.

Some time later, I joined the Mathematical Modeling Association at my university, where I met someone truly outstanding. After browsing his GitHub projects and visiting his personal website ([https://the0cp.cc/](https://the0cp.cc/)), my desire to build my own personal homepage became even stronger.

Through conversations with him, I realized that creating a personal website does not necessarily require a traditional setup involving a server, Docker, Nginx, and a backend project. Instead, solutions like **GitHub Pages + Hexo** can achieve the same goal with much lower learning and operational costs.

With guidance from ChatGPT and Google AI Studio, I built this website. This article is a review and record of that process.

---

# Process Review

## Preparation

Install two essential tools:

- **Node.js** (LTS version)  
    [https://nodejs.org/zh-cn](https://nodejs.org/zh-cn)
    
- **Git**  
    [https://git-scm.com/](https://git-scm.com/)
    

After installation, verify them using the command prompt:

```
node -v
git --version
```

If version numbers are displayed, the environment is ready.

---

## Creating a GitHub Repository

The repository name **must** be:

`name.github.io`

Where `name` is your GitHub username.

For example, if your GitHub username is `Alcrex`, the repository name should be:

`alcrex.github.io`

Make sure the repository is set to **Public**.

---

## Setting Up the Blog Locally (Hexo)

### 1. Install Hexo CLI

Run the following command in the command prompt:

```
npm install -g hexo-cli
```

---

### 2. Initialize the Blog Directory

Choose a location with sufficient disk space and create a folder for your blog (e.g., `myblog`).

In my case, I created the folder on the **D:** drive, so I ran:

```
D:
hexo init myblog
cd myblog
npm install
```

---

### 3. Preview Locally

Start the local server:

```
hexo s
```

The terminal will prompt you to visit `http://localhost:4000`.  
You can hold **Ctrl** and click the link to open it in your browser.

After previewing the default Hexo page, press `Ctrl + C` in the terminal to stop the server.

---

## Deploying the Blog to GitHub

### 1. Install the Deployment Plugin

Inside the `myblog` directory, run:

```
npm install hexo-deployer-git --save
```

---

### 2. Modify the Configuration File

Open the `_config.yml` file in the `myblog` directory using VS Code.

Scroll to the bottom and modify the `deploy` section as follows  
(**note the space after the colons**):

```
deploy:
  type: git
  repo: https://github.com/Alcrex/alcrex.github.io.git
  branch: main
```

---

### 3. Generate and Deploy

Run the following commands:

```
hexo g   # Generate static files
hexo d   # Deploy to GitHub
```

---

## Done

When the terminal displays `Deploy done`, the deployment is complete. 🎉