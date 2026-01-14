---
creation date: 2026-01-14 06:56
modification date: Wednesday 14th January 2026 06:56:40
math: true
categories:
- project-notes
- how-to
- meta
- tools-I-like
tags: 
- Docker
- Docker Compose
- Virtualisation
- Containers
- Data Engineering

layout: post
title: "Co-ordinating your Docker Containers with Docker Compose"
---


**Technologies:** Docker, Docker Compose, Python, PostgreSQL  
**Role:** Developer / Data Engineer

---

## Synopsis 

Here I talk about my experiences with **Docker** and **Docker Compose**, and explain both how and why to use them when deploying applications. I believe Docker is the perfect technology for rapidly deploying software to a system with minimal headaches, and Compose allows your containers to easily interact, creating a cohesive system rather than a collection of isolated scripts. 

--- 
## Why I tried Docker and the problems it solved for me 

I started a [Hacker News Analytics]({{ "/posts/Analysing-Hacker-News/" | relative_url }}) project to try and track tech trends (like the sudden spike in "AI" mentions versus "Rust" or "Java"). The focus was mainly on data collection from the Hacker News API, but later I needed to work on a GUI for interacting with the dataset. I found that I wanted a few things. Firstly, to be able to run my project on a dedicated device since my desktop was running out of storage space. I also found that working on the project on my personal device made me more cautious and unwilling to experiment, I didn't want to brick my PC after all. Luckily the [Scraping tool](https://github.com/teddy-mcdermott/hacker-news-analytics/blob/main/Scraper/README.md) I'd made was really effective, and with only needing 2 hours or so to completely reacquire the dataset, I felt comfort in knowing I could make my mistakes and easily start again. I bought a [Mini PC](https://support.hp.com/sg-en/product/details/hp-elitedesk-800-35w-g3-desktop-mini-pc/15234602) to host the project, specifically in an Ubuntu virtual machine. Secondly, I didn't want to have to spend a lot of time setting up the sever each time. I wanted to **easily pull from GitHub and say "Go" to my project**. This is what Docker gets you.

--- 

## Using Docker and Docker Compose 

**[Tutorial goes here]**

--- 

## What tools help me to use Docker? 

* **Docker Desktop / Engine:** The core runtime. 
* **Docker Hub:** For pulling official images (like `postgres:alpine`) to keep the footprint small. 
* **DBeaver:** To connect to the containerized database and verify the Hacker News data was being stored correctly. 

--- 

## When to use Compose vs Docker containers on their own 

While `docker run` is great for a quick test of a single tool, **Docker Compose** is the right choice as soon as you have two moving parts. 

--- 

## Key commands to memorise 

| Command                                       | Purpose                                                            |
| :-------------------------------------------- | :----------------------------------------------------------------- |
| `docker-compose up -d`                        | Start the whole stack in the background (detached).                |
| `docker-compose logs -f`                      | Follow the output of your app (great for debugging).               |
| `docker-compose down -v`                      | Stop everything and **delete** volumes (useful for a fresh start). |
| `docker-compose exec [service name] [command] | Jump directly into the container's terminal to run commands.       |

---

## What I Learned

Transitioning to Docker for this project changed how I think about infrastructure. It turned my setup process into code that lives in my GitHub repo, which was a huge time save.



--- 
## Links and References 
- [Docker Compose Guide](https://docs.docker.com/compose/)
- [The project I speak about in this article](https://github.com/teddy-mcdermott/hacker-news-analytics) 
- [Hacker News API Documentation](https://github.com/HackerNews/API) 
- [Portainer: A docker interface tool that I didn't use, but will try in the future](https://www.portainer.io/)