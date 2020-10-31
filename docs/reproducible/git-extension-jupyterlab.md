# Setting up Git extension for JupyterLab

Finally, let's look at how Git works inside JupyterLab. While there are many visual interfaces, this one integrates with your Notebook workflow.

![](../.gitbook/assets/jupyter-lab.gif)

Git for JupyterLab is an official Jupyter Lab extension. There are two main ways to install it – one might be easier on some computers than others. If none of these work for you, then refer to the JupyterLab documentation on extensions [here](https://jupyterlab.readthedocs.io/en/stable/user/extensions.html) and the Git extension's [documentation](https://github.com/jupyterlab/jupyterlab-git).

### Method 1: JupyterLab Extension Manager

![Enable extension manager by searching in the command palette &#x2013; JupyterLab Documentation](../.gitbook/assets/extension_manager_enable_manager.png)

You should be able to turn this on from inside JupyterLab using the "palette" or under "Settings" in the menu bar. If this option is not available, you may need to upgrade your JupyterLab version. You can open Conda Navigator and click the gear above Jupyter Lab or type in:

```text
pip install --upgrade jupyterlab
```

### Method 2: Install Through Anaconda Prompt \(or Terminal\)

To get it working, open your Anaconda Prompt \(or Terminal on macOS\) and type in:

```text
pip install --upgrade jupyterlab-git
jupyter lab build
```

You can also do this from a Jupyter cell an

```text
!pip install --upgrade jupyterlab-git
!jupyter lab build
```

From there, just simply close and reopen Jupyter Lab! There should be a panel on the left called "Git" now. To `git add` a file, just hover your cursor on the file in the "Git" panel and click on the up button on the left.

When you're reading to make a commit, type in a commit message and then the check box. That's it! If you want to push changes to a remote repository, relevant buttons will also appear if you configured them like shown in [the first part of this section](1.2-get-started-git.md#getting-started-with-collaborating).

{% embed url="https://github.com/jupyterlab/jupyterlab-git" %}

### Other Useful Extensions

* [Jupytext](https://github.com/mwouts/jupytext/tree/master/packages/labextension) \(mwouts/jupytext\) – for easier Git–Jupyter management
* [Table of Contents](https://github.com/jupyterlab/jupyterlab-toc) \(jupyterlab/jupyterlab-toc\)
* [Spellchecker](https://github.com/ijmbarr/jupyterlab_spellchecker) \(ijmbarr/jupyterlab\_spellchecker\)
* [Code formatter](https://github.com/ryantam626/jupyterlab_code_formatter) \(ryantam626/jupyterlab\_code\_formatter\)
* [Jupyterlab Debugger](https://github.com/jupyterlab/debugger) \(jupyterlab/debugger\) - Jupyter Visual Debugger

