In August 2016, NFL player Colin Kaepernick sparked a national controversy when he refused to stand during the national anthem. Kaepernick and other players who have since joined him say that they are protesting racial injustice in the United States, but some view the protest as disrespectful to the flag or the Armed Services.

This topic is very polarizing, so I suspected that people's natural language descriptions of the protests would separate into distinct topics.

So for my fourth project at Metis, I examined tweets tweeted during the 2018 NFL preseason, a time in which this debate seems to be annually reignited, and I used natural language processing algorithms to see if I could detect structure in people’s response to this polarizing issue.

I used TweePy to create a live streamer of tweets containing target words "national anthem" and "nfl" and I used Mongo DB to store the tweets. I then used python and SciKitLearn to process the data and model topics.   

The preprocessing steps that I took were to remove punctuation, links, user mentions, and numbers, and to put all tokens into lowercase. I used both latent dirichelet allocation and non-negative matrix factorization to model topics but NMF yielded more coherent topics so I am going to focus on those results.

In this repo, you can see the results from the one iteration of the non-negative matrix factorization. My code returns the top 7 topics with 7 key words each and you might notice that some of these topics map onto intuitive human concepts more so than others.

So topic 1 seems to be something political. And topic 2 seems to be some sort of condemnation of the protests suggesting that players shouldn’t be re-signed if they kneel. Topics 3 and 6 don’t seem to make a ton of intuitive sense and then topic 7 seems to be some sort of condemnation of the protests.

But I want to draw your attention back to topic 1 for a moment. As I mentioned, I played around with the hyperparameters a lot, including the number of top words for each topic. 7 top words seemed to result in the most coherent topics, but when I examined the top 8 words, the 8th word in the first topic, the "political" one as I am calling it, the last word in the topic was ted. Why was Ted Cruz coming up in a discussion about the NFL and the national anthem? I thought this was a bit strange so next I decided to visualize the data to see if that would help.

You can see a word cloud representation of my twitter data so more frequent words are shown as larger and what you can see is that ted cruz is indeed being heavily mentioned in tweets relating to the NFL and the national anthem but so is his opponent in the current senate race, Beto O’Rouke. I did a quick google search to see why this might be the case and I quickly discovered a video of Beto O’Rouke at a campaign event that was going viral at the time.

There were also some steps that I wanted to take on in this project that I didn’t get to.

For example, in the context of highly polarizing issues like gun control, same-sex marriage, and climate control it has been shown that the presence of moral emotional words in a tweet increases its likelihood of being retweeted. I would think that the same would apply to tweets about the national anthem but because I set up a live streamer in an attempt to capture the on-going debate about this issue in the 2018 NFL preseason, I didn’t have information about retweets and so couldn’t directly test this issue.

Additionally, I would have loved to examine changes over time. Meaning, have attitudes about this issue changed from 2016 to 2017 to 2018? But again, looking at changes over time was not possible using a live scrapper so I may very well go back and scrape tweets from 2016 to 2018 to test for changes over time and whether the presence of moral emotional words increases the likelihood of a tweet being retweeted.

In summary, using an NMF approach, I was able to do a pretty good job in modeling topics in tweets containing the nfl and national anthem. Some of these topics mapped on pretty well to human intuitive concepts but for others the mapping was less clear. But NMF did pull out one particularly relevant topic and this had to do with a senate race in Texas and a video that was going viral at the time depicting one of the candidates weighing in on this highly polarizing issue.
