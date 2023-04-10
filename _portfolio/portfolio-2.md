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

## Formulating the challenge in Teammatching

The challenge with teammatching can be broken down into two parts:
1. First finding people that may be interested in the same project.
2. Second, creating a conversation where details are discussed before forming a team.

The key part to the first step is to allow people to share their ideas or to collect them in some manner. This way they can be found by others. For the second part, there are several aspects that need to be discussed. These include the project details, the team members, and the time commitment. The second part is more of a communication problem, and is not addressed by IdeaNet, but it is a key part of the teammatching process.
