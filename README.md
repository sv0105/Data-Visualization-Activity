# Data-Visualization-Activity
Data Visualization Activity
---
title: "Data Visualization Activity"
author: "Sree Veereshwar Kumar Vallem"
date: "6/27/2022"
output:
  html_document: default
  word_document: default
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
```{r libraries, include=FALSE, echo=FALSE}
    library(tidyverse)  
    library(dplyr)  
    library(knitr)  
    library(bslib)  
    library(ggplot2)
    library(forcats)
```

```{r NBAData, echo=FALSE}
NBAData <- read.csv("C://Users//Veere//Downloads//nba_elo.csv")
```

```{r 2022NBA, echo=FALSE}
LatestNBA <- filter(NBAData, season=="2022")
```

#Team wise Total Game Points against Team 2

```{r LatestNBA, echo=FALSE}
LatestNBA['TotalScore'] =  LatestNBA['score1'] + LatestNBA ['score2'] #This is overall total score of each NBA game in 2022
ggplot(data = LatestNBA) + 
  geom_point(mapping = aes(x = TotalScore, y = team2, color = team1))
```
#Season wise Total Game Points of every home team right from start of NBA

```{r OverallNBAData, echo=FALSE}
NBAData['TotalScore1'] =  NBAData['score1'] + NBAData ['score2'] #This is overall total score of each NBA game from 1947
ggplot(data = NBAData) + 
  geom_point(mapping = aes(x = TotalScore1, y = team1, color = season))
```
