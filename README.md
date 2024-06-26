# PROBABILITY AND STATISTICS A/B (MATHEMATICAL STATISTICS) <!-- omit in toc -->

## Course materials for PROBABILITY AND STATISTICS A/B (MATHEMATICAL STATISTICS)  <!-- omit in toc -->

Teruo Nakatsuma (Faculty of Economics, Keio University, Japan)

---

- [How to set up Python and necessary packages](#how-to-set-up-python-and-necessary-packages)
  - [Step 1: Installing Anaconda](#step-1-installing-anaconda)
  - [Step 2: Creating an environment](#step-2-creating-an-environment)
  - [Troubleshooting about installation](#troubleshooting-about-installation)
    - [1. Retry installation](#1-retry-installation)
    - [2. (macOS) Installing Command Line Tools for Xcode](#2-macos-installing-command-line-tools-for-xcode)
- [How to start Jupyter Notebook](#how-to-start-jupyter-notebook)
  - [Troubleshooting about Jupyter Notebook](#troubleshooting-about-jupyter-notebook)
- [Jupyter Notebooks and related files in `notebook-a`](#jupyter-notebooks-and-related-files-in-notebook-a)
- [Jupyter Notebooks and related files in `notebook-b`](#jupyter-notebooks-and-related-files-in-notebook-b)

---

## How to set up Python and necessary packages

I strongly recommend using [Anaconda](https://www.anaconda.com/). It can install Python along with numerous essential packages at once and allows us to manage those packages flexibly.

### Step 0: For Windows PC users only

Download and install [Microsoft Visual C++ Redistributable](https://learn.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170#visual-studio-2015-2017-2019-and-2022). There are three versions:

- [ARM64](https://aka.ms/vs/17/release/vc_redist.arm64.exe)
- [X86](https://aka.ms/vs/17/release/vc_redist.x86.exe)
- [X64](https://aka.ms/vs/17/release/vc_redist.x64.exe)

If your PC's CPU is manufactured by Intel or AMD, the X64 version is suitable.

### Step 1: Installing Anaconda

1. If you have an older Anaconda on your PC, uninstall it completely by folloiwng [instructions](https://docs.anaconda.com/anaconda/install/uninstall/).

2. Download an Anaconda installer (Windows, macOS or Linux) from [here](https://www.anaconda.com/products/distribution). Choose an installer for your OS. For macOS, you should check whether Intel chip or Apple Silicon chip is used and download the corresponding installer.

3. Doubleclick the installer and follow the instructions on the screen. Do not change the default settings.

### Step 2: Creating an environment

Start `Anaconda Powershell Prompt` (Windows) or `Terminal` (macOS, Linux) and type

```IPython
conda update conda
```

This will update conda (package manager) in Anaconda.

(Optional) To update all packages, type

```IPython
conda update -n base --all
```

Then type

(Windows)

```IPython
conda create -n bayes -c conda-forge jupyterlab seaborn bokeh jupyter_bokeh pymc python-graphviz
```

(macOS)

```IPython
conda create -n bayes -c conda-forge jupyterlab seaborn bokeh jupyter_bokeh pymc numpyro python-graphviz
```

This will create the environment for PyMC. Then type

```IPython
conda activate bayes
```

(Windows) Install `numpyro` by typing

```IPython
pip install numpyro
```

Finally, type

```IPython
python -m ipykernel install --user --name bayes --display-name "Python (Bayes)"
```

Now you are ready for Python!

---

## Troubleshooting about installation

### 1. Retry installation

If you encounter any errors during the installation process, go back to the default environment by typing

```IPython
conda deactivate
```

and remove `bayes` by typing

```IPython
conda env remove -n bayes
```

Then redo **Step 2**.

### 2. (macOS) Installing Command Line Tools for Xcode

In case the computer says `Command Line Tools for Xcode` is missing,  install it as follows.

1. Install `Xcode` from App Store.

2. Start `Xcode`. If a pop-up window asks you to install additional tools, follow the instruction. Quit `Xcode`.

3. Start `Terminal` and install `Command Line Tools for Xcode` by typing

``` IPython
sudo xcode-select --install
```

If asked, type your login password.

---

## How to start JupyterLab

### Method 1: From the command line

Start `Anaconda Powershell Prompt` (Windows) or `Terminal` (macOS, Linux) and type

```IPython
jupyter lab --port=8888
```

Your default browser will pop up.

### Method 2: From Anaconda Navigator

Start `Anaconda Navigator`. You may find it in `Start Menu` (Windows) or `Launchpad` (macOS). Then click the icon named `JupyterLab`.

### Troubleshooting about JupyterLab

1. For a `Bokeh` interactive plot to work properly, the Jupyter Notebook server must use `port 8888` which is set by default. In case this port is occupied by another Jupyter Notebook server, you need to stop it by typing

```IPython
jupyter server stop
```

before you open a new JupyterLab session. If this does not work, reboot your PC.

2. PyMC may fail when you start your JupyterLab session in the `bayes` environment. If so, you must start it in the `base` environment. If the prompt starts with `(bayes)`, type

```IPython
conda deactivate
```

Then it will switch back to the `base` environment.

## Jupyter Notebooks and related files in `notebook-a`

| file name                  | description                              |
|:---------------------------|:-----------------------------------------|
| Cholera.csv                | London cholera pandemic data             |
| Mroz.csv                   | US women's labor participation data      |
| StrikeDur.csv              | strikes duration data                    |
| USStocksSW.csv             | monthly US stock returns data            |
| ar1_process.ipynb          | convergence of the AR(1) process         |
| cholera.ipynb              | Bernoulli model of the cholera data      |
| example_bernoulli.ipynb    | posterior inference on Bernoulli dist.   |
| example_exponential.ipynb  | posterior inference on exponential dist. |
| example_normal.ipynb       | posterior inference on normal dist.      |
| example_poisson.ipynb      | posterior inference on Poisson dist.     |
| exponential_duration.ipynb | exponential duration model               |
| Housing.csv                | sales prices of houses                   |
| housing_price.ipynb        | hedonic price model of houses            |
| labor_participation.ipynb  | logit model of labor participation       |
| logit.ipynb                | PyMC example of logit model              |
| poisson_regression.ipynb   | PyMC example of Poisson regression model |
| probit.ipynb               | PyMC example of probit model             |
| prussian.csv               | Prussian army horse kick data            |
| regression.ipynb           | PyMC example of regression analysis      |
| ships_damage.ipynb         | Poisson regression model of ships damage |
| ships.csv                  | ships damage data                        |
| strikes_duration.ipynb.    | strikes duration                         |
| wage_education.ipynb       | relationship between wage and education  |

---

## Jupyter Notebooks and related files in `notebook-b`

| file name | description |
|:-------------------------------|:------------------------------------------|
| bivariate_distribution.ipynb   | examples of bivariate distributions       |
| large_sample.ipynb             | consistency and asymptotic normality      |
| markovchain.ipynb              | Markov chain                              |
| probability_distribution.ipynb | examples of probability distributions     |
| python_introduction.ipynb      | simple example of Bayes' theorem          |
| skewness_kurtosis.ipynb        | skewness and kurtosis                     |

---
