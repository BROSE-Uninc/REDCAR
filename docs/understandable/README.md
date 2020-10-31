# Part 1: Understandable

## Introduction

The goals of the second workshop are:

* show you **how to organize your study** in a way that others \(fellow students, researchers or programmers\) can easily understand what an amazing job you did;
* remind you how efficiently **name variables**, **program functions** and why **code formatting** is important \(PEP-8, Black, etc.\); 
* practice it on a **case study**.

## Workflows

Let's talk about workflows first. What is a _workflow_ in simple terms? Well, it's a flow of work👨🎓, the **steps that you need to undertake to solve a problem or a task** in accordance with a domain \(i.e. data science, engineering\). A workflow can be pretty extensive in tools that should be used to support each of the actions, or a more high-level \(so-called _step-wise_ approach\). Here is a formal definition by Business Process Management Center of Excellence Glossary \(Wikipedia contributors, 2020\):

> _"Workflow is an orchestrated and repeatable pattern of business activity enabled by the systematic organization of resources into processes that transform materials, provide services, or process information."_

Even though different domains require domain-specific knowledge to define a workflow and follow it, there are certain similarities across problem-oriented workflows. You start with a problem, do something in the middle and propose a solution or an insight at the end👨🎓. Here is a [great example](https://www.forbes.com/sites/artcarden/2011/07/14/underpants-gnomes-political-economy/):

![Famous underpants gnomes profit plan ](../.gitbook/assets/plan.png)

Workflows are usually depicted with a diagram. Data science studies often depicted as [directed acyclic graphs](https://en.wikipedia.org/wiki/Directed_acyclic_graph) \(DAGs\), whereas in reality process looks similar to the System Dynamics one \(going back and forth from one stage to another\).

![Overview of the SD modeling approach according to Richardson &amp; Pugh \(1981\)](../.gitbook/assets/sd-richardson.png)

Sounds obvious, of course, but it there are a couple of important implications to keep in mind. First, **qualitative** and **quantitative workflows have a similar skeleton**. Consider a step-wise approach proposed by [Hermans & Cunningham \(2018\)](https://www.wiley.com/en-us/Actor+and+Strategy+Models%3A+Practical+Applications+and+Step+wise+Approaches-p-9781119284703) and a workflow for data scientist by [Byrne \(2017\)](https://resources.github.com/downloads/development-workflows-data-scientists.pdf):

{% tabs %}
{% tab title="Quantitative" %}
![One representation of the data science process](../.gitbook/assets/byrne.png)
{% endtab %}

{% tab title="Qualitative" %}


![Step-wise approach for actor network scanning](../.gitbook/assets/hermans.png)
{% endtab %}
{% endtabs %}

Such a high-level similarity can be helpful in establishing a transdisciplinary collaboration and promotes joint understanding of the work process.

Second, it is important to **remember** that **you are addressing a problem** or a question \(and not the method\). Identification of the"right" problem is time consuming \(as well as finding an appropriate method\). Remember famous [Russel Ackoff's](https://en.wikipedia.org/wiki/Russell_L._Ackoff) saying?

> _"Successful problem solving requires finding the right solution to the right problem. We fail more often because we solve the wrong problem than because we get the wrong solution to the right problem."_

In case of a data science project it may seem trivial. [The methods allow you](https://scikit-learn.org/stable/tutorial/machine_learning_map/index.html) to predict, to cluster, or to try to explain a certain phenomenon. But when you start working, you can realize that there is a different angle that seems more promising. Just remember, violating from the original problem or doing research in an exploratory fashion, one hand problem, can bring unexpected benefits, but on the other side, can bring an extra burden and shift your deadlines.

Finally, students should remember that the **workflow ≠ thesis structure**. While it seems attractive to have a step of predefined steps, modeling process does not equal to scientific research process. Modeling serve to help answer research questions, propose solutions or evaluate policies. They are instruments of analysis.

## Better code

Here we have two things to discuss: how to **organize your project** \(the files\) and how you **write** your **code**.

![The perfect code quality measurement doesn&apos;t exi-](../.gitbook/assets/code_metric.png)

The **project structure follows from** the chosen **workflow**. For example, if you are doing a data science research and decided to follow the workflow from above you should have Jupyter Notebooks and scripts dedicated to each of the "steps." Simulation studies conducted "purely" with programming languages \(see amazing and free [Think Complexity](https://greenteapress.com/wp/think-complexity-2e/) by Allan Downey\), follow the same logic \(i.e. separate the simulation model from analysis of experiments\). If you are using a certain simulation modeling software, for example, [Simio](https://www.simio.com/index.php), you are forced to follow its internal logic.

It is important how **name your variables** and **functions** and **comment the code**. Consider a variable `blah4`. Yes, that's a real variable! It is a data frame with a bus schedule inside. The name was given by an junior employee of a mid-size data science company working in sustainable transportation. And you know what, it is not a problem! First make it work, then make it right! The problems begin when he will placed on another project. After a week or a month is back and how easily he will figure what `blah4` stands for? So instead of exercising your memory, try to name your variables in human-readable format: `bus_schedule`. Easy-peasy, right?

Guess what is another way to reduce the effort that it is needed to understand the code? Exactly🎆! Commenting it! However, commenting is also tricky. You do not want to overwhelm yourself, colleague or another researcher with a novel on how you did this and that. Here is a trick🕵. If

* we follow a certain workflow,
* name our notebooks according to the step,
* variable and function names are also fine, 

then the amount of comments should be much less! And of course, communities are helping us the🥇standards \(i.e. [PEP-8](https://www.python.org/dev/peps/pep-0008/) or [Vensim naming conventions](https://www.vensim.com/documentation/ref_variable_names.htm)\). 

## Case study

Let us practice these and the tools from Workshop 1 Reproducible on a case study. We prepared 3 options for you:

1. Exploring emergency calls in the Netherlands;
2. Understanding dynamics of COVID-19 in the Netherlands;
3. A project that you are currently working on.

We do not state a goal for each of these studies, you can formulate it yourself. But if you feel lost, here are a some options:

1. Predict the number of firefighter calls  based on the socio-demographic and housing variables \(try [AutoML](https://www.microsoft.com/en-us/research/project/automl/)\);
2. Cluster positive tests curves \(see [tslearn](https://tslearn.readthedocs.io/en/latest/index.html)\) and find similarities in cities of the same cluster \(i.e. [population size](https://arxiv.org/abs/2003.10376)\).

!!! warning
    These are just exercises that we are proposing you to work on in the class. Without a doubt, such a simple analysis cannot capture the whole complexity of any these problems. So be aware and do not make quick conclusions.

The data can be found here:

| № | Original data sets | Processed sample data sets |
| :--- | :--- | :--- |
| 1 | [112 Nederland](https://www.112-nederland.nl/) | [SURFdrive public link 1](https://surfdrive.surf.nl/files/index.php/s/rcILzk3eJ3Hlfg1) |
|  | [Kaart van 500 meter bij 500 meter met statistieken](https://www.cbs.nl/nl-nl/dossier/nederland-regionaal/geografische-data/kaart-van-500-meter-bij-500-meter-met-statistieken) |  |
|  | [Kerncijfers wijken en buurten 2019](https://www.cbs.nl/nl-nl/maatwerk/2019/31/kerncijfers-wijken-en-buurten-2019) |  |
|  | [Wijk- en buurtkaart 2019](https://www.cbs.nl/nl-nl/dossier/nederland-regionaal/geografische-data/wijk-en-buurtkaart-2019) |  |
| 2 | [Coronavirus kaart van Nederland per gemeente](https://www.rivm.nl/coronavirus-kaart-van-nederland-per-gemeente#node-coronavirus-covid-19-meldingen) | [SURFdrive public link 2](https://surfdrive.surf.nl/files/index.php/s/K7vfcVz4Debt0OM) |
|  | [2020 coronavirus pandemic in the Netherlands](https://en.wikipedia.org/wiki/2020_coronavirus_pandemic_in_the_Netherlands) |  |
|  | [Kerncijfers wijken en buurten 2019](https://www.cbs.nl/nl-nl/maatwerk/2019/31/kerncijfers-wijken-en-buurten-2019) |  |
|  | [Bestuurlijke Grenzen Extract 2020 \(Actueel\)](https://www.pdok.nl/downloads/-/article/bestuurlijke-grenzen#764e16c78afb7a31973b7e2110b4e4ed) |  |

{% hint style="info" %}
🧙 **Tips:** Try Wayback Machine to get the past data. For example, you can complete RIVM data set on COVID-19 by municipality use the following [query](https://web.archive.org/web/*/https://www.volksgezondheidenzorg.info/onderwerp/infectieziekten/regionaal-internationaal/coronavirus-covid-19).
{% endhint %}

We expect you to do a minimalist study🦸:

1. Formulate a problem or a hypothesis;
2. Get the data;
3. Visualize it;
4. Apply a simple model;
5. Report your findings;
6. Upload the work to the GitHub.

So, select an exercise and roll-on🚀! After your finish the exercise we will be happy to check it out and give some feedback. Just send us the GitHub repo and we will send you the feedback 🤓 .

## References

1. Wikipedia contributors. \(2020, March 23\). Workflow. In Wikipedia, The Free Encyclopedia. Retrieved March 23, 2020, from [https://en.wikipedia.org/w/index.php?title=Workflow&oldid=946935282](https://en.wikipedia.org/w/index.php?title=Workflow&oldid=946935282)
2. Hermans, L., & Cunningham, S. W. \(2018\). Actor and Strategy Models. Wiley Blackwell.
3. Ciara Byrne \(2017\). Development Workflows for Data Scientists. O’Reilly Media, Inc.
4. Richardson, G. P., & Pugh III, A. I. \(1981\). Introduction to system dynamics modeling with DYNAMO. Productivity Press Inc..

<!-- ## Agenda

| When? | What? |
| :--- | :--- |
| 10:15 - 10:30 | Getting ready up with BBB |
| 10:30 - 10:45 | Recap of workshop 1 |
| 10:45 - 11:00 | REDCAR project and workshop 2 introduction |
| 11:00 - 11:30 | Talking about workflows |
| 11:30 - 11:45 | Break |
| 11:45 - 12:15 | How to write better code? |
| 12:15 - 13:00 | Starting with a case study | -->
