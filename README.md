# Analysis-of-SARS-CoV-2-lineages-in-Wastewater-samples-
Wastewater surveillance can be effectively used for detecting early signs of a disease outbreak and aids in developing strategies for control and prevention of an epidemic.


#########Load Package for for analysis######
library(ggplot2)
library(gridExtra)
library(ggplot2)
library(dplyr)
library(scales)
library(ggthemes)
library(tidyverse)
data <- read.csv("filename.csv")
data$Abundance <- data$Abundance * 100

# Assuming you have a data frame named 'data' with the specified columns

# Create the stacked bar plot
p <- ggplot(data, aes(x = Date, y = Abundance, fill = Lineage)) +
  geom_bar(stat = "identity") +
  labs(x = "Names", y = "Abundance (%)") +
  ggtitle("Lineage Abundance") +
  scale_y_continuous(limits = c(0, 100)) +  # Set y-axis limits to 0-100%
  theme(axis.text.x = element_text(angle = 45, hjust = 1),
        legend.position = "bottom") +
  guides(fill = guide_legend(title = "Lineage"))

# Show the plot
print(p)


# Convert Date column to a Date format
data$Date <- as.Date(data$Date, format = "%d-%b-%y")
library(ggplot2)
library(hrbrthemes)
library(dplyr)
library(tidyr)
library(viridis)

ggplot(data=data, aes(x=Date, group=Lineage, fill=Lineage)) +
  geom_density(adjust=0.5, position="fill", n = 1000) +
  theme_ipsum()

