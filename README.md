# hopkinsdown

This package provides a template for writing a thesis at Johns Hopkins University using **rmarkdown** and **bookdown**. This project is based on Luke Zappia's [unimelbdown](https://github.com/lazappi/unimelbdown) which is in turn based on Chester 
Ismay's [thesisdown](https://github.com/ismayc/thesisdown).

Currently none of the output formats are compliant or work correctly.

The Latex template is adapted from John "Randy" Clayton's
[JHU Dissertation LaTeX mwe](https://github.com/jrclayton/jhu-dissertation-mwe).

## Installation

You can install **hopkinsdown** from GitHub using **devtools**:

```r
# install.packages("devtools")
devtools::install_github("Zaxim/hopkinsdown")
```

You will also need to install LaTeX. The easiest way to do that is using the
**tinytex** package:

```r
install.packages(c('tinytex', 'rmarkdown'))
tinytex::install_tinytex()
# after restarting RStudio, confirm that you have LaTeX with 
tinytex:::is_tinytex()
```

## Using hopkinsdown

To use **hopkinsdown** from RStudio:

1) Use the **New R Markdown** dialog to select **Hopkinsdown Thesis** and enter 
   `index` as the name:

    ![New R Markdown](thesis_rmd.png)

    Note that this will currently only **Knit** if you name the directory `index`
    at this step.

> If you are not using RStudio run this line to create a template:
> `rmarkdown::draft('index.Rmd', template = 'hopkinsdown', package = 'hopkinsdown', create_dir = TRUE)`

2) Edit the YAML header in the `index.Rmd` file to set option.

3) Edit the individual R Markdown files to change the content. To reorder or
   remove sections edit `_bookdown.yml`.

4) Press **Knit** on the `index.Rmd` file to get your thesis in the desired
   format.

> Use the following line if not in RStudio
> `bookdown::render_book('index.Rmd', hopkinsdown::thesis_pdf(latex_engine = 'xelatex'))`
