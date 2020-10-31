# Part 2: Reproducible

## Introduction

The goal of this workshop is to introduce you a **step-wise approach** and a set of **tools** for conducting reproducible computational research.

### Anaconda Distribution

We will start by setting up an Anaconda Distribution. Today, Anaconda Distribution is one of the most popular data science software management platforms. It's free and open-source and allows you easily install and configure Python and R programming languages, Jupyter Notebook, VS Code and Spyder IDEs, and much more. The core of Anaconda Distribution is a package management system called conda.

{% hint style="info" %}
 ****🧙 **Tips:** If you're already familiar the tools that you're going to use you may want to install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) \(lightweight version of Anaconda\) or [RStudio](https://rstudio.com/) separately.
{% endhint %}

When you're working on a data science project or a simulation study it's essential to keep track of all packages that you have used. Moreover, their versions are also important. For example, you have used scikit-learn Python library of version 0.22.2 and want to pass saved pre-trained models to you colleague for further analysis. But his version is 0.18.2. If you're lucky, you'll be notified about the differences in the versions. Otherwise, you load the model, but it will be treated wrongly and you may have "wrong" results.  

The new version of a library may not have a function that you have used or result of it will be different due to modifications. The solution is to create a **virtual environment** \[[1](https://docs.python.org/3/tutorial/venv.html)\] with conda.

> _"Virtual environment is a self-contained directory tree that contains a Python installation for a particular version of Python, plus a number of additional packages."_

After you finished working on the project, you can dump all packages that you have used into a single file. Pass it to anyone and she or he will be able to recreate your virtual environment and run the code!

Pip installs only Python packages whereas conda installs packages which may contain software written in any language. Read more about the differences [here](https://www.anaconda.com/understanding-conda-and-pip/).

{% hint style="warning" %}
\*\*\*\*🧠 **Note:** Rule of thumb is to first to use `conda install <package_name>` and if it didn't work `pip install <package_name>`. Many Python packages currently have complex dependencies that won't be properly handled by pip.
{% endhint %}

### Git and GitHub

The part is dedicated to version control with Git and GitHub. 

Why version control?

![How many time you have followed the third path?](../.gitbook/assets/version-control.png)

Yon can always **separate** your experimental **work** from the main one. If you broke something there, it won't affect the project. Also, you can **rollback** to the work that you have done long time before. You made a mistake and want recover the previous version. No probs! Finally, **group work**. No need to say to a group member: "Hey! Can you wait for a while until I'll finish my work?" Work independently and then perform a magic `merge` command.

![Git merge gives your project new cool features.  ](../.gitbook/assets/merge.png)

More formally \[[2](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)\]:

> _"Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later."_

Git is the most popular version control system. It widely used across different programming languages and operation systems. 

GitHub, in its turn, provides hosting for Git.

{% hint style="info" %}
\*\*\*\*🧙 **Tips:** If you're a student, got and get your [GitHub Student Developer Pack](https://education.github.com/pack). It provides free access and discounts for 
{% endhint %}

In 2018, Microsoft bought GitHub \[[3](https://blogs.microsoft.com/blog/2018/10/26/microsoft-completes-github-acquisition/)\]. As a result, the debates have started: privacy, politics and so on. Just so you know there are similar services such as [GitLab](https://about.gitlab.com/), [BitBucket](https://bitbucket.org/product). If you want to switch to one of them, the process will be mostly smooth, since they are based on the same Git principles.

{% hint style="info" %}
 ****🧙 **Tips:** After you got familiar with Git Bash \(yes, it's important!\) you may want to explore alternatives that have some visual interface. Take a look at [VS Code](https://code.visualstudio.com/) \(nice Git integration\) or [Git Kraken](https://www.gitkraken.com/) \(cool branches visualizations\).
{% endhint %}

### JupyterLab Git extension

In third part of the workshop we will introduce you some 🍪 \(cool additions\) for JupyterLab. It will simplify the process of you interacting with Git and GitHub.

{% hint style="warning" %}
\*\*\*\*🧠 **Note:** After you installed Anaconda Distribution there is no need to open it, if you want just launch JupyterLab. The faster option is to open Anaconda Prompt \(or just Command Prompt if you're Mac user\) and type `jupyter lab`.
{% endhint %}

Take a look [here](https://github.com/mauhai/awesome-jupyterlab) for other nice extensions. For example, [table of contents](https://github.com/ian-r-rose/jupyterlab-toc). We found it extremely handy for navigating through long notebooks.

## Agenda

| When? | What? |
| :--- | :--- |
| 10:15 - 10:30 | Enjoying coffee and tea |
| 10:30 - 10:45 | REDCAR project introduction by Mikhail |
| 10:45 - 11:15 | Getting started with Anaconda by Mikhail |
| 11:15 - 11:30 | Break |
| 11:30 - 12:15 | Getting started with Git and GitHub by Nicolas |
| 12:15 - 12:30 | Setting up Git and other JupyterLab extensions with Jason |
| 12:30 - 13:00 | Lunch time! |

## References

1. Python Software Foundation. Virtual Environments and Packages. Available from [https://docs.python.org/3/tutorial/venv.html](https://docs.python.org/3/tutorial/venv.html). \[Accessed 05 March 2020\].
2. Git. Getting Started - About Version Control. [https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) \[Accessed 05 March 2020\]
3. Microsoft Corporate Blogs. Microsoft completes GitHub acquisition. [https://blogs.microsoft.com/blog/2018/10/26/microsoft-completes-github-acquisition/](https://blogs.microsoft.com/blog/2018/10/26/microsoft-completes-github-acquisition/). \[Accessed 05 March 2020\].

