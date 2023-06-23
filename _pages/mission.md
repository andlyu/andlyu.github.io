---
title: "Mission"
permalink: /mission/
author_profile: true
redirect_from:
  - /mission
---

<!-- ---
permalink: /mission/
title: "Mission"
excerpt: "mission"
author_profile: true
redirect_from: 
  - /mission/
  - /mission.html
--- -->

In neuroscience temporal patterns of neurons are heavily studied, these shed light on specific activity that occurs such as repetitive activation of neurons, and the convergence of firing rates in neurons to stable steady states.

In modern neural networks most temporal information is treated with either attention or RNNs. Attention has been highly successful in recent years but does not contain recurrent connections that are a critical component of the biological brain. RNNs on the other hand have major technical limitations with the way information propagates through time. 

The temporal patterns in neurons can be explored in the following settings: 1) Deep Learning for time-based modalities such as video and speech, where I believe the temporal aspect can be leveraged for self-supervised learning purposes. 2) In Reinforcement Learning, the temporal sequence of states and actions is rudimentary for modeling the rewards, actions, and the state of the environment. 3) Hopfield Networks and Dense Associative Memory have investigated the convergence of neural networks to stable steady states, yet they are limited in their application to temporal data. 

Of these, deep learning in video seems to leverage the temporal sequence of frames most directly and has added explainability over speech due to visual frames.

<!-- In the next few years, I hope to research the concept of neural dynamics such as stable steady states in the context of neural networks. I believe that this concept is a fundamental aspect of the biological neural networks that can contribute to artificial neural networks. 

## Neuroscience Perspective

- **Attractor Networks**: Attractor Networks are populations of biological neurons that who’s firing rates reach stable stead states or oscilations. Please read the ([wiki](https://en.wikipedia.org/wiki/Attractor_network)) for more details.
    - From the computatoinal neuroscience perspective electircal currents of individual cells (and then multiple cells) have been studied to understand how they behave as a function of time.
        - Individually, Based on the [Hodgkin–Huxley model](https://en.wikipedia.org/wiki/Hodgkin%E2%80%93Huxley_model), at different input currents, a neuron will  will either reach a constant voltage will fire at a specific frequency.
        - Multiple neurons have also been modeled together and have been shown to converge to a specific state (when measuring their firing rates).
        - Such modeling techniques can be [used to describe memory](https://www.science.org/doi/10.1126/science.1112555), where the stable states represent familiar situations that neural networks can converge to.
    - I believe that such attractive characteristic is genetic in nature as such networks are linked with specific functions. That being said, I think that the states that the neural networks converge to must be learned.

## Computer Science Perspective
- From the computer science perspective, these neural networks have been modeled as Hopfield NN, and Deep Belief Networks. Rencently Diffusion models have a similar characteristic where they converge to specific outputs. And the temporal aspect is currently mostly modeled with attention as it.
    - Hopfield Networks (1982) have binary neurons that can model associative memory
        - They have energy based function that
        - Dense Associative Memory (2016)
            - Extends hopfield neural networks to `continuous` case
    - Diffusion Models
        - Diffusion takes a latent space and denoises it. This means that a neural network predicts the output, and a step is taken in that direction until outputs look realistic.
        - This is similar to attractor networks as the results converge to a specific set of states such as ``real looking images" in stable diffusion.
        - I believe this can be further learned with neural network states, where a model is able to converge to them
    - **Temporal Aspect.** Currently, most temporal patterns are modeled through attention.
        - In Neuroscience lots of modeling observes how neurons behave as a function of time. In Computer Science, temporal data is most commonly used as input in attention networks but was previously commonly modeled by RNNs and CNNs.
        - There has been little exploration into modeling converging representations as a function of timed
        - I believe the video domain can be leveraged to explore this direction.
    - **Neurosymbolic AI.** Neurosymbolic AI represents the intersection of symbolic logic and Neural Network Processing. -->

<!-- 
A data-driven personal website
======
Like many other Jekyll-based GitHub Pages templates, academicpages makes you separate the website's content from its form. The content & metadata of your website are in structured markdown files, while various other files constitute the theme, specifying how to transform that content & metadata into HTML pages. You keep these various markdown (.md), YAML (.yml), HTML, and CSS files in a public GitHub repository. Each time you commit and push an update to the repository, the [GitHub pages](https://pages.github.com/) service creates static HTML pages based on these files, which are hosted on GitHub's servers free of charge.

Many of the features of dynamic content management systems (like Wordpress) can be achieved in this fashion, using a fraction of the computational resources and with far less vulnerability to hacking and DDoSing. You can also modify the theme to your heart's content without touching the content of your site. If you get to a point where you've broken something in Jekyll/HTML/CSS beyond repair, your markdown files describing your talks, publications, etc. are safe. You can rollback the changes or even delete the repository and start over -- just be sure to save the markdown files! Finally, you can also write scripts that process the structured data on the site, such as [this one](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb) that analyzes metadata in pages about talks to display [a map of every location you've given a talk](https://academicpages.github.io/talkmap.html).

Getting started
======
1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this repository](https://github.com/academicpages/academicpages.github.io) by clicking the "fork" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section

Site-wide configuration
------
The main configuration file for the site is in the base directory in [_config.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_config.yml), which defines the content in the sidebars and other site-wide features. You will need to replace the default variables with ones about yourself and your site's github repository. The configuration file for the top menu is in [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml). For example, if you don't have a portfolio or blog posts, you can remove those items from that navigation.yml file to remove them from the header. 

Create content & metadata
------
For site content, there is one markdown file for each type of content, which are stored in directories like _publications, _talks, _posts, _teaching, or _pages. For example, each talk is a markdown file in the [_talks directory](https://github.com/academicpages/academicpages.github.io/tree/master/_talks). At the top of each markdown file is structured data in YAML about the talk, which the theme will parse to do lots of cool stuff. The same structured data about a talk is used to generate the list of talks on the [Talks page](https://academicpages.github.io/talks), each [individual page](https://academicpages.github.io/talks/2012-03-01-talk-1) for specific talks, the talks section for the [CV page](https://academicpages.github.io/cv), and the [map of places you've given a talk](https://academicpages.github.io/talkmap.html) (if you run this [python file](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) or [Jupyter notebook](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), which creates the HTML for the map based on the contents of the _talks directory).

**Markdown generator**

I have also created [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator
) that converts a CSV containing structured data about talks or presentations into individual markdown files that will be properly formatted for the academicpages template. The sample CSVs in that directory are the ones I used to create my own personal website at stuartgeiger.com. My usual workflow is that I keep a spreadsheet of my publications and talks, then run the code in these notebooks to generate the markdown files, then commit and push them to the GitHub repository.

How to edit your site's GitHub repository
------
Many people use a git client to create files on their local computer and then push them to GitHub's servers. If you are not familiar with git, you can directly edit these configuration and markdown files directly in the github.com interface. Navigate to a file (like [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) and click the pencil icon in the top right of the content preview (to the right of the "Raw | Blame | History" buttons). You can delete a file by clicking the trashcan icon to the right of the pencil icon. You can also create new files or upload files by navigating to a directory and clicking the "Create new file" or "Upload files" buttons. 

Example: editing a markdown file for a talk
![Editing a markdown file for a talk](/images/editing-talk.png)

For more info
------
More info about configuring academicpages can be found in [the guide](https://academicpages.github.io/markdown/). The [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (which this theme was forked from) might also be helpful. -->
