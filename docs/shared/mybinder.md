# Sharing for Accessibility

![MyBinder.org Homepage](../.gitbook/assets/image%20%285%29.png)

Binder is a free service that allows you to simply specify an online Git repository to create a Jupyter or RStudio environment. That means anyone anywhere \(with internet\) can run an instance of your repository under the exact conditions you specified.

Perhaps your project's figures are slightly out of date but you've configured the code to automatically include the latest data \(good work!\). Someone else can easily run your code to see what the latest figures would look like.

## Example

Let's take a look at how to do this by creating another example project. Find a folder to house the project, and let's get a simple notebook and environment set up in it.

```bash
mkdir ~/MySharedRepoProject # Make a new folder
cd ~/MySharedRepoProject
git init
```

Then, let's create a new environment through the Conda prompt and make a new notebook.

```bash
conda create --name SharingREDCAR python=3.7.4 # Create new environment
conda activate SharingREDCAR
conda install jupyterlab # Some people might to install here
jupyter lab ./ # Launch Jupyter Lab in this folder (Notebook is fine too)
```

Within Jupyter Lab, create a new notebook. Let's keep it super simple and simply plot an easy function with Seaborn. First, we need to install the packages we know we will need.

```bash
conda install numpy pandas seaborn
```

Next, make a new notebook \(remember, call it something meaningful like `0.0-TestNotebook.ipynb`\) and copy the follow script inside.

```python
import math
import numpy as np
import pandas as pd
import seaborn as sns

x = np.linspace(0,6.28,100) # [0,2*pi] in 100 pieces
y = [math.sin(i) for i in x]

# Move x and y into a Pandas DataFrame for Seaborn
df = pd.DataFrame({'x':x,'y':y})

# Plot our data as a line plot with Seaborn
sns.relplot(x="x", y="y", sort=False, kind="line", data=df)
```

{% hint style="info" %}
Of course, you would usually split code into cells, but we want something you can easily copy-paste if you don't want to type it out.
{% endhint %}

{% hint style="warning" %}
The above code should not run in yet because we haven't specified the environment it needs.
{% endhint %}

Now, make a new repository on GitHub so we can put this code online, and then let's see how it works!

```text
git add 0.0-TestNotebook.ipynb
git remote add origin https://github.com/jasonrwang/SharedREDCAR.git
git push
```

### Loading in Binder

Go to [mybinder.org](3.1-setup-binder.md) and copy and paste your GitHub repository URL in the main box.

{% hint style="info" %}
Binder actually supports _any_ online Git repository!
{% endhint %}

Click Launch \(the orange button\).

The next part will take a few minutes. If you scroll down on the Binder page, you will see a "How It Work" section, which is pretty descriptive, but also introduces some new concepts. In our words, what is happening is that Binder is taking some space on a remote server and reserving it for you, downloading any packages you need \(that you need to specifiy – more on that below\), and then setting up the server so that you can access it.

When it completes, you should see your notebook should be there. Go ahead and open it! What happens?

{% hint style="danger" %}
Because we haven't told Binder which packages we need, you should see an error.
{% endhint %}

Here, you can simply run `!conda install <packageName>`  in a cell to get the packages that you want. However, you'd have to do that every time you launch a Binder instance. Instead, you can tell Binder what you need.

### Specifying the Environment

As we mentioned in [workshop 1](../1-reproducible/#anaconda-distribution), defining an environment lets others use your files more easily. Let's tell Binder what we need with an `environment.yml` file.

Go back to Conda prompt and generate a file.

```text
conda env export > environment.yml
```

This is the way we taught you earlier. Alternatively, you can simply make `environment.yml` like below. These are the most important packages we need to run the code and the other ones that the previous command yielded should also show up.

```yaml
name: SharedREDCAR
channels:
  - conda-forge
dependencies:
  - numpy=1.18.1
  - pandas=1.0.3
  - python=3.8.2
  - seaborn=0.10.0
```

{% hint style="warning" %}
Make sure that `environment.yml`sits within your main project directory and not any other folders inside.
{% endhint %}

Now, let's push those changes back up to GitHub and try it again in Binder!

```text
git add environment.yml
git push
```

That's it! Repeat the steps above in [Loading in Binder](3.1-setup-binder.md#loading-in-binder) and you should now be able to run the code!

## Bonus Information

* You can give your users a shortcut to launch your work in a Binder instance by using the prompt on the Binder main page that says "Copy the text below, then paste into your README to show a binder badge: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jasonrwang/SharedREDCAR/master)". Just make sure to do this _before_ you click "Launch".
* Binder provides documentation on how to work with non-Conda languages [here](https://mybinder.readthedocs.io/en/latest/using.html#choose-from-many-open-source-languages) and gives information on launching in Jupyter Lab or RStudio [here](https://mybinder.readthedocs.io/en/latest/using.html#choose-from-multiple-user-interfaces).
* If you are on the go and want to check something quickly in Jupyter or RStudio with Binder, check out [jasonrwang/EPA\_binder](https://github.com/jasonrwang/EPA_binder) on GitHub.
* Binder is a free service so its servers are not very powerful. Thus, its function is mostly as a tool to help people run something quickly. If you want to easily run a remote server and do powerful calculations, there are other options. We listed a few on the [first page](./#a-short-note-on-another-options) of this workshop.



