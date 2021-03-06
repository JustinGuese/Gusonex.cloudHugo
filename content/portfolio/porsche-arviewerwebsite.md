---
title: "Porsche AR Viewer Website"
date: 2019-11-05T16:47:50+01:00
image: "images/portfolio/porsche-arviewerwebsite.png"
description: "This is meta description."
author: "Justin Güse"
---
The website for the Porsche AR Viewer (http://www.discovar.at) had special requirements. For once, security guidelines for the Porsche Holding are immensely high, and second, a solution was needed to host the website at a minimal cost. Both challenges were solved in their own way.

## Security Guidelines

The first approach has been a classic CMS hosted on a LAMP stack, but soon the guidelines regarding hosting blew the budget. Another solution was needed. I proposed the idea of a static website hosted on an AWS S3 bucket because without a CMS or any dynamic parts of the website (PHP, ...) the website becomes "serverless" and therefore basically unhackable. The website was programmed by myself using HTML5 and Bootstrap.

## Hosting websites at a minimal cost

There was barely any budget for hosting. Together with the aforementioned conditions, a classic server setup was not thinkable of. Together with the security guidelines, I decided to host the static website on an AWS S3 bucket, which means that you are basically only paying for the usage, or in other words if someone views the website, instead of paying a fixed monthly cost. Additionally, the AWS includes a "free tier limit", which is a monthly free amount of storage and transmission that is included in your account for free - and therefore oftentimes resulting in a website hosted for free.

What are your experiences with static websites? Do you have a web project that might need speed, security and cost improvement? Comment below or write me a direct message.
