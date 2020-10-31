# Getting started with Anaconda

## Virtual environment

Let's open Anaconda Prompt \(or Command Prompt if you're Mac user\).

![](../.gitbook/assets/anaconda-prompt.gif)

The first step is to choose the environment name. Usually, it's = project name.

```bash
conda create --name redcar python=3.7.4
```

After you have created a new virtual environment, you need to activate it to use it. To do so, use the following command:

```bash
conda activate redcar
```

Now you can install all the packages that you will use in this project. Let's try to install pandas:

```bash
conda install pandas
```

You can always install a specific version of a package `conda install pandas==0.25` \(e.g., your project group member using not the latest one.\) You can also install a set of packages at once. Just type them separated with space:

```bash
conda install matplotlib seaborn numpy
```

Let's take a look at what packages do we have:

```bash
conda list
```

To dump this list of packages into a single file use:

```bash
conda env export > environment.yml
```

🎉 We created a file conventionally called `environment.yml` that contains all the packages that have been installed! Now we can pass by this file to a person and he or she will be able to recreate the same setup. Usually this file is stored under `C:/Users/<your_user_name>/` \(and for Mac \)

Alternatively, if you want to build an can use the following command:

```bash
conda list --explicit > spec-file.txt
```

Note that this specification file will allow you to install on the same operation system \(i.e. Windows\).

Now let's get back to our base environment. For this simply type:

```bash
conda deactivate
```

Let's finalize our practice by deleting this virtual environment 😱 :

```bash
conda env remove --name redcar
```

Don't worry! We doing this only to recreate it again from previously environment.yml file 🦉 . If you somehow forget to do so, take one [here](https://github.com/mikhailsirenko/REDCAR/blob/master/.gitbook/assets/environment.yml) and put it to `C:/Users/<your_user_name>/` \(and for Mac \). The command for creating an environment from the file is as follows:

```bash
# Deafult option
conda env create --name redcar --file environment.yml

# Or if you used the second option
conda list --explicit > spec-file.txt
```

Alright! We're back on track. We have a new **virtual environment** with a base set of packages to continue our work!

### Installing a kernel to a new environment 

However, to make new environment to work inside JupyterLab \(or Jupyter Notebook\), we need to tell JupyterLab that the environment exists. We can do this with the following command:

```text
python -m ipykernel install --user --name=redcar
```

Poof! You're done! Now you should see an extra icon on the right from default _Python 3_ called _redcar_. 

After you've finished a project, you may want to delete associated virtual environment and the kernel from JupyterLab \(read get rid of _myenv_ icon like on the image below, or as in our case _redcar_\).

![](../.gitbook/assets/jupyter_venv.png)

 To do so, let's open Anaconda Prompt or Command Prompt and type:

```bash
jupyter kernelspec list
```

The output of this command is a list of all available kernels. For example, if you have only two kernels installed _redcar_ and default _Python 3_, __the output should look like this:

```text
Available kernels:
  redcar      /home/user/.local/share/jupyter/kernels/redcar
  python3    /usr/local/share/jupyter/kernels/python3
```

Alright, let's delete _redcar_:

```text
jupyter kernelspec uninstall redcar
```

Alright! We've just rolled back to the original state of your JupyterLab.

{% hint style="warning" %}
🧠 **Note:** There are other ways to manage virtual environments [pipenv](https://pipenv.pypa.io/en/latest/) or [venv](https://docs.python.org/3/library/venv.html). We cannot say which one is better. As usual there are pros and cons. Our advice is: whenever you feel uncomfortable with the tool that you're using, dive in to find a better option.
{% endhint %}

### Cleaning up your `base` environment

Most probably, you haven't knew that there should be a new environment for every single project. Instead your were staging all things that you wanted to try out to the `base`  . And at another sunny weekend you said to yourself: "Well, it's time to make a cleaning!" 

There is a different ways to keep track of was installed in your environments. As we know, magic command is `conda list` . The next step is to list all the packages that you don't use anymore and uninstall them with `conda remove`. Alternatively, you can type:

```bash
conda list --name base --rev
```

`rev` here stands for "revision" and the output of this command is a set of "snapshots" of your base environment. For example,  on 01-01-2020 you had`rev 0` which is a very first version of your base environment when you've just installed Anaconda. The good news are: you can rollback to this revisions! The bad news, however, are that it is unstable! Practice showed that it's better to rollback to at least `rev 1`  . We can do it with:

```bash
conda install --rev 1
```

You see a command `install` over there? Yes, it means that we will install the packages that you had in `rev 1`. The obvious problem is that some of them \(installed in let's say 2016\) aren't available anymore. In this case, it's better to avoid playing with revisions. Instead try to install a fresh new version of Anaconda. 

## Cookiecutter Data Science

![](../.gitbook/assets/cookiecutter-logo.png)

[Cookiecutter](https://cookiecutter.readthedocs.io/en/1.7.0/README.html) is a tool that helps to create project templates for Python packages, Java and Android applications, etcetera. Having a project template with a couple of lines of code prevents you from manual work \(and that's the end goal, right 🐌?\).

The project template that we will use was designed by _DrivenData_ and called [Cookicutter Data Science](https://drivendata.github.io/cookiecutter-data-science/). The project website says: 

> _"Cookiecutter Data Science is a logical, reasonably standardized, but flexible project structure for doing and sharing data science work."_

After testing in numerous ⚔, we concluded that it's pretty handy. So let's continue by installing Cookiecutter and Cookiecutter Data Science.

The first step is to open Anaconda Prompt \(or Command Prompt\) and activate the virtual environment.

```bash
conda activate redcar
```

Now let's install Cookiecutter with pip \(it's not available with conda 🤷\):

```bash
pip install cookiecutter
```

Nice! The next step is to point Cookiecutter to a specific project template:

```bash
cookiecutter https://github.com/drivendata/cookiecutter-data-science
```

You'll get a set of questions such as: 

* project name and repo name \(usually they're =\), 
* author name \(surname and company if any\),
* short description of your project \(a couple of line of code for README.md\),
* licence \(read more about licenses [here](https://www.kiuwan.com/blog/comparison-popular-open-source-licenses/)\), 
* S3 bucket and AWS profile \(for establishing a pipeline with Makefile\).

Let's fill it up!

![](../.gitbook/assets/cookiecutter-ds.gif)

{% hint style="success" %}
Alright! Great success! Now it's time to continue this work with Git and GitHub.
{% endhint %}

