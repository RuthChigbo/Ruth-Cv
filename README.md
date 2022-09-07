# Ruth-Cv
My Updated Cv


---
title: "Ruth Cv"
output: html_document
date: "2022-08-31"
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:

```{r cars}
summary(cars)
```

## Including Plots

You can also embed plots, for example:

```{r pressure, echo=FALSE}
plot(pressure)

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
```

docname: CV
output: vitae::Ruthcv
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = FALSE,
                      warning = FALSE,
                      message = FALSE)
require(xfun)
packages <- c('vitae'     # The CV's LaTeX Template
             ,'tibble'    # Data structure for tribbles
             ,'magrittr'  # The Pipe %>%
             ,'here'      # Relative File Paths
             ,'readr'     # Data Loading
             ,'glue'      # String Manipulation
            )
xfun::pkg_attach2(packages, message = FALSE)
source(file = here("r","data.r"))
```

# Employment

```{r EMPLOYMENT}
library(dplyr)
library(tidyr)
library(readr)
library(xfun)
View(xfun)
install.packages("vitae")
library(vitae)
library(glue)
library(here)
library(magrittr)
```


```{r EMPLOYMENT}
Work %>%
  detailed_entries(
    with = title,
    what = unit,
    why = detail,
    when = glue::glue("{startMonth} {startYear} --> {endMonth} {endYear}",.na = ""),
    where = where
  )
```

# Education

```{r EDUCATION}
edu %>%
  detailed_entries(
    with = inst,
    what = degree,
    why = detail,
    when = glue::glue("{startYear} --> {endYear}",.na = ""),
    where = where
  )
```

# Skills

```{r SKILLS}
skills %>%
  detailed_entries(
    with = area,
    what = skills
  )
```

# Honors

```{r HONORS}
honors %>%
  detailed_entries(
    with = area,
    what = accomplishment,
    why = detail,
    when = year,
    where = where
  )
```

# Projects

```{r PROJECTS}
projects %>%
  detailed_entries(
    with = area,
    what = accomplishment,
    why = detail,
    when = year,
    where = where
  )
```

# Works

```{r WORKS}
works %>%
  detailed_entries(
    with = area,
    what = accomplishment,
    why = detail,
    when = year,
    where = where
  )
```

\pagebreak

# Certifications

```{r CERTIFICATIONS}
certifications %>%
  detailed_entries(
    with = area,
    what = accomplishment,
    why = detail,
    when = year,
    where = where
  )
```

