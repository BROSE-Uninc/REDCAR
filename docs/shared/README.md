# Part 3: Shared

## Introduction

The goals of this workshop are to:

* cover some tools and best practices for sharing your work that can **make it easier for others to access** \(and also reproduce!\),
* examine a few ways you can **collectively work on a project** together, and
* practice these concepts **hands-on**.

We will mostly cover [MyBinder](https://mybinder.org/) \(a specific implementation of the JupyterHub project\) and [Google Colab](https://colab.research.google.com/). We'll briefly also mention some cloud storage methods you can use, but won't cover that in-depth.

## Sharing for Accessibility

So your code is now more reproducible and understandable. Great. Let's tell the world! Hello world!

![](../.gitbook/assets/image.jpeg)

We already showed you in [workshop 1](../1-reproducible/#git-and-github) how to put your Git-tracked repository of work onto GitHub, a cloud Git repository. We talked about how we can manage that repository to make it easy for someone to "clone" or download and run on their own computer.

However, that person needs to also have a preliminary understanding how environments and package management work. They also need access to a laptop where they can install software freely. What if someone doesn't understand what an environment is? What if they have a company computer they can't install Python and Jupyter on or want to see your work from a phone or tablet \(most internet users are mobile these days\)?

MyBinder.org is a free cloud service that gives anyone browser-based access to a Jupyter or RStudio interface that can run your code on a remote server. In other words, as long as your repository is configured neatly, anyone with internet access can run your code without needing to configure anything!

## Sharing for Collaboration

The other main reason to share our scientific work is for others to collaborate with use. Again, Git via GitHub can handle a lot of that, but we haven't covered multi-user Git \(branching, merging, pull requests, and resolving merge conflicts\). Unfortunately, we won't here either, but one of our colleagues shared a nice interactive game that can teach you it: [https://learngitbranching.js.org](https://learngitbranching.js.org).

Another option is to use something like Google Colab, which is similar to Binder, but doesn't _necessarily_ need a Git repository behind it; you can simply open Colab, upload files, and save it on the \(Google\) cloud. You can share a link with others and they will be able to see exactly what you do, but not in real-time. Colab is similar to Google Docs except it does not support live coding, where two people can edit and run a notebook simultaneously.

There are options for real-time Notebook editing, but we haven't tested them yet. CoCalc is a paid option and [Deepnote](http://deepnote.com) is in a closed beta at the time of writing.

## A short note on another options

Of course, as always, there are other services that provide similar solutions 🚀

* [Kaggle Notebooks](https://www.kaggle.com/notebooks)
* [Microsoft Azure Notebooks](https://notebooks.azure.com) \(free and paid tiers\)
* [Amazon Sagemaker](https://aws.amazon.com/sagemaker/) \(Machine Learning-oriented – it's expensive but powerful\)
* [IBM Notebooks](https://dataplatform.cloud.ibm.com/docs/content/wsj/analyze-data/notebooks-parent.html)

For R you can use [RStudio Cloud](https://rstudio.cloud/). The service requires you to register and right after you'll get access to your _workspace._ There, in similar to RStudio fashion, you can create a project, make scripts and use the whole potential beloved RStudio.

Always keep in mind the potential drawbacks of such services. **You** **create** and **work** with the scripts and notebooks **online**. As a result, if you've lost the internet connection, you can also lose some parts for your work. Without a doubt, there is always a certain backup mechanism. However, stuff happens, you know... 

Second, **computational power** and **storage capacity**. Of course, without paying this services extra fee, you won't reach the maximum 💯. Though, that poses the question: do you even need this maximum? If not, you're safe, keep up good work. Otherwise, think about the heavy part do it locally and share only the resulting notebooks. For example, I want to perform clustering on a huge data set out of 1 billion samples. So, I'm doing it on my [super powerful laptop](https://github.com/mikhailsirenko/REDCAR/blob/master/.gitbook/assets/laptop.jpg), saving the obtained clusters and loading them into a notebook. No need to use cloud services for that 🎆.

Finally, **privacy**. Make sure that you've read the terms and conditions. You don't want to lose the rights of your code or data, right? If the terms and conditions are too long and written in a tricky bureaucratic way, ask fellow programmers on Stack Overflow.

## Agenda

| When? | What? |
| :--- | :--- |
| 10:15 – 10:30 | Getting ready up with BBB |
| 10:30 – 10:45 | Recap of workshops 1 and 2 |
| 10:45 – 11:00 | REDCAR project and workshop 3 introduction |
| 11:00 – 11:30 | Sharing for Accessibility |
| 11:30 – 11:45 | Break |
| 11:45 – 12:15 | Sharing for Collaboration |
| 12:15 – 13:00 | Debugging to get it working for you + discussion \(?\) + Closing |

