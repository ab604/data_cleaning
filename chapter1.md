---
title       : Introducing R
description : Introduction to R for Southampton Data Carpentry
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:353ec4b851
## Looking at the data
The surveys data set includes continuing monthly rodent surveys. Each month rodents are trapped on all 24 experimental plots and information on each captured rodent is contained in this file. The data set should prove useful for **studying population dynamics and species interactions**.

The `surveys` dataset is loaded into the workspace.
Have a look at the data and identify which of these variables were NOT recorded.

Try using `glimpse()` or `head()` to look at the structure of the data.

*** =instructions
- month
- week
- year
- species

*** =hint
Use `glimpse(surveys)` to look at the structure of the data.

*** =pre_exercise_code
```{r}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer
library(readr)
library(dplyr)
surveys <- read_csv("surveys.csv")
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
## More movies

In the previous exercise, you saw a monthly rodent surveys dataset. In this exercise, we'll have another look at the dataset 

The monthly rodent surveys dataset, `surveys`, is again available in the workspace.

*** =instructions
- Check out the structure of `surveys`.
- Find the range of years over which the survey took place and assign it to `survey_timerange`.
- Use `plot()` to  plot `good_movies$Run` on the x-axis, `good_movies$Rating` on the y-axis and set `col` to `good_movies$Genre`.

*** =hint
- Use `str()` for the first instruction.
- For the second instruction, you should use `...[movie_selection$Rating >= 5, ]`.
- For the plot, use `plot(x = ..., y = ..., col = ...)`.

*** =pre_exercise_code
```{r}
# You can also prepare your dataset in a specific way in the pre exercise code

library(readr)
library(dplyr)
surveys <- read_csv("surveys.csv")
```

*** =sample_code
```{r}
# surveys is available in your workspace

# Check out the structure of surveys

# Find the range of years over which the survey took place and assign it to `survey_timerange`

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

test_function("str", args = "object",
              not_called_msg = "You didn't call `str()`!",
              incorrect_msg = "You didn't call `str(object = ...)` with the correct argument, `object`.")

test_object("good_movies")

test_function("plot", args = "x")
test_function("plot", args = "y")
test_function("plot", args = "col")

test_error()

success_msg("Good work!")
```
