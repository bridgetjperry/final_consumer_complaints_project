# final_consumer_complaints_project
Mini Project for April 19 in GW Reporting in the Digital Age course
---
title: "Consumer Complaints Final Project"
author: "Bridget Perry"
date: "5/5/2022"
output: html_document
---

```{r setup, include=FALSE}
library(flexdashboard)
library(tidyverse) #includes ggplot2
library(tigris)
library(janitor)
library(writexl)
library(scales)
library(lubridate)
library(ggplot2)
library(formattable)
library(gt)
library(DT)
library(tibble)

```


Table 1: Complaint Submission Medium and Response Time Table

```{r}

table(complaints$submitted_via, complaints$timely_response)


```

Table 2: Company Response to Customer and Response Time Table

```{r}

table(complaints$company_response_to_consumer, complaints$timely_response)


```

Visualization 1: Submission Medium Graph

```{r}

ggplot(complaints, aes(x = submitted_via, y = "")) + 
  geom_col(color = "#8ebcda", fill = "#9ebcda") +
  coord_flip() +
  labs(title = "Ways Complaints Were Submitted ", x = "Submission Medium", y = "  ")


```


Visualization 2: Response Time Graph

```{r}

ggplot(complaints, aes(x = timely_response, y = "")) +
  geom_col(fill = "blue") +
  labs(title = "Responsiveness to Complaints", x = "Was the Response Timely?", y = " ")
