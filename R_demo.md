# Why/How to Use R
## Reproducibility, Sourcing
With R, you can create a script tracing all of the actions done with data. 
With an excel sheet, it can be difficult or impossible to trace how data was manipulated from its source. 
If you can read an R script, you can see how and why certain choices were made. It makes finding and fixing mistakes simpler. 
## Getting into R with the Tidyverse

```R
library(tidyverse)

income_base_model %>%
    filter(year %in% c(2010, 2020, 2030, 2040),
           age_group != "0 to 15",
           model_type != "base"
           ) %>%
    group_by(year, model_type, age_group) %>% summarize(population = sum(population)) %>% 
    group_by(year, model_type) %>%
    mutate(percent = population / sum(population), age_group = as.integer(age_group)) %>% ungroup() %>% 
    mutate(year = as.character(year)) %>% 
    ggplot(aes(x = age_group, y = percent, color = year, group = paste0(year, model_type))) +
    geom_smooth(se = F, linewidth = 0.9) + 
    geom_point() +
    facet_grid(cols = vars(model_type)) + scale_color_viridis_d()
```

The easiest way to get into R is to use a series of packages called the `tidyverse`. 

# Why to Use Git/Github? 
## Version Control
Imagine Word's track changes, but for all files and multi-file projects. 
