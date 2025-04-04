# INSTRUCTIONS BEFORE ARRIVAL

Please follow the below instructions before arriving at the course.
If you encounter any issues, please contact us (Romain), and we will troubleshoot, 
so that you can arrive with everything set up on your computer.


# WORK ON SERVERS vs. LOCAL MACHINES

You will set up everything on your local machine, instead of us providing a consistent and working server for 
the duration of this course. Why? Because you will also not work on a nicely set up server at home, but with 
your own machine. Thus, we don't want to create an artificial environment for you during the course, 
but give you the chance to set up everything such that you can go home and continue with the work.

> [!IMPORTANT]
> We recommend to have at least 8GB of RAM on your computer, as some of the calculations can 
> be quite memory-intensive.

# ANACONDA AND GIT

We ask the participants to download and install Anaconda (or the 
Python environments manager of your choice) and Git 
before the course:

- Anaconda: https://www.anaconda.com/products/distribution
- Git: https://git-scm.com/downloads

We recommend using homebrew to install Git on Mac:

```bash
  brew install git
```

For Windows users, you can download the Git installer from the link above (you most likely
need the 64-bit version).

## Clone this repository

Option A: Download the [GitHub desktop](https://desktop.github.com/download/) application, 
click to clone a repository, and paste the link of the repository shown further below.

Option B: Via the CLI (**C**ommand **L**ine **I**nterface): using your Windows/Mac terminal, 
navigate to the folder where you want to store the course material. For example, you can 
create a folder called `brightway-2025` in your `Documents` folder. 

To know your current location in the terminal, you can run the following command:

```bash
  pwd
```

To navigate to the `Documents` folder, you can run the following command:

```bash
  cd Documents
```

To go back to the parent folder, you can run the following command:

```bash
  cd ..
```

If you want to create a new folder, you can run the following command:

```bash
  mkdir training-brightway-2025
```

Once you are in the folder of your choice, you can **clone** this GitHub repository 
using Git onto your computer by running the following command in your terminal:

```bash
  git clone https://github.com/Laboratory-for-Energy-Systems-Analysis/training-day-dtu-2025.git
```

You can now navigate to the `training-day-dtu-2025` folder and access its content on your computer.

## Environments setup

When you will do exercises on your computer, you will use a number of libraries
that are not installed by default by Anaconda. To make sure you have all the
necessary libraries, we will create Anaconda **environments** for you, using
**recipes** that we have prepared.

We have prepared a conda recipe file which installs the following environment:
- `bw2_env_xxx.yaml`: it will install the `brightway` library as well as `activity-browser`

After running the recipe file, you will have the following environment on your computer:
- `bw2`

Here is how to install this environment:

Using your terminal, navigate to the `envs` folder of the repository:

```bash
  cd training-day-dtu-2025/envs
```

Then, run the following command to create the `bw2` environment:

On Windows or Mac with an Intel processor:


```bash
  conda env create -f bw2_env_win64.yaml
```

On a Mac with an M1/2/3/4 processor:

```bash
  conda env create -f bw2_env_osxARM.yaml
```

This will create a conda environment called `bw2` with all the required dependencies.

You can check that the environments have been created by running the following command:

```bash
  conda env list
```

You should see the environment listed in the terminal (plus the `base` environment).

You can activate an environment by running the following command:

```bash
  conda activate wurst
```

and check the installed packages by running:

```bash
  conda list
```

## Ecoinvent database

You need to acquire credentials (username and password) to 
download the [ecoinvent](https://ecoinvent.org) database. Ask the person in charge of your group/university to get these credentials. 
Or ask the ecoinvent support if you can't find out in-house.

We will be using the ecoinvent 3.10 cut-off database for the course.

In the terminal, place yourself in the `training-day-dtu-2025/envs` folder and:

1. Activate the environment you have created (i.e., `bw2`):

```bash
  conda activate bw2
```

2. Run the Python file `prepare_project.py` which will create a ``brightway2`` project called `training-day` and import `ecoinvent-3.10-cutoff`.

```bash
  python prepare_project.py "ecoinvent_username" "ecoinvent_password"
```

Make sure to replace `"ecoinvent_username"` and `"ecoinvent_password"` with your actual ecoinvent credentials.

> [!IMPORTANT]
> For Mac users, use single quote characters around the username and password.

If successful, you should see the following message:

```bash
  List of databases in training-day project: Databases dictionary with 2 object(s):
        biosphere
        ecoinvent-3.10-cutoff
```

If not, please [contact us](mailto:romain.sacchi@psi.ch).

# Code editor

We recommend using [PyCharm](https://www.jetbrains.com/de-de/pycharm/download/) or [Visual Studio Code] as an IDE 
(Integrated Development Environment) for the course.

> [!NOTE]
> Both are free if you select the "Community Edition" version (not Professional). 
> They have a lot of features that will help you during the course.
