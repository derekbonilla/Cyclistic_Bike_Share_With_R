# Cyclistic_Bike_Share_With_R
Google Data Analytics Capstone Project analyzed with R

### Goal

...

### About the data
...
Wandering around [Kaggle](https://www.kaggle.com/), I was looking for ideas on how to approach my SQL data cleaning project. I found the [CarPrice_Assignment](https://www.kaggle.com/goyalshalini93/car-data) dataset in another user’s notebook. It’s a great dataset to practice on because it contains inconsistencies that a data analyst would happen upon in a work project. 

### Real-world situation

You are a junior data analyst working in the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and visualizations.


## Prerequisite

Install the required packages.

```{r}
install.packages("tidyverse")
install.packages("lubridate")
install.packages("ggplot2")
```

Once the packages are installed, it can be loaded by running the `library()` function.

```{r}
library("tidyverse") #helps to wrangle the data
library("lubridate") #easier to work with date-times
library("ggplot2") #helps visualize data
```

Additionally, use the `setwd()` function to change/set the current working directory to simplify calls to data.

```{r}
setwd("~/Documents/Cyclistic Trip Data")
```

## Step 1: Collect Data

At this point I want to upload the datasets that is going to be used in this analysis.

```{r}
M1_2021 <- read_csv("202101-divvy-tripdata.csv")
M2_2021 <- read_csv("202102-divvy-tripdata.csv")
M3_2021 <- read_csv("202103-divvy-tripdata.csv")
M4_2021 <- read_csv("202104-divvy-tripdata.csv")
M5_2021 <- read_csv("202105-divvy-tripdata.csv")
M6_2021 <- read_csv("202106-divvy-tripdata.csv")
M7_2021 <- read_csv("202107-divvy-tripdata.csv")
M8_2021 <- read_csv("202108-divvy-tripdata.csv")
M9_2021 <- read_csv("202109-divvy-tripdata.csv")
M10_2021 <- read_csv("202110-divvy-tripdata.csv")
M11_2021 <- read_csv("202111-divvy-tripdata.csv")
M12_2021 <- read_csv("202112-divvy-tripdata.csv")
```

## Step 2: Wrangle Data And Cominbe Into A Single File

Compare column names, using the `colnames()` function, of each of the files. They DO need to match perfectly before using the command to join them into one file.  

``` {r}
colnames(M1_2021)
colnames(M2_2021)
colnames(M3_2021)
colnames(M4_2021)
```

Use the `str()` funcition to inspect the internal structure and get a summary of the columns. Using this function we inspect and look for disparities. Again, These DO need to match before joining the files into one big data frame.

``` {r}
str(M1_2021)
str(M2_2021)
str(M3_2021)
str(M4_2021)
```

Stack all indvidual month's data frames into one big data frame. 

```{r}
all_trips <- bind_rows(M1_2021,M2_2021,M3_2021,M4_2021,M5_2021,M6_2021,M7_2021,M8_2021,M9_2021,M10_2021,M11_2021,M12_2021)
```
