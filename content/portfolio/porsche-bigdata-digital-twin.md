---
title: "Porsche Digital Twin"
date: 2019-11-05T16:47:50+01:00
image: "images/portfolio/porsche-bigdata-digital-twin.png"
description: "This is meta description."
author: "Justin Güse"
---
> "A digital twin is a digital replica of a living or non-living physical entity."

Source: https://en.wikipedia.org/wiki/Digital_twin

A digital twin in marketing is a user that is similar to a user that has already been on your website.
This is done because you are already knowing what products or pages the user viewed and can offer a similar using the same experience.
But how is this done?

## Big Data aspects of a digital twin

First, we saved all the web events of our websites in a No-SQL database called Elasticsearch. Elasticsearch is a great application for text-based search and quick queries on huge databases using Lucene.

### Graph search in Elasticsearch

Simplified, we used a graph search that is integrated into Elasticsearch (see https://www.elastic.co/de/what-is/elasticsearch-graph) to find users that are similar to the current user. Via REST-API calls with the matching Lucene queries, similar products from digital twins were extracted, and presented as recommendations to the current user.

### Challenges using Elasticsearch for Digital Twins

A huge challenge in this scenario has been speed. Users usually leave a website if it loads longer than 250ms. This expands drastically, with 11% of the users leaving after one second loading time, and around 90% with more than four seconds of loading time (Source: https://think.storage.googleapis.com/docs/mobile-page-speed-new-industry-benchmarks.pdf). Therefore we had to optimize the Elasticsearch cluster and partly simplify our queries to achieve a loading time of around 200ms. How? Leave a message below or contact me to find out more. 

Did you ever use Elasticsearch for Digital Twins? Do you want to find out how you can build digital twins and matching recommendations for your customers? Leave a message in the comments below or message me directly.
