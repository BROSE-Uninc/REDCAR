# Better code

I hope you are convinced that there is a need to write better code👨💻:

![Don&apos;t like be Obi Wan](../.gitbook/assets/bad_code.jpg)

We talk about 3 interconnected things that matter:

1. Project structure;
2. Naming;
3. Comments.

## Data science project structure

The **project structure follows from** the chosen **workflow**. As we discussed in the previous section, there is no 🥇 standard, **workflows are similar** and **share the core**, to our knowledge the one proposed by the Hardvard's data science course is good-enough. So let's see what we have:

![One representation of the data science process](../.gitbook/assets/byrne.png)



The process of asking the right question probably should not be documented as a script or a Jupyter Notebook. But starting from the second step, we will need some magic 🧞.  Luckily we have a tool and template project structure that can easily satisfy this workflow needs. Ladies and gentlemen, welcome [Cookiecutter](https://cookiecutter.readthedocs.io/en/1.7.0/README.html)!

_Cookiecutter_ is a tool that helps to create project templates for Python packages, Java and Android applications, etc. Having a project template created with a couple of lines of code prevents you from manual work \(and that's the end goal, right 🐌?\).

The project template that we will use was designed by _DrivenData_ and called [Cookicutter Data Science](https://drivendata.github.io/cookiecutter-data-science/). The project website says: 

> _"Cookiecutter Data Science is a logical, reasonably standardized, but flexible project structure for doing and sharing data science work."_

After testing in numerous ⚔, we concluded that it's pretty handy. The instructions on how to make it work can be found in [Getting started with Anaconda](../1-reproducible/1.1-get-started-anaconda.md). Let's take a closer look at its directory structure:

```text
├── LICENSE
├── Makefile           <- Makefile with commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default Sphinx project; see sphinx-doc.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.py           <- Make this project pip installable with `pip install -e`
├── src                <- Source code for use in this project.
│   ├── __init__.py    <- Makes src a Python module
│   │
│   ├── data           <- Scripts to download or generate data
│   │   └── make_dataset.py
│   │
│   ├── features       <- Scripts to turn raw data into features for modeling
│   │   └── build_features.py
│   │
│   ├── models         <- Scripts to train models and then use trained models to make
│   │   │                 predictions
│   │   ├── predict_model.py
│   │   └── train_model.py
│   │
│   └── visualization  <- Scripts to create exploratory and results oriented visualizations
│       └── visualize.py
│
└── tox.ini            <- tox file with settings for running tox; see tox.testrun.org
```

At first you can be feel overwhelmed with all new elements listed here: what is `tox.ini`, why do we need `Makefile`? Do not worry about it at first. Let's focus on the main folders.

### data

Data plays a critical role in reproducibility of a study. You manual fixed some typos, forgot original URLs where from the data was downloaded, overwritten raw data... Things like these make impossible to reuse your study. Besides, it is not really handy to run all of your notebooks again and again to download a single data set. If you found what you were looking for: write a downloading script and store it.

{% hint style="danger" %}
🐉**Warning**: Remember! Never manually correct raw data! If you did any manipulations to the data, separate it and store it in processed folder!
{% endhint %}

### notebooks

Computational **notebooks are for** sharing **stories** and important elements of your study 📖 . Do not use them for everything. If you wrote a function that does some preprocessing, make tests, comment it with a proper docstring and save it as \*.py file. The rule of thumb is do not put the code in the notebook if it is not necessary to either understand it or manipulate it \(i.e. some custom plot\).

As with any story, **computational notebooks** also **require an outline**. More more people are starting to use JupyterLab with an extension [Table of Contents](https://github.com/jupyterlab/jupyterlab-toc) \(if do not know, run and install it!\). However to make sure that everyone will be on board, put a bullet pointed list on top with an outline. See, everyone happy now 🌈 .

Finally, notebook should have a **clear purpose**, a **clear input** and **a clear output**. If I opened `1.1-data-gathering-cbs.ipynb`, I'm expecting that the goal is to gather the data from CBS, the input is probably a URL, and the output is the data set saved elsewhere. If you are doing something complicated, It is pretty handy to have a diagram built in [Lucidchart](https://www.lucidchart.com), for example.

### src

src is a folder that contains source code for all sort of functions. Cookiecutter Data Science proposes a separation of functions by the goal. If it is a data gathering script, store it under data subfolder, etc. Straightforward logic, right? Again, after a certain time, you will start appreciate lengthy-function-free notebooks. Just give it some time and practice.

## Naming

![XKCD \#1513](../.gitbook/assets/image%20%286%29.png)

It can be incredibly useful to structure your names in both a way that is legible and discernable between types. As mentioned earlier, name a variable that contains a bus schedule `bus_schedule`! That way, you will be able to remember what it is when you look back at your code and someone reading it will be able to immediately understand what it does too.

But, furthermore, naming functions slightly differently will indicate that it is a process rather than just some carrier for information. Functions are commonly capitlized \(e.g. `Read_Bus_Schedule`\).

![](../.gitbook/assets/image%20%284%29.png)

There are also conventions like using "[camelCase](https://en.wikipedia.org/wiki/Camel_case)" for variables \(`busSchedule`\) and "TitleCase" for functions \(`ReadBusSchedule`\); using underscores is called "snake\_case". Avoid using hyphens entirely \(they might be confused with "negative" or "subtract"\), unless you are using NetLogo. Within the community you're working in, check if there is a standard. Python's PEP8 guide only points out a few conventions but NetLogo \(the Agent-based Modelling tool\) prefers using camelCase. Whatever you do, don't do both.

![We do not condone violence!!!](../.gitbook/assets/image%20%283%29.png)

## Structuring and Functions

Writing code in a that is more legible can not only make it easier for a reader to understand what is happening, but also to help you think through and implement your work.

Each programming language and thematic community \(e.g. machine learning, data science, simulation\) have their own sets of standards and best practices, but they are all fundamentally the same. In addition to what was written on the front page for this workshop, below are some additional pointers.

### Writing to Minimize Superfluous Information

Concision is precision.

#### Writing Single-Purpose Functions

Often, programmers will write massive functions with many steps and many lines of code. This can make it harder to debug, profile \(time and measure to speed up running the code\) and understand the code.

One way to think about writing functions instead is to think about **writing one function for only one purpose**. That means you can "nest" functions together, but you should delineate them clearly.

If something in one of your functions goes wrong, the code interpreter will probably stop running and tell you something went wrong. Sometimes, the interpreter will be nice and tell you exactly what went wrong. Other times, it will only give out a generic answer. By modularizing aspects of your code into different functions, you can catch specific issues more easily. Similarly, if you are running a profiling tool \(these will basically time your code and tell you how long each function takes to run\), splitting up code into different functions might help you find problematic functions or logic that slows down your code.

Modularizing code into different functions can also make it easy for readers to dive into the part they really care about. You can nest functions within one another so that users can look directly at what they are curious about. For example, something like `AnalyzeNeighbourhood` might be written as:

```python
def AnalyzeNeighbourhood(data):
    # Read and Prepare Data
    dfNeighbourhoodData = pd.read_html(data)
    dfNeighbourhoodData = dfNeighbourhoodData.coolstuff()
    
    # Process Data
    dfNeighbourhoodData = dfNeighbourhoodData.coolstuff1()# COMPLEX CHANGE 1
    dfNeighbourhoodData = dfNeighbourhoodData.coolstuff2()# COMPLEX CHANGE 2
    dfNeighbourhoodData = dfNeighbourhoodData.coolstuff3()# COMPLEX CHANGE 3
    dfNeighbourhoodData = dfNeighbourhoodData.coolstuff4()# COMPLEX CHANGE 4
    
    # Visualize
    fig,ax = plot(dfNeighbourhoods)
    fig.title = "Neighbourhood Insight"
    fig.xaxis = "X variable"
    fig.yaxis = "Y variable"
```

Instead, you can modularize it into:

```python
def AnalyzeNeighbourhood(data):
    '''
    This function analyzes neighbourhood data, given in HTML format,
    prepares it, does some really cool stuff to it, and then
    visualizes it in a really cool way.
    '''
    readData = ProcesseNeighbourhoodData(data)
    processedData = ProcesseNeighbourhoodData(readData)
    VisualizeNeighbourhoodData()
    
def ReadNeighbourhoodData(data):
    '''
    Reads and prepares data for the AnalyzeNeighbourhood function.
    '''
    processedData = pd.read_html(data)
    processedData = processedData.coolstuff()
    
    return processedData

def ProcesseNeighbourhoodData(processedData):
    '''
    This is a short function that makes cool calculations on
    the prepared data from ProcessNeighbourhoodData.
    '''
    finalNeighbourhoodResults = processedData.coolstuff1()# COMPLEX CHANGE 1
    finalNeighbourhoodResults = finalNeighbourhoodResults.coolstuff2()# COMPLEX CHANGE 2
    finalNeighbourhoodResults = finalNeighbourhoodResults.coolstuff3()# COMPLEX CHANGE 3
    finalNeighbourhoodResults = finalNeighbourhoodResults.coolstuff4()# COMPLEX CHANGE 4
    
    return finalNeighbourhoodResults
    
def VisualizeNeighbourhoodData(processedData):
    '''
    This is a short function that visualizes the analyzed data
    from ProcessNeighbourhoodData.
    '''
    fig,ax = plot(dfNeighbourhoods)
    fig.title = "Neighbourhood Insight"
    fig.xaxis = "X variable"
    fig.yaxis = "Y variable"
```

Obviously, the second example is actually longer than the first one. This example was very straightforward. Hopefully you can see how, if your function was more complicated, such an approach would be useful.

Additionally, many functions often share elements. For example, you might have a set of visualizations, using many sets of data, you'd like to create for analysis or presentation. Instead of redefining a visualization scheme for them each time, you can write your own visualization function.

#### Defaulting to Expected Values

Sometimes \(especially if you are dealing with dynamic inputs, like from a user\), your code might behave strangely. In doing data or text cleaning, you might have many, many "cases" \(alternative arrangements\) that you did not expect. For example, if you want a user to type in their name, they might write "red car" instead of "Red Car". Of course, you can run some functions to detect this. However, it's simpler to try and format the eventual result the way you want. In this example, you'd probably do something like `userInput.title()`.

This approach is called "defensive programming", and there's a great YouTube on the subject if you are using `if` statements. The downside to doing defensive programming is that sometimes, you might have an issue propagate throughout your work. Being defensive, while hugely convenient \(and partly robust\), masks underlying errors you might have.

{% embed url="https://youtu.be/ldqDpmMkXgw" %}

### Tools to Help

Whichever editor you are coding in likely has tools to help you do some of these things. The specific tools are usually called "Linters". Here are a few example programs below:

* Visual Studio Code: [https://code.visualstudio.com/docs/python/linting](https://code.visualstudio.com/docs/python/linting)
* Jupyter: [https://github.com/kenkoooo/jupyter-autopep8](https://github.com/kenkoooo/jupyter-autopep8) \(unfortunately, it can only "fix" your code and cannot show you issues in real time\)

![Example of Python linting in Visual Studio Code \(Source: Microsoft\) ](https://gblobscdn.gitbook.com/assets%2F-LxgDVGTZ1Ermo-tNUjZ%2F-M3QFo9SGLawPbM9kREm%2F-M3QKZEAociw2S7jnUuq%2Fimage.png?alt=media&token=8944d4fb-2f38-4d02-bfb9-8b94994dcfae)

## Comments

If we now we are \(thanks to project structure and correctly named notebooks\), there is no need in extensive commenting what you have done.

Commenting functions is essential! You need to use a certain docstring format for it. Take a look [here](https://www.datacamp.com/community/tutorials/docstrings-python#sixth-sub).

![](../.gitbook/assets/comment_code.jpg)

## Less ugly code in Jupyter Notebooks

Working with Python scripts can be clumsy in Jupyter Notebooks. You need you have either all scripts in the same folder as the notebooks or specify directory in a complicated fashion. That's pretty annoying.

As usual, there is a trick 🕵 ! You can install your project folder as package! Then process of importing your function will look like:

```python
from src.data import make_dataset
data_set()
```

Now, let's see how make it work. First, **we need** to have a file called **setup.py**. If you used Cookiecutter Data Science template, then the file was created by default. Here is an example this file's code:

```python
from setuptools import find_packages, setup

setup(
    name='src',
    packages=find_packages(),
    version='0.1.0',
    description='Modelig and simulation of Westeros weather',
    author='Jon Snow',
    license='BSD-3',
)

```

And second, we need to install it as a package. Remember, we need to do in a dedicated to the project virtual environment. Open Anaconda prompt and run the following lines of code:

```python
# Activate your virtual environment
conda activate redcar

# Go to the project directory
cd google drive/redcar

# Finally install the repo as a package
pip install --editable .
```

That it is! Amazing 🦄 ! Combined with modularizing your functions, your code should already be much more understandable.

