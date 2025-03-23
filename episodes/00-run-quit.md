---
title: Running and Quitting
teaching: 15
exercises: 0
---

::::::::::::::::::::::::::::::::::::::: objectives

- Launch the JupyterLab server.
- Create a Jupyter notebook.
- Shutdown the JupyterLab server.
- Create Markdown cells in a notebook.
- Create and run Python cells in a notebook.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How can I run Python programs in JuypterLab?

::::::::::::::::::::::::::::::::::::::::::::::::::

To run Python, we are going to use [Jupyter Notebooks] via [JupyterLab] for the remainder of this workshop. Jupyter notebooks are common in data science and visualization and serve as a convenient common-denominator experience for running Python code interactively where we can easily view and share the results of our Python code.

There are other ways of editing, managing, and running code. Software developers often use an integrated development environment (IDE) like [PyCharm] or [Visual Studio Code], or text editors like Vim or Emacs, to create and edit their Python programs. After editing and saving your Python programs you can execute those programs within the IDE itself or directly on the command line. In contrast, Jupyter notebooks let us execute and view the results of our Python code immediately within the notebook.

JupyterLab has several other handy features:

- You can easily type, edit, and copy and paste blocks of code.
- Tab complete allows you to easily access the names of things you are using
  and learn more about them.
- It allows you to annotate your code with links, different sized text, bullets, etc. to make it more accessible to you and your collaborators.
- It allows you to display figures next to the code that produces them   to tell a complete story of the analysis.

Each notebook contains one or more cells that contain code, text, or images.

## Getting Started with JupyterLab

JupyterLab is an application server with a web user interface from [Project Jupyter] that enables one to work with documents and activities such as Jupyter notebooks, text editors, terminals, and even custom components in a flexible, integrated, and extensible manner. JupyterLab requires a reasonably up-to-date browser (ideally a current version of Chrome, Safari, or Firefox); Internet
Explorer versions 9 and below are *not* supported.

In this lesson we will run JupyterLab on [NCI's Gadi supercomputer].

:::::::::::::::::::::::::::::::::::::::::  callout

## JupyterLab? What about Jupyter notebooks?

[JupyterLab] is the next stage in the evolution of the Jupyter Notebook. If you have prior experience working with Jupyter notebooks, then you will have a good idea of what to expect from JupyterLab.

Experienced users of Jupyter notebooks interested in a more detailed discussion of the similarities and differences between the JupyterLab and Jupyter notebook user interfaces can find more information in the [JupyterLab Interface] documentation.


::::::::::::::::::::::::::::::::::::::::::::::::::

## The JupyterLab Interface

JupyterLab has many features found in traditional integrated development environments (IDEs) but is focused on providing flexible building blocks for interactive, exploratory computing.

The [JupyterLab Interface] consists of the Menu Bar, a collapsable Left Side Bar, and the Main Work Area which contains tabs of documents and activities.

### Menu Bar

The Menu Bar at the top of JupyterLab has the top-level menus that expose various actions available in JupyterLab along with their keyboard shortcuts (where applicable). The following menus are included by default.

- **File:** Actions related to files and directories such as *New*, *Open*, *Close*, *Save*, etc. The *File* menu also includes the *Shut Down* action used to shutdown the JupyterLab server.
- **Edit:** Actions related to editing documents and other activities such as *Undo*, *Cut*, *Copy*, *Paste*, etc.
- **View:** Actions that alter the appearance of JupyterLab.
- **Run:** Actions for running code in different activities such as notebooks and code consoles (discussed below).
- **Kernel:** Actions for managing kernels. Kernels in Jupyter will be explained in more detail below.
- **Tabs:** A list of the open documents and activities in the main work area.
- **Settings:** Common JupyterLab settings can be configured using this menu. There is also an *Advanced Settings Editor* option in the dropdown menu that provides more fine-grained control of JupyterLab settings and configuration options.
- **Help:** A list of JupyterLab and kernel help links.

:::::::::::::::::::::::::::::::::::::::::  callout

## Kernels

The [JupyterLab docs] define kernels as "separate processes started by the server that runs your code in different programming languages and environments." When we open a Jupyter Notebook, that starts a kernel - a process - that is going to run the code. In this lesson, we'll be using the Jupyter ipython kernel which lets us run Python 3 code interactively.

Using other Jupyter [kernels for other programming languages] would let us
write and execute code in other programming languages in the same JupyterLab interface, like R, Java, Julia, Ruby, JavaScript, Fortran,etc.

::::::::::::::::::::::::::::::::::::::::::::::::::

### Left Sidebar

The left sidebar contains a number of commonly used tabs, such as a File Browser (showing the contents of the directory where the JupyterLab server was launched), a list of Running terminals and Kernels, a Table of Contents, and the Extension Manager. 

Under the File Browser tab you will also find buttons for the Launcher and to create New Folders, Upload Files and Refresh the File List.

A screenshot of the default Left Side Bar is provided below.

<p align='center'>   <img alt="JupyterLab Left Side Bar" src="fig/0_jupyterlab_left_side_bar.png" width="250"/>
</p>

The left sidebar can be collapsed or expanded by selecting "Show Left Sidebar" in the View menu or by clicking on the active sidebar tab.

### Main Work Area

The main work area in JupyterLab enables you to arrange documents (notebooks, text files, etc.) and other activities (terminals, code consoles, etc.) into panels of tabs that can be resized or subdivided. A screenshot of the default Main Work Area is provided below.

If you do not see the Launcher tab, click the blue plus sign under the "File" and "Edit" menus and it will appear.

<p align='center'>   <img alt="JupyterLab Main Work Area" src="fig/0_jupyterlab_main_work_area.png" width="750"/>
</p>

You can subdivide a tab panel by dragging a tab to the left, right, top, or bottom of the panel.

## Creating a Jupyter Notebook

To open a new notebook click the Python 3 icon under the *Notebook* header in the Launcher tab in the main work area. You can also create a new notebook by selecting *New -> Notebook* from the *File* menu in the Menu Bar.

Additional notes on Jupyter notebooks.

- Notebook files have the extension `.ipynb` to distinguish them from plain-text Python programs.
- Notebooks can be exported as Python scripts that can be run from the command line by selecting *Save and Export Notebook As... -> Executable Script* from the *File* menu in the Menu Bar.

:::::::::::::::::::::::::::::::::::::::::  callout

## How It's Stored

- The notebook file is stored in a format called JSON.
- Just like a webpage, what's saved looks different from what you see in your browser.
- But this format allows Jupyter to mix source code, text, and images, all in one file.
  
::::::::::::::::::::::::::::::::::::::::::::::::::


## The Notebook has Command and Edit modes.

- If you press <kbd>Esc</kbd> and <kbd>Return</kbd> alternately, the outer border of your code cell will change from gray to blue.
- These are the **Command** (gray) and **Edit** (blue) modes of your notebook.
- Command mode allows you to edit notebook-level features, and Edit mode changes the content of cells.
- When in Command mode (esc/gray),
  - The <kbd>b</kbd> key will make a new cell below the currently selected cell.
  - The <kbd>a</kbd> key will make one above.
  - The <kbd>x</kbd> key will delete the current cell.
  - The <kbd>z</kbd> key will undo your last cell operation (which could be a deletion, creation, etc).
- All actions can be done using the menus, but there are lots of keyboard shortcuts to speed things up.

:::::::::::::::::::::::::::::::::::::::  challenge

## Command Vs. Edit

In the Jupyter notebook page are you currently in Command or Edit mode?  
Switch between the modes.
Use the shortcuts to generate a new cell.
Use the shortcuts to delete a cell.
Use the shortcuts to undo the last cell operation you performed.

:::::::::::::::  solution

## Solution

Command mode has a grey border and Edit mode has a blue border.
Use <kbd>Esc</kbd> and <kbd>Return</kbd> to switch between modes.
You need to be in Command mode (Press <kbd>Esc</kbd> if your cell is blue).  Type <kbd>b</kbd> or <kbd>a</kbd>.
You need to be in Command mode (Press <kbd>Esc</kbd> if your cell is blue).  Type <kbd>x</kbd>.
You need to be in Command mode (Press <kbd>Esc</kbd> if your cell is blue).  Type <kbd>z</kbd>.



:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

### Use the keyboard and mouse to select and edit cells.

- Pressing the <kbd>Return</kbd> key turns the border blue and engages Edit mode, which allows   you to type within the cell.
- Because we want to be able to write many lines of code in a single cell,
  pressing the <kbd>Return</kbd> key when in Edit mode (blue) moves the cursor to the next line in the cell just like in a text editor.
- We need some other way to tell the Notebook we want to run what's in the cell.
- Pressing <kbd>Shift</kbd>\+<kbd>Return</kbd> together will execute the contents of the cell.
- Notice that the <kbd>Return</kbd> and <kbd>Shift</kbd> keys on the right of the keyboard are right next to each other.

### The Notebook will turn Markdown into pretty-printed documentation.

- Notebooks can also render [Markdown].
  - A simple plain-text format for writing lists, links, and other things that might go into a web page.
  - Equivalently, a subset of HTML that looks like what you'd send in an old-fashioned email. 
- Turn the current cell into a Markdown cell by entering the Command mode (<kbd>Esc</kbd>/gray) and press the <kbd>m</kbd> key.
- `In [ ]:` will disappear to show it is no longer a code cell and you will be able to write in Markdown.
- Turn the current cell into a Code cell by entering the Command mode (<kbd>Esc</kbd>/gray) and press the <kbd>y</kbd> key.

:::::::::::::::::::::::::::::::::::::::  spoiler


### Markdown does most of what HTML does.

Examples of markdown syntax and its rendered output.

+---------------------------------------+------------------------------------------------+
| Markdown code                         | Rendered output                                |
+=======================================+================================================+
+---------------------------------------+------------------------------------------------+
| ```                                   | <p></p>                                        |
| *   Use asterisks                     | -   Use asterisks                              |
| *   to create                         | -   to create                                  |
| *   bullet lists.                     | -   bullet lists.                              |
| ```                                   |                                                |
+---------------------------------------+------------------------------------------------+
+---------------------------------------+------------------------------------------------+
| ```                                   | <p></p>                                        |
| 1.   Use numbers                      | 1.   Use numbers                               |
| 1.   to create                        | 2.   to create                                 |
| 1.   bullet lists.                    | 3.   numbered lists.                           |
| ```                                   |                                                |
+---------------------------------------+------------------------------------------------+
+---------------------------------------+------------------------------------------------+
| ```                                   | <p></p>                                        |
| *  You can use indents                | - You can use indents                          |
|   *  To create sublists               |   - To create sublists                         |
|   *  of the same type                 |   - of the same type                           |
| *  Or sublists                        | - Or sublists                                  |
|   1. Of different                     |   1. Of different                              |
|   1. types                            |   2. types                                     |
| ```                                   |                                                |
+---------------------------------------+------------------------------------------------+
+---------------------------------------+------------------------------------------------+
| ```                                   | <p></p>                                        |
| # A Level-1 Heading                   | ## A Level-1 Heading                           |
| ```                                   |                                                |
+---------------------------------------+------------------------------------------------+
+---------------------------------------+------------------------------------------------+
| ```                                   | <p></p>                                        |
| ## A Level-2 Heading (etc.)           | ### A Level-2 Heading (etc.)                   |
| ```                                   |                                                |
+---------------------------------------+------------------------------------------------+
+---------------------------------------+------------------------------------------------+
| ```                                   | <p></p>                                        |
| Line breaks                           | Line breaks                                    |
| don't matter.                         | don't matter.                                  |
|                                       |                                                |
| But blank lines                       | But blank lines                                |
| create new paragraphs.                | create new paragraphs.                         |
| ```                                   |                                                |
+---------------------------------------+------------------------------------------------+
+---------------------------------------+------------------------------------------------+
| ```                                   | <p></p>                                        |
| [Links](http://software-carpentry.org)| [Links](https://software-carpentry.org)        |
| are created with `[...](...)`.        | are created with `[...](...)`.                 |
| Or use [named links][data-carp].      | Or use [named links][data_carpentry].          |
|                                       |                                                |
| [data-carp]: http://datacarpentry.org |                                                |
| ```                                   |                                                |
+---------------------------------------+------------------------------------------------+

:::::::::::::::::::::::::::::::::::::::::::::::

Now that are you are familear with Jupyter Notebooks in JupyterLab, let us set up  our environment for the workshop by making copies of today's workshop notebooks and checking we have the packages we need installed.

## Prepare for the Workshop

### Make a copy of the lesson notebooks

In a blank cell of a notebook, copy the lesson notebooks into your working directory. Note that by running `!<command>` inside a Jupyter Notebook cell, we are able to interact directly with the underlying operating system as if from a terminal command line.

These commands will:
- creates a new folder in your working directory for the lesson notebooks
- copies the lesson notebooks from the project directory to your working directory
- lists the contents of the new folder to verify the files were copied successfully

```bash
!mkdir /scratch/cd82/$USER/notebooks
!cp /scratch/cd82/icwcnn-files/*.ipynb /scratch/cd82/$USER/notebooks/
!ls /scratch/cd82/$USER/notebooks/
```

![](fig/00_workingdir_scripts.png){alt='Screenshot of the contents of the notebooks folder in the users working directory.'}

### Check your environment has the necessary libraries installed

On the Left Sidebar, navigate to the *notebooks* directory you just created. 

Open the *00_setup_check.ipynb* notebook and run the cells to check that you have the necessary libraries installed.

![](fig/00_package_check_output.png){alt='Screenshot of the Jupyter Notebook with list of library versions and no error messages.'}

## Closing JupyterLab

Save your work!

Click the 'Close' button on the JupyterLab tab in your browser to close the JupyterLab server.

If you wish to come back to your session and you still have walltime remaining, click the **Open JupyterLab** on the NCI ARE page.to restart the JupyterLab server.

If you are finished with your session, click the **Cancel** button on the NCI ARE page to cancel the session and free up resources for other users.

## Shutting Down JupyterLab

Save your work!

BEWARE! Shutting down the Jupyter Server with these steps will **Delete** your JupyterLab session, *even if you have walltime remaining*.

From the Menu Bar select the "File" menu and then choose "Shut Down" at the bottom of the dropdown menu. You will be prompted to confirm that you wish to shutdown the JupyterLab server (don't forget to save your work!). Click "Shut Down" to shutdown the JupyterLab server.

<!-- Collect your link references at the bottom of your document -->

[Jupyter Notebooks]: https://jupyter.org/
[JupyterLab]: https://jupyterlab.readthedocs.io/en/stable/
[PyCharm]: https://www.jetbrains.com/pycharm/
[Visual Studio Code]: https://code.visualstudio.com/
[NCI's Gadi supercomputer]: https://nci.org.au/news-events/events/introduction-gadi-4
[Project Jupyter]: https://jupyter.org/
[JupyterLab Interface]: https://jupyterlab.readthedocs.io/en/stable/user/interface.html
[JupyterLab docs]: https://jupyterlab.readthedocs.io/en/stable/user/documents_kernels.html
[kernels for other programming languages]:  https://github.com/jupyter/jupyter/wiki/Jupyter-kernels
[official notebook documentation]: https://jupyterlab.readthedocs.io/en/stable/user/notebook.html
[markdown]: https://en.wikipedia.org/wiki/Markdown
[data_carpentry]: https://datacarpentry.org

:::::::::::::::::::::::::::::::::::::::: keypoints

- Python scripts are plain text files.
- Use the Jupyter Notebook for editing and running Python.
- The Notebook has Command and Edit modes.
- Use the keyboard and mouse to select and edit cells.
- The Notebook will turn Markdown into pretty-printed documentation.
- Markdown does most of what HTML does.

::::::::::::::::::::::::::::::::::::::::::::::::::


