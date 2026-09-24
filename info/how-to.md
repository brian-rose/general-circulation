# How to use this book

Stay tuned for more!

## Instructions for UAlbany DAES students

These instructions require credentials that should be available to graduate students in UAlbany's [Department of Atmospheric and Environmental Sciences (DAES)](https://www.albany.edu/daes). Users elsewhere will need to adapt to their available computing resources.

### Log into the University-maintained JupyterHub

- Follow this link in your favorite web browser: <https://jupyterlab.its.albany.edu/>
- Use your UAlbany NetID credentials to log in.
- From the drop-down menu, choose a job profile. Batch is open to anyone at UAlbany, while Daes-burst is restricted to DAES users. A safe choice is:
    > Daes-burst (restricted) - 4 cores, 32GB, 8 hours
- If you are unable to spawn onto "Daes-burst", then you will also be unable to open the dask worker cluster when you try to run the notebooks. So please let me (BR) know if this is the case.
- Wait for the server to start. You should then see the familiar JupyterLab environment in your browser.

:::{note}
We are running the data-intensive notebooks on the University-maintained Jupyter instance rather than our internal DAES-maintained hubs because that allows us to launch dask worker clusters on the HPC cluster.
:::

### Obtain a local copy of the notebook

This is a different filesystem than the DAES linux network, and we don't currently have a tool in place to automatically copy and update the notes directly from the online sources. So you have to manage the files yourself.

Here are a few ways to do it. All of these are acceptable for work in this class, so follow the approach that appeals to you.

#### Copy a single notebook

_Do this if you just want to work on one notebook at a time and organize your file space manually yourself._

- From any content page of the book (e.g. <https://brian-rose.github.io/general-circulation/lectures/angular-momentum-budget/>), click the download button near the top-right of the browser window.
- Download the `*.ipynb` notebook file locally.
- Use the file browser in the left column of the JupyterLab screen to navigate to wherever you want to store the notebook
- Drag and drop the `*.ipynb` file into that file browser.

You now have a copy of the single notebook ready to open in your Jupyter session.

#### Copy the whole repository (no version control)

_Do this if you want the whole collection of notebooks but are not comfortable with `git` and version control._

- Go to the source repository at <https://github.com/brian-rose/general-circulation>
- Click the green "Code" button.
- From the dropdown window, select "Download ZIP"
- Use the file browser in the left column of the JupyterLab screen to navigate to wherever you want to store the notebook
- Drag the resulting folder `general-circulation-main` into that file browser

You now have a copy of the whole repository of notebooks ready to open in your Jupyter session.

#### Copy the whole repository (with version control)

_Do this if you are experienced with git and want to use version control to keep your local copy in sync with my updates throughout the semester._

- Open a Terminal from the JupyterLab Launcher.
- In the terminal, navigate to wherever you want to store the notes.
- Do `git clone https://github.com/brian-rose/general-circulation.git`.

You now have a git clone of the whole repository of notebooks ready to open in your Jupyter session. Further suggestions:

- Use version control with `git` to manage your work and pull in my updates as necessary.
- **Do all your work on branches, not on main**. Use main only to pull in my updates. That way you will avoid complicated git conflicts.


:::{tip}
For tutorials on using git and GitHub, see [Pythia Foundations](https://foundations.projectpythia.org/foundations/getting-started-github/).
:::

### Launch a notebook and select the correct kernel

- Use the JupyterLab file browser to locate the notebook (`*.ipynb` file) that you want to run.
- Double-click on the notebook file to launch in the JupyterLab.
- **Select the kernel called "DAES Python 3.14 August 2026 Environment".**
- Run the notebook!

:::{caution}
It's easy to forget to select the right kernel. If you encounter import errors immediately, you're probably using the wrong kernel!
:::

### Using the dask cluster

Many of the notebooks have code like this (with some variations):
```
from dask_jobqueue import SLURMCluster

cluster = SLURMCluster(cores=64, # size of a single job -- typically one node of the HPC cluster
                       memory="374GB",  # the max memory on the 64-core burst-daes nodes, I believe
                       walltime="01:00:00",
                       queue="burst-daes",
                      )

cluster.scale(1)
dclient = dClient(cluster)
dclient
```

These are instructions to allocate 64 cores (one physical node) from the HPC cluster in a way that lets Dask parallelize our large array calculations. You can see that we are specfically asking to use the `burst-daes` partition. These are restricted to DAES users.

We are using `SLURMCluster` here because slurm is the cluster management software that UAlbany uses for its HPC system.

One thing you may want to change here is the `walltime` argument. In the example above, it is set to one hour. It's fine to request a longer walltime, especially for interactive, exploratory work. Your cluster will be killed with no warning after that time elapses.

:::{tip}
Aside from invoking the dask worker cluster as shown above, we don't have to write any specific code to parellize the calculations. The Xarray code we use to define and execute our data manipulations look exactly the same as they would without the worker cluster (but run much faster).
:::

#### Monitoring the HPC cluster

From a terminal (e.g. the terminal in your active JupyterLab session on the hub), you can do
```
ssh [your-net-id]@head.its.albany.edu
```

After logging in, you can see all the active jobs on the cluster with 
```
squeue
```
or to see only your own jobs
```
squeue -u [your-net-id]
```

If you have followed the above instructions and launched a dask worker cluster from your Python code, you should see at least two active jobs that belong to you. One is the JupyterHub session, and the other is your dask worker cluster.

You can also see how many compute nodes are actually available. Try this:
```
sinfo
```

If you don't see any idle nodes for partition `burst-daes`, then you won't be able to launch a dask worker cluster until other jobs are done.

For more information on Slurm and research computing at UAlbany, visit the [askIT Knowledge Base pages](https://albany.atlassian.net/wiki/spaces/askit/overview) and look for the tabs on Research and HPC systems.

### Releasing resources back to the user community

You'll see that most of my notebooks the invoke a dask cluster have a line at the end like
```
cluster.close()
```

This tells Slurm to kill the dask workers and release the allocation so it's available for other users. This will also happen automatically when you exceed the `walltime` you set initially, so it's not critical.

Likewise, if you are done working on the notebook, you can release the cores you reserved to run your Jupyter session (though these will also time out eventually).

From the JupyterLab session, go to File --> Hub Control Panel. Then click "Stop My Server".

:::{tip}
Save your work! JupyterLab will not save the changes in your notebook automatically.
:::
