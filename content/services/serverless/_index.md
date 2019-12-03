---
title: "Serverless & Microservices"
date: 2019-05-12T12:14:34+06:00
description: "This is meta description."
---

>  “No server is easier to manage than no server.", [Werner Vogels, Amazon CTO, AWS re:Invent 2015](https://en.wikipedia.org/wiki/Werner_Vogels)

#### Do you want to use serverless as well?


[Get a free 15 minute consultation!](/contact)
No matter if it is a website, a web application or databases, let us have a chat!


### This website is running Serverless

Like Werner Vogels said during re:Invent 2015, "no server is easier to manage than no server". But what does this mean, and why <strong>is this website so fast?</strong>

<img src="/images/portfolio/gusonex-cloud.png"
     alt="Google Pagespeed Score of 100"
     style="float: middle; width:50%" />


Do you believe me if I tell you that this website has no classic server architecture running in the background? And that it easily achieves a [Google Pagespeed Score of 100%](https://developers.google.com/speed/pagespeed/insights/?url=www.gusonex.cloud) with a loading time of ~0.3 seconds in Desktop?

But what is serverless and why did I choose it for this website? Let us start with the basics.

### What is serverless?

First things first, of course, there still is a server in the background, because we did not yet manage to run websites on real clouds. But the huge difference is, that I as an end-user to not have to set up any LAMP or other server environments, and instead just worry about my code. What are the things I usually have to manage whilst running a website?

- 1. **Keep the server hardware running**: Every component of your computer can fail. Add backups and redundancy to this and you are quite busy ordering server components
- 2. **Update your operation system**: Every major operation system discovers new vulnerabilities and fixes them with updates. This is a major security step that needs to be done. Unfortunately are some updates crashing your code, meaning each update needs to be carefully reviewed beforehand.
- 3. **Update your runtime**: If your software is using Java for example, it is mandatory for the same reasons as in point two, to update your software. This can cause crashes of your code as well.
- 4. **Security considerations**: Let us say you want to publish a machine learning environment into a productive stage. A Data Scientist should be able to manage this, but usually they do not have a huge background in server security and might fail to implement security precautions.
- 5. **Scaling**: If your website grows in size, your old server might easily crash due to the high demand. This can result in a lot of unsatisfied customers, or failed orders. With serverless additional servers are automatically added in the background if the demand is growing, and automatically subtracted to save costs.
- 6. **Your application**: Finally, after fulfilling all the other steps, you can worry about your code and application.

As you can see, a lot of effort is required to run code on traditional architectures. With serverless all but the last step are managed by a provider, meaning you can simply focus on your code, and do not worry about updates, maintenance and other things to be done in the background. Serverless and Microservices both have a huge potential in the future and can help to save costs, avoid downtimes and greatly improve performance.

### How does this website run serverless?

I am using the static hosting option of AWS S3, where you can host HTML code, transforming it into a serverless hosting model. One downside with this is of course, that I can not execute "dynamic code", like for example PHP like it is used in WordPress.
But WordPress and co are so popular you might say, why take the effort to write static HTML code?
I still decided to go down the "static" route, because with it **many benefits** arise.

### Benefits of hosting a Blog or Website serverless:

- 1. **Autoscaling**: No matter how many visitors are on my website, it will always allocate the matching resources in the background. AWS S3 does a great job in autoscaling and always delivering the right amount of processing power to deliver the best performance.
- 2. **Security**: This website is simply not hackable. Goodbye to SQL-injections and other vulnerabilities. As there is no dynamic part the only thing hackable is the AWS account. All the patching and updating happens on AWS's part in the background.
- 3. **Insane speeds**: Whilst WordPress and others need to render webpages this website is written in pure HTML. This means the content can directly be displayed on the device without the "pre-calculating"-step in-between that takes up a lot of time. This is why this website loads in milliseconds. In order to make it available worldwide at the same speeds, I have added CloudFront, AWS's CDN to deliver this website worldwide in milliseconds and to add a free SSL certificate (the green icon at the top bar).
- 4. **Hosting for free**: Whilst you would have to pay around 50 USD per month in hosting fees to achieve the same speeds worldwide (depending on your website size), I am paying... nothing! AWS S3 and CloudFront come with a [FreeTier limit](https://aws.amazon.com/de/about-aws/whats-new/2014/05/08/aws-free-usage-tier-now-includes-amazon-cloudfront/), the certificate is offered for free, and to use up all the free tier limits millions of visitors need to arrive on my website.
- 5. **I can still use dynamic content**: And what if I need dynamic content to e.g. manage logins or contact forms? Actually you are still able to use it. Some parts of this website use AWS Lambda, a service to execute code serverless, which allows to still include dynamic content.

### Recipe for this website

TLDR;
What exactly did I use for this website?

- 1. **Static Website Generator**: I used [Hugo](https://gohugo.io/), a static website generator to help myself write pure HTML. It safes you a lot of redundant tasks and is incredibly fast (written in GO). You could actually instantly copy this website cloning my [repository on Github](https://github.com/JustinGuese/Gusonex.cloudHugo).
- 1.1 **Dynamic Comments by Disqus**: [Disqus](https://help.disqus.com/en/articles/1717063-adding-disqus-to-your-site) is offering a good solution to allow comments on a static website (remember: no dynamic content in static websites!)
- 1.2 **Dynamic Contact Form via Formspree**: [Formspree]https://formspree.io/) is offering contact forms for static websites. It would be possible as well to use [AWS Lambda for this](https://aws.amazon.com/de/blogs/architecture/create-dynamic-contact-forms-for-s3-static-websites-using-aws-lambda-amazon-api-gateway-and-amazon-ses/), but this solution has been easier to integrate in Hugo.
- 2. **AWS S3 Static Website Hosting**: The output is then hosted on an AWS S3 bucket set up for static hosting [Link](https://docs.aws.amazon.com/de_de/AmazonS3/latest/dev/WebsiteHosting.html).
- 3. **CDN using AWS CloudFront**: To instantly deliver the website worldwide and to use the free SSL certificate provided by AWS it is served via [AWS CloudFront](https://aws.amazon.com/de/cloudfront/).

<br><br>

#### Do you want to use serverless as well?


[Get a free 15 minute consultation!](/contact)
No matter if it is a website, a web application or databases, let us have a chat!

## Our services

#### Serverless Databases
#### Serverless Analytics
#### Serverless ETL Pipeline design (Cloud and on-premise)
#### Serverless Data Archives
#### Serverless Security Concerns and Compliance
#### Serverless Data crawling, data mining
#### Serverless NoSQL databases
#### SQL to serverless migration
#### Infrastructure as a service
#### Hadoop, Elasticsearch, AWS EMR as serverless
#### Transformation of products to serverless
#### Serverless Websites
