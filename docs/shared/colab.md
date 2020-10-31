# Sharing for Collaboration

Sometimes, we need to share our work for others to collaborate with us on. For some use cases, shifting all of your work to the cloud has benefits.

In short, Google Colab is a Notebook instance hosted on Google's servers. Not only can you use their cloud servers for computing, but you can also use it to manage data too \(though sometimes you might explicitly avoid Google too for data storage!\).

Colab allows you to save and share your Notebook work online without ever needing to download it back onto your own computer.

![Google Colab&apos;s Introduction Notebook](../.gitbook/assets/screen-shot-2020-04-08-at-23.44.04.png)

#### Starting a Colab Notebook

There are a few ways we can start a Colab project:

1. Upload a project from your computer
2. Import a repository from GitHub
3. Import a repository from Google Drive
4. Start a new notebook

All of these options can be found in "File" menu in the top left corner.

#### Managing the Environment

Unfortunately, Colab is not based in Conda and only supports Python 2 and 3. That means you need to install packages individually with `!pip install packageName`. Unlike Binder, if you close the file and relaunch it, the packages should stay with the Notebook. This also means that instead of using an `environment.yml` file, you will need to use Python's `requirements.txt` instead. The syntax is even easier in this case:

```text
numpy==1.18.1
pandas==1.0.3
seaborn==0.10.0
```

On the downside, to suffiiciently run the requirements file, you will need to "mount" and run this notebook through Google Drive. `requirements.txt` needs to be in the same directly as your Notebook; you can then run from the notebook:

```text
!pip install -r requirements.txt
```

{% hint style="info" %}
This is certainly a big trade off between using Google Colab and Binder with a cloud Git repository.
{% endhint %}

#### Sharing Your Work

One hugely powerful feature of Google Colab is that you can directly click the "Share" button in the top right corner just like with any Google Docs file.

![](../.gitbook/assets/screen-shot-2020-04-09-at-00.56.08.png)

Sharing can also be done in the same ways as starting a project, though the GitHub portion requires you to give Colab access as a third party tool on GitHub. It's all automatic, if you choose to do this.

## Loading Data

The following are relevant to any implementation of a Notebook, not just Google Colab.

#### Upload into the Instance

Both Google Colab and Binder allow you to upload files to your Notebook instance. However, they will be deleted as soon as you end the session by closing that window or you otherwise disconnecting. Since Binder simply serves Jupyter Notebook or Lab, we won't cover that here. To load data into Google Colab, you can use the Files tab \(it looks like a folder\) in the left-most panel to upload data.

#### Using Google Drive \(Colab-Specific\)

Google Colab also allows you to "mount" your Google Drive. It does not seem possible to mount another person's drive or one of your other accounts.

#### Store Your Data Online

Another way to load data into a project is host it somewhere else. For example, if your data can be publicly shared, you can host it on Pastebin. For example, I've put the DataFrame I generated in the Notebook example here: [https://pastebin.com/raw/LZrhPHSN](https://pastebin.com/raw/LZrhPHSN)

I can simply load this DataFrame within my Notebook:

```python
df = pd.read_csv('https://pastebin.com/raw/LZrhPHSN', index_col=0)
```

There are many other ways to store data online. **Talk to Nicolas, the Data Steward, about storing the data for your projects.**

#### **Use Git LFS**

The Git framework was originally conceived to work with code, not other types of files. However, many projects require non-code files to be tracked too, like PDFs and files for Word, Photoshop, and more. In some ways, you can think of data in the same way.

[Git Large File Storage \(LFS\)](https://git-lfs.github.com) was to solve these issues. It's a little tricky to adapt an existing Git repository to use LFS, but it's certainly possible. However, we will assume you are starting a new project and already know the format of all of your files. Let's say they are CSV files in this case.

First, let's install it in the Conda Prompt with:

```text
conda install git-lfs
```

Next, from a GitBash window within your project folder \(whether blank or an existing one\), type the following:

```bash
## Activate Git LFS in GitBash
# You actually only need to run this once on your computer
# and not once per repository.
git lfs install

# Start tracking all CSVs within LFS
git lfs track "*.csv" # This will create a `.gitattributes` file
git add .gitattributes # This tells other Git repos you are using LFS
git commit -m "Now tracking CSV files via LFS" # (Optional)
```

That's it! The rest of the workflow is the same as normal Git. Add your actual CSV files, commit those changes, and then push them to your cloud repository.

{% hint style="warning" %}
While GitHub started the Git LFS project, they provide very limited resources in using it under the free tier. You will be limited to 1 GB maximum per repository and 1 GB bandwidth per month \(see more [here](https://help.github.com/en/github/managing-large-files/about-storage-and-bandwidth-usage)\). Instead, you can look at using GitLab, which has 10 GB per repository and unlimited bandwidth.
{% endhint %}

{% hint style="info" %}
If you want to migrate a repository, check out the main Git LFS page \(you need `git lfs migrate`\).
{% endhint %}

