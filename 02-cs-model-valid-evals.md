# Model validation for course evals
Student Name  
October 24, 2017  



## Setup

### Load packages


```r
library(tidyverse)
library(broom)
```

### Load data and calculate `bty_avg`


```r
# Load data
evals <- read_csv("data/evals-mod.csv")

# Calculate bty_avg
evals <- evals %>%
  rowwise() %>%
  mutate(bty_avg = mean(c(bty_f1lower, bty_f1upper, bty_f2upper, 
                          bty_m1lower, bty_m1upper, bty_m2upper))) %>%
  ungroup()
```

## Tasks from class

...
