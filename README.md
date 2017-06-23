# SFC Summer School in Paris - July 2017

This folder contains all the information regarding the series of three labs organised during the <a href="https://cepn.univ-paris13.fr/applied-stock-flow-consistent-macro-modelling/">Applied Stock-Flow consistent and Agent-based Macro-modelling – Summer School</a> held in Paris in July 2017

# Prerequisites

## R and Rstudio

In order to get the most out of the labs, the students are required to have installed <a href="http://www.r-project.org2">R</a> and <a href="http://www.rstudio.com">RStudio</a>. In order to get familiarised with R, there are multiple tutorials and MOOCS on-line, I recommend the <a href="https://www.coursera.org/learn/r-programming">Coursera R Programming</a> course but you will find many others. The students are also required to do the following homework in `Swirl`.

### Swirl

In order to do this homework, you need to have `Swirl` installed. To do so execute the following command. Note that you only need to do this once on a computer but you will have to do it every time you work on a different computer.

```{r, eval=FALSE}
install.packages("swirl")
```

`Swirl` is a package that allows you to learn R by offering interactive lectures. For more information see http://swirlstats.com/

If you already have installed the package, you are ready to start using it. In order to do so, you first need to load it using the command here under. Note that if the command generates an error, it is probable that you haven't installed `Swirl`.

```{r, eval=FALSE}
library(swirl)
```

Once swirl is loaded, we first need to install all the lectures we find interesting. The following code installs these 3 lectures. If the code generates an error, there is a chance that you did not load correctly the `Swirl` package.Note that you only need to do this once on a computer but you will have to do it every time you work on a different computer.

```{r, eval=FALSE}
install_course("R Programming")
install_course("The R Programming Environment")
install_course("Exploratory Data Analysis")
```

You are now ready to start using `Swirl` to do so, execute the following line of code and follow the instructions.

```{r, eval=FALSE}
swirl()
```

### Your homework

I want you to do all the lectures from "The R Programming Environment" set and lecture 9-11 and 13-15 from the "R Programming" set. This should give you a good overview of R programming.

## Required packages

### pdfetch

During the labs we will use different packages. The first lecture will concentrate on the system of national accounts and Eurostat data. To access easily Eurostat data, we will use the <a href="https://cran.r-project.org/web/packages/pdfetch/pdfetch.pdf">package pdfetch</a>.

This is how you install pdfetch:

```{r, eval=FALSE}
install.packages("pdfetch")
```

### PKSFC

In order to design, simulate and analyse SFC models, we will use the <a href="https://github.com/S120/PKSFC">PKSFC package</a>. The package can be downloaded in the root folder. Note that the package needs a version of R above or equal to 3.1.1. Furthermore, you will need to install `expm`, `igraph` and `networkD3`. You will hence need to use the following command.

```{r, eval=F}
install.packages("expm")
install.packages("igraph")
install.packages("networkD3")
```

Once those packages have been installed, download the PK-SFC package on your computer and store it in a folder of your choice. Make sure that the name of the package is "PKSFC_1.5.tar.gz". Then run the following command line. It will install the package from your local folder where 'pathToYourFolder' represent the path to the folder where you downloaded the package.

```{r, eval=F}
install.packages("pathToYourFolder/PKSFC_1.5.tar.gz",repos = NULL, type="source")
```

You are almost set, now you need to load the package. In order to do so, you should run the following line. You might have some output but if no error message is being printed this means you are now ready to use the PK-SFC.

```{r}
library(PKSFC)
```

The following paper <a href="http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2492242">Visualising Stock Flow Consistent Models as Directed Acyclic Graphs</a>, shows how any SFC model can be seen as a directed graph (DG) and allows for a different representation than the traditional Transaction-Flow and Balance Sheet Matrices. Obviously these representations are more useful for large models than small models. The package includes the functions needed to obtain the DG representation. However, in order to use these functionalities, the package `Rgraphviz` needs to be installed. Because it is not stored in CRAN, you need to use the following commands to install it.

According to the latest [README](http://www.bioconductor.org/packages/2.11/bioc/readmes/Rgraphviz/README):

```{r,eval=FALSE}
Rgraphviz now comes bundles with Graphviz. This should greatly simplify installation 
on all platforms, compared with earlier versions.
```

Bioconductor 2.11 contains a lot of libraries that you might not want or need, but it does seem to be the easiest path to achieving what you want. These are the instructions on the [Rgraphviz homepage](http://www.bioconductor.org/packages/2.11/bioc/html/Rgraphviz.html):

```{r,eval=F}
source("http://bioconductor.org/biocLite.R")
biocLite("Rgraphviz")
```

In order to test for the success of the installation:
```{r}
library("Rgraphviz")
```

## Readings

### Lab 1 National Accounts: rooting the SFC approach in empirical data

Godley, W. and M. Lavoie (2007) “Monetary Economics: An Integrated Approach to Credit, Money, Income, Production and Wealth”, Basingstoke, Palgrave Macmillan. Chapters 1-2

<a href="http://ec.europa.eu/eurostat/cache/metadata/Annexes/nasa_10_f_esms_an1.pdf">European System of Accounts (2010)</a>

<a href="http://ec.europa.eu/eurostat/web/sector-accounts">Sectoral account description by Eurostat</a>

<a href="https://cran.r-project.org/web/packages/pdfetch/pdfetch.pdf">pdfetch package description</a>

### Lab 2 The PKSFC R package: simulating simple models

Godley, W. and M. Lavoie (2007) “Monetary Economics: An Integrated Approach to Credit, Money, Income, Production and Wealth”, Basingstoke, Palgrave Macmillan. Chapters 3-4.

Caverzasi, E. and A Godin (2015) “Post-Keynesian stock-flow-consistent modelling: a survey”, *Cambridge Journal of Economics*, 39 (1), 157-187.

Fennell, P., O'Sullivan, D., Godin, A. and S. Kinsella (2016) "Is it possible to visualise any stock flow consistent model as a directed acyclic graph?", *Computational Economics*, 48(2), 307-316.

<a href="https://github.com/S120/PKSFC/tree/master/Tutorials">PKSFC Tutorial webpages</a>

### Lab 3 Empirically calibrated simple SFC models

Godley, W. and M. Lavoie (2007) “Monetary Economics: An Integrated Approach to Credit, Money, Income, Production and Wealth”, Basingstoke, Palgrave Macmillan. Chapters 3-4.

Burgess, S., Burrows, O., Godin, A., Kinsella, S. and S. Millard (2016) "A dynamic model of financial balances for the United Kingdom". Bank of England *Staff Working Paper*, no. 614.

<a href="https://github.com/S120/PKSFC/tree/master/Tutorials">PKSFC Tutorial webpages</a>