# Sentiment Analysis in Song Lyrics Through Time
## Objective
To examine how sentiment in popular music lyrics changes with time. Sentiment can be categorized a number of ways but at a minimum will contain negative,neutral,positive labels. Categorization will depend on the chosen model. 

### Sub-topics
Sub-topic unique word count
Sub-topic song length
Within genre trends
Popularity of genres and their lifecycles


## Data Sources:
- Popular Songs:
    - Measuring popularity can be ambigious and but one commonly held source (at least in N. America) is the Billboard Hop 100. Weekly measure of Top 100 songs in America.
    - [Billboard Hot 100](https://data.world/kcmillersean/billboard-hot-100-1958-2017)
    - [Billboard Hot 100 API](https://github.com/guoguo12/billboard-charts)
- Song Lyrics 
    - there are several sources for song lyrics
    - https://github.com/elmoiv/azapi 
    - https://docs.genius.com/#/getting-started-h1 
    - https://www.lyrics.com/lyrics_api.php (100 queries a day)
    - 

## Process
1. source data
2. join lyric to populatarity measure
3. Baseline in NLTK
4. Baseline in Hugging Face
5. Investigate
6. Scale Up
7. Investigate
8. Contrast
9. Develop Dashboard(s)

## Background:

### Billboard Hot 100
Some background on how this is measured. The Hot 100 is ranked based on by radio airplay audience impressions as measured by the Nielsen BDS, sales data complilded by Neilsen Soundscan (digital and retail sales), as well streaming activity provided by online music sources. The weights applied by billboard are not know (ip) but it is know that their aggreation of data has changed with societal change (death of records sales and the rise of streaming).

### Sentiment Models
 


## Questions
- Do rises in other societial issues such as metal health, suicide, climate change, war make it's way into popular music. Can you see their prevalance in lyrics reflect increasing rates in the population?
- should I bother trying to train a sentiment model or just use an existing one? Could take the twitter datatset and build a model from that and then apply it to song lyrics. Seems like work for the sake of it though. Will use transfer learning.
- Can experiement with differnet sentiment models. Interesting to get more nuanced sentiment beyond, positive, negative, neutral.


## References
- [sentiment analysis tutorial](https://www.youtube.com/watch?v=QpzMWQvxXWk)


### Sub-topic Correlation of Sentiment in Song Lyrics of popular music with sentiment in media
This is potentially a can of worms. For estabishing relationships between popular music and what is happening in the world we would need to contrast what is happening within the demographics that define popular music. Which is likely folks aged 14-35 and with the media that those people consume. Which is not necessarilly going to be the media source you have access to. What we could do instead is look at periods of economic decline versus those of prosperity and see if there is a corressponding shift as these effect the general population.