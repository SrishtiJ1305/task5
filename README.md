# Introduction
This is my work from the Google Code-in task Use the simple Cranlogs API to obtain half-yearly R package downloads summaries in 2018.
Below you can see the code with comments.

# Prerequisites
- R
- RStudio
- jsonlite
- curl


# Code Description
The code below can be copied to R and executed as is.

```
# task5

library("animint2")
library("servr")
library("gistr")
#Sys.setenv(GITHUB_PAT = "fade8acef36b0fe3dfc7cbaf2107e6de88dee218")
gist_auth()
gists(per_page = 2)


data(WorldBank, package = "animint2")
tail(WorldBank)

WorldBank1975 <- subset(WorldBank, year==1975)
head(WorldBank1975)
scatter <- ggplot()+
  geom_point(
    mapping=aes(x=life.expectancy, y=fertility.rate, color=region),
    data=WorldBank1975)

scatter
animint(scatter)


animint2gist(animint(scatter))

```

# Authors 
- Srishti jain

# Screen recording

![](http://g.recordit.co/cmSlmVxzqO.gif)
