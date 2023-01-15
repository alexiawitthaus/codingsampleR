# Coding sample in R 

This code was developed as part of my work as a research assistant. 

The goal of this part of this code was to 

1. get the number of references in each article of a database and 
2. Get the DOIS of the articles that did not have an OpenAlexID. 

In order to do this, I used the OpenalexR package, and the oa_fetch function, that called the API. 


The primary issue encountered  is due to the size of the data frame, and  given that I needed to access the API more times than I was allowed to, the package gave me random Null values. This means that I would get articles listed as not having an OpenAlexID, when in reality they did. This was problematic, since it would invalidate all our results and wouldn't allow us to create the network properly. 

I solved this by creating an outer loop and looping several times over those articles that initially gave us an NA. As the size of the outer loop increases, the probability of a random error decreases. 
