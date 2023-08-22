---
layout: post
title:  "Startup Project Management Tools"
date:   2018-06-13
categories: Business
description: Tools we've tried for project management
authors: ["Matt Konda"]
---

I thought it might be worth writing some of my ideas about tools we either use or have used at Jemurai.  After starting, I realized that I should write separate posts for different types of tools as this quickly became a long read.  So here, I'll focus on different ways we have organized ourselves - meaning project management and tracking tools.

## Trello

When I first started Jemurai, I was a [Trello](https://trello.com) fan.  We used it effectively for a significant period of time before we got to the point where we needed something more.  I both loved and hated that it was unstructured.  It meant that things like metrics and common processes had to be explained to team members and collaborators.  The simplicity was a tradeoff.  We never really used the rich media part, it was just a simple Kanban board for us.

At the end of each week, I found myself left with a lot of little cleanup.  I would create different boards for different sprints.  I struggled with seeing things across boards.  Even though I mostly figured that out for myself, it wasn't clear for everyone else.  Ultimately, it was a bit more "managing the boards" than I wanted.  All in all, Trello was a good place to start.

## Miscellaneous

I briefly tried Sprintly, and liked parts of it.  Contrary to Trello, it really pushed you to do Sprints and organize that way.  I liked how it helped with reporting to clients about progress through tasks.  I don't recall using it for multiple concurrent projects.  It was also early, I'm sure it has improved.

I used Asana at a client.  It was adequate.  I tried Remember the Milk.  I tried Rally, AgileZen, VersionOne.  None of these quite fit us.

I'll write a separate posts about our experiences with CRM's.  For the purposes of this post, the relevant bit is that we use HighRise for Sales related Todo's.

## JIRA / TFS

Eventually we moved to JIRA and used it for a couple of years.  

I had used JIRA a ton, even back when the "Agile" part of it was Greenhopper.  We planned sprints, and I even used the Portfolio add on which gave me a much better way to see across projects.  Maybe the best thing about using JIRA was that we were in step with our customers, many of whom seemed to be using JIRA for large software development projects.

A couple of things didn't really resonate about it in the long term.  We had lots of little projects that were hard to track independently, which made shifting from one view to another hard.  I built dashboards to see everything and it all worked.  In the end, I was dis-satisfied and felt that a weakness was that it wasn't oriented to "getting things done" or tracking dates on customer facing deliverables.  You can do it, but its not necessarily emphasized because the main use case is building big complicated projects.  We typically had 2-3 of those plus 10 small projects.  We even ran sales, HR, marketing tasks through JIRA.  Again, it worked, but it wasn't necessarily intuitive for everyone.

We used TFS at clients that were .Net shops and it seemed very JIRA like, just from that world.

After Atlassian completely revamped the Confluence UI, I finally decided that I was done with JIRA and Confluence.  

## BaseCamp

We moved to BaseCamp.  I had read Rework and various parts of that story resonated.

BaseCamp was a good move.  It showed clear tasks, had template projects and todo lists that allowed us to use checklists for the samller mini projects.  The ability to share with clients was really cool, but we didn't use it much.  I think I was afraid that clients might be nervous about tracking their stuff in BaseCamp.

I really like the way the BaseCamp business runs.  It is opinionated and solves specific problems well.  They are successful and know it.  When we cancelled, they refunded our yearlong subscription no questions asked.  I would easily use BaseCamp again.

## GitHub

What made us move to GitHub was wanting to be able to leverage issues tied to code.  The Project concept in GitHub is pretty comparable to the way we started with Trello.  Kudos to Joe from my team who figured out how we could use Projects across Repos.

We ended up with:

* A Repo for each major codebase.  Issues tracked as close to codebase as possible.
* A Jemurai wide Project specifically for backlog.  This allows us to link issues from any repo into a backlog where they can be dragged up and down to reflect priority.
* A Jemurai wide Project for each sprint.  In this case, issues from different projects get linked into the Sprint project.
* We have general repo defined that we file issues that are not code related.  That way our project board can reflect product management and other tasks visible.

We still end up doing a bit of shuffling of issues each week, but since the underlying issues aren't the same as the project cards, we can just associate them to another project - we don't have to copy them.

## Journaling

I like to keep track of what goes on every day in a journal.  I used to do this on paper, Emacs OrgMode and Atom.  I tried DayOne.  Now I do it in VS Code with a file for each day in a folder that includes notes for several years all sync'd to DropBox.  This way, I can get to the notes from lots of devices if need be.  The format being simple text helps with portability and easy of writing.  I can instantly take notes during meetings.

I still use an Moleskine notebook for face to face meetings because I find that I can actively listen better with a small notebook out of the way than I can with a laptop clicking along.

Journaling is an important part of project and task management because it is the thing that gives me insight into productivity, prioritization issues and process changes when they need to happen.

## OmniFocus

I found that for me to go back to an outside system many times during the day was distracting.  So I prep my todo list and calendar each day.  That includes making sure what I want to do is represented in OmniFocus.  I also block times in my calendar to make sure that I'm spending my time on the right things.  This is where prioritization happens.  Its a reality check as to whether the right work is planned.

I use OmniFocus both on my Mac and on my Phone.  I like the UI.  I use a Chrome extension, which I build from source myself, to copy web text into OmniFocus tasks.  The nice thing about that generic approach versus other kinds of integrations is that it works with basically any web content.

## Change

Although we have had a lot of change, generally we have progressed to simpler more intuitive systems to use.  Each time that we change, we have been able to refocus on the pieces of the process that are most important to us.  So I would say that we leverage the change to clean up process.

## Conclusion

Obviously it has been a long winding road to decide what tools will work best for us.  There is no doubt we will continue to evolve here.  

What is working today is:

* GitHub issues and projects for team work
* OmniFocus for personal to do lists
* VS Code for journaling
* HighRise for sales todo's

We define team work at the beginning of each week and check on it daily in standups.

During the day, I use OmniFocus to make sure I am on point for each specific activity I am doing.