---
layout: post
title:  "Retiring OWASP Glue"
date:   2021-03-09
categories: Projects
description: "A writeup and post mortem of the OWASP Glue project"
---

![OWASP Glue](/assets/images/glue.png)

In 2014 I started working on a tool I called Pipeline that later turned into OWASP Glue.  The TLDR; of this post is that I am stepping away and suggesting that the tool be retired or that new maintainers step in.

The idea was to make it easier to build security tools into the development pipeline.  Back then, that was mostly Jenkins.  We took things like Brakeman, Bundler Audit, Bandit and others and made Glue run them and build out findings in a set format.  Later, we sent that output to Jira, GitHub, TeamCity, Pivotal.  The idea was Glue was the glue that tied those processes together.  It is actually funny to think about how Pipeline is so overloaded now.  At the time, it wasn't such a common term.

Actually, part of what we wanted to do was scan prebaked images like AMI's.  People were using Packer to build tailored AMI's and we thought Pipeline could run AV and FIM on those with Clam and Hashdeep.  It was only later and as we started to use it with clients on application security focused projects that we got deeper into the open source tooling for AppSec, extending to support nmap, ZAP and some commercial tools.

Even then, it was somewhat overlapping with tools like Defect Dojo and commercial tools like ThreadFix.  We liked having the tool be open and theoretically easy to use.  In the early days, we had a lot of help from Alex, Brian and Rafa.  There was even a spin off and open source UI called CodeBurner that was built to apply Glue across a directory of a thousand applications.  I would also note that Glue drew heavily on Justin Collins' Brakeman tool from the start and if you look closely enough you can see the obvious code sharing. 

An easy critique was that loaded up, our Docker image could have been measured in GB with the Java runtime, Python and Ruby just to support running the tools.  But it was easy and fun to write the integrations in Ruby.  At one point, we had commercial tooling like Contrast and Checkmarx integrations.

In 2018, Omer Levi Hevroni offered to help with Glue.  He had fresh energy and new ideas about how to abstract the running tools.  In many ways, this felt like the ideal next step for the project.  Diversify the leadership team and work to bring new people and ideas into it.  He made significant improvements and brought new people and capabilities to the tool.

Unfortunately, that also signaled the beginning of my reduced involvement and in the longer term it made it hard to come back and fix things.  Like any software project, working with it actively helps keep it fresh.  Since I wasn't doing that it started to get harder to really contribute.  That become a frustration as folks came to me asking "why doesn't Glue work with the new Dependency Check?" for instance.  I wanted to help, but I couldn't really.  I didn't know what changed in Dependency Check and heck - I'm not even working on a laptop with a JVM today.  It is a great lesson that writing something that works at a point in time is good but being able to maintain it and keep it working is another whole level of effort.

Sitting here in 2021, and having discussed this with Omer, we have come to the conclusion that Glue may not be the best solution out there to build around.  Omer recommends Defect Dojo or commercial tooling.  I am using a more unix like philosophy these days and working on small tools that interoperate like unix command line tools (fkit, off and crush).  Glue was much more of a monolith if you look at it honestly.  When I want to run dependency check, I'm doing that in a GitHub action or BitBucket Pipeline and piping the output to fkit to do the work of reporting issues.  Many people built Jenkins plugins or GitHub actions for things like ZAP.  Glue is still an interesting project.  I'm glad I worked on it and there is a lot to learn from how it works and what worked and what didn't.

There is also a time and a place to let go and to say that the tool had its run.  Don't we all always say "the easiest way to make sure an application isn't vulnerable is to turn it off?"  Granted, Glue doesn't probably sit in a place where it is introducing vulnerabilities - but it is natural for software to age and be retired.  This is me saying:  Glue has run its course.  Please find another actively maintained approach for doing application security in your pipelines.  Or perhaps others will step in to maintain and improve Glue.  In that case, thank you and good luck.

Thanks for all of the support over the years.  Thanks to Alex, Brian, Rafa, Omer, Runako and others who contributed to the tool.  I had fun and it legitimately helped people.

