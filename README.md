# Homework-1
GitHub Version Control for Homework 1 for Econometrics, Fall 2020
---
title: "Homework 1"
author: "Patrick Sinclair"
date: "9/9/2020"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

#### Question 1 - Team Members

1. Dorothy Gay
2. Monica Martinez-Raga
3. Patrick Sinclair


#### Question 3 - Dice Roll
**Part 1 - A Fair Die**

```{r fair die, echo=FALSE}
dice.roll <- sample(1:6, size = 20, replace = TRUE)
dice.roll
```

**Part 2 - Adjusted Dice**

Larger Sample Space - 10 Potential Outcomes

```{r large sample space, echo=FALSE}
dice.roll <- sample(1:10, size = 20, replace = TRUE)
dice.roll
```

Outcomes Not Replaced - 20 Potential Outcomes, 10 events

```{r no replacement, echo=FALSE}
dice.roll <- sample(1:20, size=10, replace=FALSE)
dice.roll
```
```{r}
# try to add Excel table of results
```
For each of the different simulated die rolls probability of a 6 occurring on one roll in each experiment is 0.1667, 0.1 and 0.0001 respectively. The event of a 6 occurred more frequently in each experiment than those probabilities would suggest. Of 200 rolls of a fair die, 6 appeared 36 times (0.18). The same number of rolls of a 10 sided die produced a 6 on 23 occasions (0.115). Using code to create a roll of a 20 sided die with the numbers not be replaced produced a 6 on 5 of the 100 rolls (0.05).  

Were more trials conducted in each experiment, the experimental probability of recording a 6 should approach the classical probability.

#### Question 4 - PUMS Data
**Snapshot of Age and Level of Education**
```{r, acs2017data, echo=FALSE}
load("acs2017_ny_data.RData")
acs2017_ny[1:10,1:7]
attach(acs2017_ny)
```
**Summary Statistics for the Dataset**
```{r, summary, echo=FALSE}
summary(acs2017_ny)
```
**Total Number of Observations in the Dataset**
```{r, observations, echo=FALSE}
print(NN_obs <- length(AGE))
```
**Summary Statistics on Age of Women in the Data**
```{r, echo=FALSE}
summary(AGE[female==1])
```
*Individually Coded Statistics*  
Mean
```{r, echo=FALSE}
mean(AGE[female==1])
```
Standard Deviation
```{r, echo=FALSE}
sd(AGE[female==1])
```
**Summary Statistics on Age of Men in the Data**
```{r, echo=FALSE}
summary(AGE[!female])
```
*Individually Coded Statistics*  
Mean
```{r, echo=FALSE}
mean(AGE[!female])
```
Standard Deviation
```{r, echo=FALSE}
sd(AGE[!female])
```
**Top Coding Issues**  
Average Age of Women, adjusted for topcoding
```{r, echo=FALSE}
mean(AGE[ (female==1) & (AGE<90)])
```
Average Age of Men, adjusted for topcoding
```{r, echo=FALSE}
mean (AGE[ (!female) & (AGE<90)])
```
After adjusting the topcoding for the ages of both women and men, we see a larger fall in the average age of women than that in men. The difference in average age also falls, by 0.3637 years. By lumping all the respondents above the age of 90 as "95", skewness is imposed upon the dataset and results in distorted mean values for age.

```{r}
# add information on education levels in Inwood
```

#### Question 5 - S&P 500
