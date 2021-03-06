-   [Overview](#overview)
-   [Goals and Syllabus](#goals-and-syllabus)
    -   [Part 1 (1.5hr, general audience): *Why it’s
        important*.](#part-1-1.5hr-general-audience-why-its-important.)
    -   [Part 2 (4 hr, folks analyzing data): *Doing It Right -
        Workflows*.](#part-2-4-hr-folks-analyzing-data-doing-it-right---workflows.)
    -   [Part 3 (2 hr, folks using R): *Doing It Right - R
        Packages*.](#part-3-2-hr-folks-using-r-doing-it-right---r-packages.)
    -   [Part 4 (0.5hr, general audience): *Looking at
        Replicability*.](#part-4-0.5hr-general-audience-looking-at-replicability.)
-   [Software Required](#software-required)
    -   [R and RStudio](#r-and-rstudio)
    -   [R Packages](#r-packages)
        -   [Windows and RTools](#windows-and-rtools)
        -   [tinytex and PDF Output](#tinytex-and-pdf-output)
        -   [Bonus: Git and GitHub](#bonus-git-and-github)
-   [An Example Analysis](#an-example-analysis)
-   [An Example Package](#an-example-package)
-   [Further Resources](#further-resources)
    -   [Places to Learn More](#places-to-learn-more)
    -   [Notes for Participants](#notes-for-participants)

Overview
========

Welcome to the FDA’s 2018 Short Course on Reproducible Research (RR)
Using R and RStudio!

This day-long course will be presented at the FDA on Fri, Nov 16, 2018
by [Keith Baggerly](mailto:kabagg@gmail.com).

Goals and Syllabus
==================

The goal of this course is to introduce you to the issues associated
with making research **reproducible**, in the sense that someone else,
starting with your data and code, should be able to easily recreate your
results. This is an important subset of the issues associated with
making research **replicable**, where someone else performing similar
experiments and analyses with new data could reasonably expect to get
similar results. We’ll look at examples showing the depth and breadth of
the problem, motivating the drive to do things better, and then
introduce recently developed tools that make adopting better practices
much easier.

The course is split into 4 parts, which vary in length and the level of
background required.

Part 1 (1.5hr, general audience): *Why it’s important*.
-------------------------------------------------------

We use in-depth analyses of a few problematic case studies to show how
basic mistakes can and have negatively impacted patient care. We’ll
apply forensic bioinformatics to reverse engineer what must have
happened in these cases, and discuss the breadth of the problem.

[Part 1 Slides](Slides/fda_rr_part_1.pdf)

Part 2 (4 hr, folks analyzing data): *Doing It Right - Workflows*.
------------------------------------------------------------------

We’ll introduce ways of organizing data, code, and text in ways that
will make it easier for others to get the same results you got, and
tools available today which make implementing these practices easier.
We’ll do some of this live with toy examples, and examine more realistic
examples with prebuilt analyses. My own examples will use R and RStudio,
but the general concepts presented here can be adapted to other
programming environments. A short topic list includes

-   literate programming with markdown/markdown
-   working on the web with git/github
-   README files
-   folder structures
-   projects, encapsulation, and here
-   gathering raw data
-   make, appoximations, and file naming
-   report structure
-   sanity checks

[Part 2 Slides](Slides/fda_rr_part_2.pdf)

Part 3 (2 hr, folks using R): *Doing It Right - R Packages*.
------------------------------------------------------------

For folks who are doing analyses in R, R packages are everywhere. Recent
packages, specifically `devtools` and `roxygen2`, have made it much
easier to write even more new packages, so you can now write a package
in 15 minutes or so (with some practice). We’re going to show you how,
and then use what we’ve learned to share scripts that make organization
easier. We’ll discuss

-   the structure of R packages
-   DESCRIPTIONs, LICENSEs, and documentation
-   vignettes
-   storing data in packages
-   storing templates in packages
-   storing analyses in packages

[Part 3 Slides](Slides/fda_rr_part_3.pdf)

Part 4 (0.5hr, general audience): *Looking at Replicability*.
-------------------------------------------------------------

Even when findings are reproducible, they may not be replicable. We
review some common problems leading to poor replicability, and discuss
various sanity checks we can try putting in place to let us catch some
of the bigger ones.

[Part 4 Slides](Slides/fda_rr_part_4.pdf)

Software Required
=================

Parts 2 and 3 of the course will involve a good deal of live demo and
opportunities to try it yourself, so you’ll want to have a laptop you
can create and edit files on with recent versions of the relevant
software (all free) preinstalled. Specifically, you’ll want R, RStudio,
and a bunch of R packages.

R and RStudio
-------------

On my MacBook Pro laptop (OS X 10.13.6) I’m currently running

-   R version 3.5.1 (2018-07-02) and
-   RStudio version 1.2.1047

R is available from [CRAN](https://cran.r-project.org/). A list of CRAN
mirrors is available from [the R Project](https://www.r-project.org/).

RStudio 1.2 is currently in “preview release”, and is available
[here](https://www.rstudio.com/products/rstudio/download/preview/).

RStudio 1.1, the “official version”, is available
[here](https://www.rstudio.com/products/rstudio/download/).

I’d encourage you to get 1.2 for two reasons. First, it’s likely to be
officially released quite soon, per
[discussion](https://community.rstudio.com/t/rstudio-1-2-release-date-interval/9522).
Second, it includes better support for Python via the `reticulate`
package, and the capability to produce more types of output files,
including PowerPoint.

R Packages
----------

The main R packages I’ll use (in alphabetic order, with my version
numbers shown) are:

-   devtools 1.13.6
-   downloader 0.4
-   here 0.1
-   knitr 1.20
-   readr 1.1.1
-   rmarkdown 1.10
-   roxygen2 6.1.0

I may use other packages from the tidyverse without extensive
discussion:

-   tidyverse 1.2.1

### Windows and RTools

For those of you running Windows machines, you’ll also need to install

-   [Rtools](https://cran.r-project.org/bin/windows/Rtools/)

for Part 3 of the course, in order to get new packages you create to
compile properly. Jeff Leek gives a slightly more expansive description
of installation
[here](http://jtleek.com/modules/01_DataScientistToolbox/02_10_rtools/).

### tinytex and PDF Output

The `rmarkdown` package uses LaTeX formatting to generate pdf versions
of reports (as opposed to figures), so if you want to generate pdf
reports, you’ll need to have some version of LaTeX installed on your
computer.

If you don’t have LaTeX installed, probably the easiest way for R users
to address this is by using the `tinytex` package. Installation and use
of `tinytex` is described [here](https://yihui.name/tinytex/).

### Bonus: Git and GitHub

As we go along, I’ll be saving my work using the
[git](https://git-scm.com/) version control system, and posting
materials to the course’s repository on [github](https://github.com/)
both so you’ll all be able to access everything after the course and so
you’ll be able to see web interactivity and sharing “live”. We won’t
discuss the mechanics of these tools much in the course itself due to
time constraints, but you may want to install git on your machine and
set up an account on github if you find the illustrated usages
interesting.

An Example Analysis
===================

While we’ll be working through some parts of a reproducible analysis
setup “live”, but we won’t be able to take our live analysis through all
the steps we might encounter with a real analysis. To balance this,
we’re including a link here to a more realistic analysis.

[Example Analysis on GitHub](https://github.com/kabagg/example_analysis)

This analysis surveys 4 datasets from the web:

-   [Potti et al data on
    figshare](https://ndownloader.figshare.com/files/10615624?private_link=66603862d770b4c73146),
    5.1 Mb
-   [NCI60 data from NCI
    DTP](https://wiki.nci.nih.gov/download/attachments/155845004/WEB_DATA_NOVARTIS_ALL.zip?version=1&modificationDate=1378406329000&api=v2&download=true),
    26.2 Mb
-   [GEO SOFT Dataset
    GSE349](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE349),
    4.7 Mb
-   [GEO SOFT Dataset
    GSE350](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE350),
    4.4 Mb

An Example Package
==================

We’ll also be assembling a few working R packages “live”, but, as with
the analyses mentioned above, we won’t be able to flesh our live package
out to any great extent. To balance this, we’re including a link to a
more realistic (but still basic) package.

[Example Package on GitHub](https://github.com/kabagg/examplePackage)

Further Resources
=================

Places to Learn More
--------------------

We can’t cover everything, so here are [some places to learn
more](Resources/resources.md).

Notes for Participants
----------------------

I’m sending some of the above around about a month before the course
itself to give people a heads-up. These notes are [online
here](Resources/notes_for_participants.md), or in [MS Word
here](Resources/notes_for_participants.docx).
