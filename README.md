# Interactive-Map

---

Author: "Jane Chen"

Date: "29/04/2017"


This page includes an interactive map. This is for the Coursera “Developing Data Product” Week 2 Peer-Review Assessment. 

```{r, echo = FALSE, fig.width = 10}
library(leaflet)
library(datasets); data(state)
statedata <- cbind(state.name, state.abb, state.center, data.frame(state.x77))
income_map <- data.frame(lat = state.center$y, 
                         lng = state.center$x) %>% 
    leaflet() %>% 
    addTiles() %>% 
    addMarkers(popup = paste(statedata$state.name, statedata$state.abb, "<br>", 
                             "Income per Captica", statedata$Income, "<br>", 
                             "High-School Graduation Rate", statedata$HS.Grad))
income_map
```
