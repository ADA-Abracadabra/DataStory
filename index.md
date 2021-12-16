# Studying social sentiments of people from different work fields over time using quotes

## Context
A quote is not just text, not just sentences. It is the process of using words to express an idea, thoughts, a message, an explanation and much more. If it is possible to just focus on those aspects, we must not forget that there is a mind behind a quote, a human being that lived, saw or reflected about a subject, a situation that may be its own.
Over the years, the humanity experienced many terrible events like wars, economic crisis or more recently pandemics but also peaceful and light hearted periods such as Christmas for example.

People change over time, or at least the way they feel, think and express themselves, and this is what will interest us today. By focusing on the background of the mind behind a quote, we want to study and see its sentiment in general or during a specific event. Is someone's expressed sentiment directly related to its occupation, what it is going through ? Those are questions we aim to answer, focusing more on the speaker than the words he or she used.

## Sentiment analysis
This project articulates around sentiment analysis. In order to observe any evolution, changes or to the contrary, a certain stability of the emotional state of the society, we will here work with quotes, from [Quotebank](https://github.com/epfl-dlab/Quotebank) and in order to give them a score, we will use the [VaderSentiment](https://github.com/cjhutto/vaderSentiment) as sentiment analysis tool, despite specifically attuned to sentiments expressed in social media, it turned out to be one of the best scoring model among the ones we tested.
[Add small exemple of sentiment analysis and what we do as preprocessing]
Our pipeline for this is really simple, we first process the quote and then apply the sentiment analyzer provided by Vader and focus on the compounding score (YET).
This allow us to get a score for each quote, which is the main metric we will use in order to study the sentiment, mental state in the next sections !

## Dates
Let's dive into the temporal aspect of our story and begin with a simple but important notion, the distribution of the quotes over time :

[Add plot]

Overall, we do not see any weird behavior over time in the numbers of quotes, expect in 2016 where sudden drops happen, which can come from the data used, and thus we will (sadly) not work with this year in the next chapters. 
Also, we note that the first and last years (2008 and 2020) are not fully covered over the data, which is not a problem by itself but may lack some precision about some events.
Now, what about the main aspect that interest us, which is the sentiment. In order to have a first touch about this, we observe the score of the quotes month by month over the years :

[Add plot]
[Add analysis]

This is a nice baseline before shifting our focus on the people behind the quotes, and more precisely, their occupations !

## Occupations
Here, let's begin by explaining briefly what we did in order to study the professions. Due to the huge number of occupations, we decided to group them depending on the "domain" they are related (medicine, military, etc...). To do this, we first used a clustering method to get a kind of pre-grouping and then, we do a kind of manual check by re-attributing a job to another cluster that we define to contain only one domain based on selected wordlist related to a certain type of work. 

More formally, the initial clustering helped us to group some of the occupations together but unfortunately, since no "ecology" or "economy" cluster seemed to stand out, we had to "help" the clustering a little bit by providing a wordlist that would then look, in all the clusters that didn't make sense, for the jobs and their description in order to reclassify them together.

Here is the histogram of the number of occurences of the occupations among all the speakers per cluster :
![Clusters Plot](img/plotcluster.jfif)

![Medical Plot](img/plotmedicalsentiment.jfif)

![Ecology Plot](img/plotecologysentiment.jfif)

![Military Plot](img/plotmilitarysentiment.jfif)


Add plot

## Is there a link between one's profession and their mental state (positivity, negativity) ?

## How does the sentiment of a speaker change over a given period of time ?

## Can we correlate the positivity changes of different speakers' professions such as medical workers, finance workers, and climate activists with multiple history events such as the COVID19 pandemic, the subprime crisis, or global warming ?

## Discussion

## Difficulties

## Conclusion
