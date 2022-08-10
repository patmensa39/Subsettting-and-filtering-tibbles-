# Subsettting-and-filtering-tibbles-
### Building and Printing tibbles 
library(tidyverse)
View(CO2)

## making a tibble 
co2_tibble <- as_tibble(CO2)
co2_tibble

### viewing the data

co2_tibble <- as_tibble(CO2) %>% print(n =20)

### viewing the entire data 
co2_tibble <- as_tibble(CO2) %>% print(n = Inf)

### creating your own tibble 

name <- c('Samuel', 'Joyce', 'Doris', 'Selorm', 'Patrick', 'Elorm')
birthyear <- c(1966, 1970, 1988, 1991, 1991, 2008)
Basic_school_attended <-c('Roman Catholic', 'Presby', 'Feden', 'Feden', 'Feden', 'Benoni') 
Occupation <- c('Farmer and Agro-Chemist', 'Trader', 'Disease Control Officer', 'Nurse',
                'Manager Operations', 'Student')
family <- tibble(name, birthyear, Basic_school_attended, Occupation)
family
view(family)

# Subetting tibbles 
### selecting one variable 
family$name
family$Basic_school_attended

# Selecting unique variables without duplicates 
unique(family$Basic_school_attended)

# Another way of subsetting (Operator)[] 
## with this, you can use the name of the variable or the position of the variable 
### selecting Occupation which is the 4th variable
family[['Occupation']]

family[[4]]


### Filtering 
family

family %>% filter(birthyear == 1991)
family %>% filter(Basic_school_attended == "Feden")

Feden_people <- family %>% filter(Basic_school_attended == "Feden")
Feden_people

##family born after 1990
family %>% filter(birthyear > 1990)

##family born on 1991
family %>% filter(birthyear == 1991)


##family born on 1991 OR went to feden
family %>% filter(birthyear == 1991 | Basic_school_attended == "Feden")

##family born on 1991 and went to feden
family %>% filter(birthyear == 1991 & Basic_school_attended == "Feden")
