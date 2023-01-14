# USpredictionRModel
 
Highlight of Code

```
setwd("/Users/zishuzhu/Desktop/problemset3")
sur_raw <- read_dta("ns20200625/ns20200625.dta")
sur_raw <- labelled::to_factor(sur_raw)
#select variables from sample data
new_sur <- 
  sur_raw %>% 
  select(vote_2020,
         vote_intention,
         registration,
         age,
         gender,
         state,
         household_income,
         race_ethnicity,
         employment
         )
new_sur$age<-as.numeric(new_sur$age)
#filter the valid voters
survey_dat<-new_sur %>% 
  filter(registration=="Registered"&
           vote_intention=="Yes, I will vote",
           (vote_2020=="Joe Biden"|vote_2020=="Donald Trump")
  )
```
