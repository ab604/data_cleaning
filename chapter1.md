---
title       : Introducing R
description : Introduction to R for Southampton Data Carpentry
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:353ec4b851
## Looking at the data
The surveys data set includes continuing monthly rodent surveys. Each month rodents are trapped on all 24 experimental plots and information on each captured rodent is contained in this file. The data set should prove useful for **studying population dynamics and species interactions**.

The `surveys` dataset is loaded into the workspace, along with the package `dplyr`.
Have a look at the data and identify which of these variables were NOT recorded.

Try using `glimpse()` or `head()` to look at the structure of the data.

*** =instructions
- month
- week
- year
- species

*** =hint
Use `glimpse(surveys)` to look at the structure of the data.

# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer
*** =pre_exercise_code
```{r}
surveys <- read.csv("http://s3.amazonaws.com/assets.datacamp.com/production/course_2129/datasets/surveys.csv", stringsAsFactors = FALSE)
library(dplyr)
#glimpse(dat)
```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "That is not correct!"
msg_success <- "Exactly! There's no week variable in the dataset."
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:87071ce5bb
## Finding the survey duration

In the previous exercise, you saw a monthly rodent surveys dataset. In this exercise, we'll have another look at the dataset 

The monthly rodent surveys dataset, `surveys`, is again available in the workspace.

*** =instructions
- Check out the structure of `surveys`.
- Find the range of years over which the survey took place and assign it to `survey_timerange`.
- Then return the range to the console by calling the object you've assigned.

Variables in R data frames are called by using the name of the data frame followed by a dollar sign and the name of the variable. For example: `surveys$month` will return the values in the month column of the surveys dataset.

Objects are assigned using an arrow symbol `<-`, such that `survey_number <- 5` assigns the number five to an object called `survey_number`.

*** =hint
- Use `str()` for the first instruction.
- .
- .

*** =pre_exercise_code
```{r}
library(dplyr)
surveys <- read.csv("http://s3.amazonaws.com/assets.datacamp.com/production/course_2129/datasets/surveys.csv", stringsAsFactors = FALSE)
```

*** =sample_code
```{r}
# surveys is available in your workspace
# Check out the structure of surveys using glimpse()

# Find the range of years over which the survey took place and assign it to `survey_timerange`
# Assignment is done using the arrow  <-
# The variables can be called using the dollar sign $

# Show the range by calling the object you just created: survey_timerange

```

*** =solution
```{r}
# surveys is available in your workspace

# Check out the structure of surveys
glimpse(surveys)
# Find the range of years over which the survey took place and assign it to `survey_timerange`
survey_timerange <- range(surveys$year)
# Show the range by calling the object you just created: survey_timerange
survey_timerange
```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

#test_function("str", args = "object",
              #not_called_msg = "You didn't call `str()`!",
             # incorrect_msg = "You didn't call `str(object = ...)` with the correct argument, `object`.")

#test_object("good_movies")

#test_function("plot", args = "x")
#test_function("plot", args = "y")
#test_function("plot", args = "col")

#test_error()

success_msg("Good work!")
```
