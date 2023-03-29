# Sentiment Analysis on Popular Song Lyrics

## Introduction 
The purpose of this project was to investigate the change in the sentiment of popular music lyrics over the last 60 years. The measure of popularity in this case is the Billboard Top 100, which has been running since 1958. The Billboard Top 100 charts the 100 most "popular songs" in the US each week. How popularity is measured has changed with how we consume music but today is an arregation of record sales, both digital and physical, as well as streams and radio play. The specifics of the aggregation is closely guarded by Billboard.

The topic was choosen for personal development in the area of natural language processing as well as personal interest. Popular music by virtue of being popular, is always a sign of the times and I was curious to see, in an admittledly blunt way if lyrical sentiment did show any clear trend. It also presents a well suited application of NLP as it allows for a consistency that would be difficult to create with human observations. 

It goes without saying that lyrical sentiment is just one aspect of the overall sentiment of a song, but it is a start...

## Data Sources
The following APIs were used:
- Popular Songs:
    - [Billboard Top 100](https://raw.githubusercontent.com/HipsterVizNinja/random-data/main/Music/hot-100/Hot%20100.csv)
- Song Lyrics:
    - [Lyric Genius](https://lyricsgenius.readthedocs.io/en/master/) 
- Spotify Artist ID and Genre Data:
    - [Spotipy](https://spotipy.readthedocs.io/en/2.22.1/)

## Data Stack
- Python
- Packages:
    - Pandas, Seaborn, Matplotlib, Tensor Flow, Hugging Face
- Tableau

## EDA Insights
There's no need to highlight everything from the EDA process but the following are interesting points when considering how popular music has changed throughout the years and the advent of digital streaming and downloading of music.
What we observe is that there was an intital peak in the late 60s early 70s in the variety of music we were listening to, both in terms of the number of unique songs and artists. That was in gradual decline until the late 1990s and early 2000s, when the advent of home computer use and the digital consumption of music started to emerge. The late 90s is also known as ther period when record sales hit their peak. What is beautiful about this is that we can clearly how having access to digital music changed how and what we could listen to. Once the pay wall went down the floodgates opened. A varied diet is a healthy diet.

![Alt text](junk/Artists%20per%20year.png) ![Alt text](junk/Unique%20Song%20Count.png)

## Results
With the Twitter Sentiment Roberta model we see that there is a gradual increase in negative from 1958-2022. Average increase of 3.3% in negativive sentiment with each passing decade. 

![Alt text](junk/Moving%20AVG%20Pos%20and%20Neg.png)

| Decade | 2 Sample Z Test (P) | Reject null? |
| :----: | :-----------------: | :----------: |
|60 vs 70| 0.007|Yes|
|70 vs 80| 0.09|No|
|80 vs 90| 0.03|Yes|
|90 vs 00| 0.15|No|
|00 vs 10| 0.51|No|
|10 vs 20| 6e-11|Yes|


The obvious next challange is understanding "How" this change has come about and that is a much more difficult question to answer. It doesn't take a much imagination to come up with some probably hypothesis'; our tolerance to explicit content has changed or the emergence and passing of genres (nu-metal, hip-hop ect.).
I attempted to answer the question with looking at genres of music and how their prevelence in popular music has changed or how the sentiment within genres has changed. 

The issue here is that genre is far more nuanced than I initially thought. When genre data was layered in from the Spotify API it showed that there were approximately 600 genres listed and no meaningful trend was going to be visible without further aggregation. As such this has been pushed out to follow up work for now.

## Follow Up Work

1. Lyrics API:
    - There are multiple free to use lyric APIs available. I chose lyric genius but as you might expect with some free services the quality is not comprehensive. There were 30444 unique songs featured in the Billboard dataset, of which it was possible to retrieve around 85% of the lyrics. However, on closer inspection the API occaisionally provides the entire text of a novel instead on lyrics. It is particularly fond of James Joyce for some bizarre reason. There may be some error in how I queried the API but I couldn't find the bug at the time. So this reduced the size of the data set further.
2. Transfer learning using the ROBERTA model:
    - There is room for optimisation here. For sentiment analysis I used a Twitter ROBERTA Base Sentiment from Hugging Face. At the time when I was completing this project I was pretty new to Deep Learning. When it came to sentiment classsifcation the ROBERTA model struggled to analyse all 26K songs. The root cause of the faults could not be found and requires a deeper dive into the construction of the Twitter model. In the end it was possible to retrieve the sentiment of only 17K songs.
3. Consolidation of Genres:
    - To gain a better understanding of why we see a gradual increase in negative sentiment in music one hypothess is to look at the trends at the genre level. Spotify genre data was pulled and joined to the popular music dataset but the difficulty is the range of genres. A single artist can be labelled with up to 15 genres and there were a approximately 600 unique genres available. With this it becomes difficult to pull out isolated trends so it was decided to agrregate genres under broader labels such as "hip-hop", "rap", "blues" ect. This continues to be a work in progress.
