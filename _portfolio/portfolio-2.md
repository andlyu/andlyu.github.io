---
title: "IdeaNet"
excerpt: "[IdeaNet](http://www.ideanetapp.com) is a personal project to improve the teammatching process. 
It's a site where people can search for others with simialr ideas for class projects or projects for specific events.
 After running a a few customer interviews and pilot cases, it became appearent that teammatching requires more communication that is not addressed by the site.
 As such it was pivoted to aid in mentorship matching where similar interests are also key. <br/><img src='/images/IdeaNet.png' width='30%'>"
collection: portfolio
---

[IdeaNet](http://www.ideanetapp.com) is a personal project to improve the teammatching process. 
It's a site where people can search for others with simialr ideas for class projects or projects for specific events.
 After running a a few customer interviews and pilot cases, it became appearent that teammatching requires more communication that is not addressed by the site.
 As such it was pivoted to aid in mentorship matching where similar interests are also key.

## Motivation

Teammatching is a common problem in many settings. For example, in a class project, students are often asked to form teams to work on a project.
At the same time, it is often difficult to find people with similar interests and skills to work with especially in settings with many unfamiliar people.
The aim of IdeaNet is to make it easier to find people, especially strangers to team up with to work on projects. While this is a common problem to address, I believe that NLP can be leveraged to build an highly effective tool to solve this problem.

## How it works

The technology behind IdeaNet is a simple web app that allows users to create Ideas that are automatically matched with other similar interests.
A Sagemaker endpoint is used to generate embeddings for each Idea using SentBERT, and the embeddings are used to find similar Ideas through cos similarity.
The Embeddings are stored in a Database, and similarity scores is used to match Ideas with similar interests.
