# Introduction

These are the materials for the "Reproducible reports" Brown Bag. At the bottom
of this document you will find some additional resources to learn more about R
Markdown. The `simple-report` folder contains the example that was used during
the talk. 

# R Markdown and reproducible reports

R Markdown is a "low-overhead way of writing reports which includes R code and
the code's automatically-generated output." In other words, it is a system that
allows you to write documents that intercalate code and the output of the code.
The documents themselves can also include rich text features like mathematical
notation, hyperlinks, or images in addition to some formatting.

Think for instance about some of the work on propensity modeling that we are
currently doing. For each individual in a sample we want to estimate their
probability of responding to the survey. It is a research problem in which we
want to try different data cleaning options, different modeling strategies, and
see how they perform. When we meet, we want to see where things stand, the code
that has been used for data cleaning, how the data looks like at each step, and
the intermediate output of some of the models together with some tests. But just
seeing the results is not very useful. I personally like to have comments to
interpret the output and to explain why some decisions have been taken.


We could run our code in whatever language we prefer, copy the output and paste
it into a Word document or an Excel sheet, and then add comments around. If the
statistician wants to see the code that generated the output, we could attach a
log file or maybe copy the significant portions into our final document. But
there is a strong inefficiency in this approach: if anything changes in the code
or in the data, we would need to do the process all over again. There is a
disconnect between the solution we use to run the analysis and produce the
statistical output and the file that documents and describes it.

This is where literate programming, reproducible reports and R Markdown in
particular come to help. They allow you to use a single document to include all
the information and also enough flexibility to make it look good for public
sharing. 

# A basic R Markdown report

There are three components: a header, the body, and chunks of code. 

The _header_ contains metainformation about the report, like the title or the
author but also some instructions about the type of output, extensions, ... It
is written in the YAML format: 

```
---
title: "This is my report"
author: "Gonzalo Rivero"
date: October 16
output:
  pdf_document
---
```

The _body_ of the document, which is written in the markdown language. We will
talk about the markdown format in a bit, but by now think of plain text.

_Chunks_ with the code. They are used to include the actual code that you will
be using. These chunks are delimited by three backticks. 

```
  ```{r}
  mean(c(1, 2, 3))
  ```
```

In the `simple-report/` folder we will see a more elaborated example and some of
the other options that R Markdown allows us. 

# Resources

1. The [official site](http://rmarkdown.rstudio.com/) of the packge contains a
   really good introduction that also discusses more advanced topics. It also
   includes an introduction to the `pandoc` dialect of Markdown.

2. More information about the `pandoc` engine for format conversion can be found
   [here](https://pandoc.org/getting-started.html).

3. An alternative to the R Markdown reports is [Jupyter](http://jupyter.org/). 
