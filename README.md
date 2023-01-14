# Joe Biden With a Huge Advantage Against Donald Trump in 2020

United States Presidential Election :pencil2::pencil2:
 
:star_struck: I build a model with the post-stratification to estimate the proportion of voters in favor of voting for Donald
Trump. Post-stratification is a way to ‘re-weight’ so that the weighted totals within different cells equal the
population totals. Our sample data was post-stratified on age, gender, employment status, state, household
income, and race. The weight of the known population in the census data was also post-stratified by these
variables.
 
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
