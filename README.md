library(tidyverse)

set.seed(123)

#Computing all the possible heights
heights=seq(145.5,180.5,0.1)
heights
#Forming the 10 000 heights received from each individual
Population_heights=sample(heights,10000,replace = TRUE)
Population_heights

#All the individual heights above and equal to 165 
Above_165 = Population_heights[Population_heights >= 165]
Above_165
#All the individual heights below 165
Below_165 = Population_heights[Population_heights < 165]
Below_165
#Checking if the number of heights correlate with the number of people
Population_number=length(Above_165) + length(Below_165)
Population_number

#data frame for the plot
df=data.frame(Population_heights)
#Forming my histogram and including red dotted line to show the height 165 cm
ggplot(df,aes(x=Population_heights))+
  geom_histogram(color="black",fill="blue")+
  geom_vline(xintercept = 160,linetype="dashed",color="red")
 labs(title = "Histogram of Population Heights", x = "Height (cm)") 
