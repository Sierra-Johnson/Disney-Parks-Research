How I want to structure the project:


1) Data collection:
    Data from: Google's Big Query
    Collecting: tweets from Twitter

2) Data filtering:
    To start:
        Filter out filler words (the, and, or,etc.)


    Later version to implement:
        Use NLP model to determine if a tweet is positive/negative and the main context of the tweet
            Filter out tweets that are about other areas of the park (i.e. attractions, rides, food, etc.)





2a) Data model 
Spreadsheet of entries where each entry is a tweet
each row contains:
    AUTO_INCREMENT: tweetID (primary id)
    string: tweetContents
    float: tweetRating (-1 to 1)
        Note to self: this should be set to 0 initially, 
            calculated after dataset has been verified to look good
            write method to calculate once so it doesn't need to be redone because this will be time intensive
    []: keywords (new table)
        will be a list of the key words in the tweet
            i.e. character names, locations, etc.
            will referrence KEYWORDS table for the word, score

    enum location:
        1: Disneyland
        2: Disneyworld
        etc.
            Note to self: can get more specific if wanted later


another table named KEYWORDS:
    TODO this needs to be rethought
    foriegn key: tweetID 
    string: word (the actual word)
    float: score (-1 to 1 of how positive the word is)
        intialized to 0, LATER function to provide with score and update table





3) Data Processing:
    Questions to answer:
        What is the most common word(s) used to describe character interactions in each park?
            If x word is used most at park A, how much is it used at park B?



    (To add later)
        How "good"/"bad" are the mean of the tweets for a given park?
            A tweet is given a score between -1 to 1 on how positive the key words in the tweet are 
                i.e. if a tweet about Disneyland uses "incredible" 3 times and incredible is a .9 score, that is a very positive tweet
                        then average how positive/negative all the tweets for a given park are
