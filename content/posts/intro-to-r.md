---
title: "Intro to R"
date: 2021-04-26T16:08:06-07:00
draft: false
---

In this article, we'll get you setup with academia's most popular data science programming language: R.

R is the successor to S, and a relative of the commercial project S+ (S-PLUS). It was created by Ross Ihaka and Robert Gentleman, and was first released in August of 1993. It is used to plot, graph, query, edit, and study data. R is an interpreted language, meaning that R code is executed on the spot, rather than compiled into a binary file that can be executed later. To use R, you can download it from the [R website](https://www.r-project.org), or install it via [Homebrew](https://k-explorer.github.io/posts/getting-started-with-homebrew) with `brew install r`.

At [The DS Dev](https://k-explorer.github.io/blog), we recommend downloading [RStudio](https://rstudio.com/products/rstudio/download/%23download), which is a free and extremely useful IDE for R, with many features. RStudio will be used for the examples in all of our R articles.

Once you've setup R (and you can check that this has been done by typing `R` in Terminal and seeing what happens), and installed, opened, and checked out RStudio (optional but **_highly_** recommended), it's time to start using R. 

R is a language with an _extremely_ large number of packages to assist in your data science workflow. The most important ones are…

1. The Tidyverse (`install.packages('tidyverse')`): a collection of packages to make R code neater and faster. Includes 
    - [**dplyr**](https://dplyr.tidyverse.org/), to query data frames, or **tibbles**
    - [**tibble**](https://tibble.tidyverse.org), a package to manipulate a neater type of data frame.
    - [**ggplot2**](https://ggplot2.tidyverse.org), a package to make elegant data visualizations, i.e. graphs and plots
    - [**tidyr**](https://tidyr.tidyverse.org), a package for tidying R code
    - [**readr**](https://readr.tidyverse.org), a package for importing data from all kinds of files
    - [**forcats**](https://forcats.tidyverse.org), to work with factors
    - [**purrr**](https://purrr.tidyverse.org), to enhance R's functional programming toolkit
    - [**stringr**](https://stringr.tidyverse.org), to assist with strings, however unimportant they may be
    
    Not included in the main package collection but equally useful are 
    - [**googledrive**](https://googledrive.tidyverse.org)(`install.packages('googledrive')`), an R interface to your Google Drive
    - [**googlesheets4**](https://googlesheets4.tidyverse.org)(`install.packages('googlesheets4')`), to turn your GSheets into Tibbles.
    
2. DBI (`install.packages('DBI')`), and ODBC (`install.packages('odbc')`): DBI is an R database interface, for accessing and manipulating SQL and NoSQL databases. As **drivers**, interfaces between applications (or programs), and databases, are necessary, R comes with the  `odbc` package, used for managing all databases using ODBC data sources on your system (see any ODBC setup tutorial, especially the one [here](https://db.rstudio.com/best-practices/drivers/), which focuses on R). Package drivers meant to target only one database include `RSQLite`, `RMariaDB`, and `RMySQL`. As RMySQL is discontinued, it is recommended that you use `RMariaDB`, as the two databases are so similar that the same driver can be used for both (see "What is SQL Anyway?" post's [database section](/blog/posts/what-is-sql-anyway)).

Once you've done all of the above steps, you're ready to start working with R. A recommended tutorial to continue learning from is _R for Data Science_, by Hadley Wickham (one of the developers of RStudio). R4DS is free online at [r4ds.had.co.nz](https://r4ds.had.co.nz).
    
