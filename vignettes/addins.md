---
title: "Rstudio Addins"
author: David Kane
output: rmarkdown::html_vignette
vignette: >
  %\VignetteEngine{knitr::knitr}
  %\VignetteIndexEntry{Rstudio Addins}
  %\VignetteEncoding{UTF-8}
---



## Overview

We have provided four additions to the RStudio Addins menu: "Tutorial Code Exercise", "Tutorial Written Exercise (with Answer)", "Tutorial Written Exercise (no Answer)" and "Format Tutorial Chunk Labels." The first three each insert the skeleton for the next exercise in a tutorial, featuring all the key component parts. We even takes a guess at the correct exercise number.  The "Format Tutorial Chunk Labels" addin is the most useful. Always run it before testing your tutorial. It ensures that all the exercises are sequentially numbered and that all the code chunk names are correct and unique.

You can find the addins in the "Addins" tab on the top Rstudio toolbar. Make sure that your cursor is located at the point in your Rmd at which you want to insert the new exercise. 

<img src="images/code-exercise-1.png" alt="plot of chunk unnamed-chunk-1" width="95%" height="95%" />

### Tutorial Code Exercise

Create a new code exercise skeleton with an exercise title and with auto-generated code chunk ids.



````default
### Exercise 7

```{r exercises-7, exercise = TRUE}

```

<button onclick = "transfer_code(this)">Copy previous code</button>

```{r exercises-7-hint, eval = FALSE}

```

###
````

See [our advice](https://ppbds.github.io/tutorial.helpers/articles/instructions.html#exercises) about writing good tutorial code exercises. 

<!-- DK: Add some details, a precise of the advice, explaining the structure we provide. -->



### Tutorial Written Exercise (with and without answers)

Both create similar exercise structures with auto-generated chunk id and exercise title. The difference is that the `question_text()` options are filled in differently.

Written Exercise with Answer:


````default
### Exercise 8

```{r exercises-8}
question_text(NULL,
	message = "Place correct answer here.",
	answer(NULL, correct = TRUE),
	allow_retry = FALSE,
	incorrect = NULL,
	rows = 6)
```

###
````

Written Exercise without Answer:


````default
### Exercise 9

```{r exercises-9}
question_text(NULL,
	answer(NULL, correct = TRUE),
	allow_retry = TRUE,
	try_again_button = "Edit Answer",
	incorrect = NULL,
	rows = 3)
```

###
````

<!-- DK: More details on why/how of these questions. -->


### Format Tutorial Chunk Labels

<!-- DK: Fix this section. Maybe don't use images? -->

An addin that formats all the code chunk labels in the current Rmd.

It formats the labels of the code and written exercise code chunks as well as the hints.

Limitations:

- It doesn't work well with the \`r\` that shows the entire code chunk

- The code chunk labels (derived from your section titles) have a hard cutoff at 20 characters. So please make sure that your Section Titles are different somewhere in the first 20 characters (including spaces).




