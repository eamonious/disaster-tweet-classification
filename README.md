[PLEASE NOTE: A fully-rendered version of the project workbook can be viewed here](https://nbviewer.jupyter.org/gist/eamonious/1dd3226577714b84db4a7e0387a64baf)


# Leveraging Social Media To Alert Emergency Response Personnel During Disasters

### Data Science Problem:
In this project we sought to make initial steps toward designing and implementing a web-tool or an app for rapid alert and notification about a disastrous event, in close to real time. The tool ideally would alert about the event, similar, for example, to earthquake or tsunami warnings that appear on Google's home page immediately after a major disaster. While traditional methods for alerting on such events rely on official information derived from official sources (e.g. USGS), this tool will utilize social media activity to identify these events and alert when an event first occurs.

The question we look at primarily here is, given a sea of text content from social media platforms, how do you identify what is relevant information for emergency response personnel? And what sort of implementation would be valuable?


##  Readme information
### Datasets/Resources used:
- [Figure Eight - Disasters on social media dataset](https://d1p17r2m4rzlbo.cloudfront.net/wp-content/uploads/2016/03/socialmedia-disaster-tweets-DFE.csv)
- Contributors looked at over 10,000 tweets culled with a variety of searches like “ablaze”, “quarantine”, and “pandemonium”, then noted whether the tweet referred to a disaster event (as opposed to a joke with the word or a movie review or something non-disastrous).

- [CrisisLex: SandyHurricaneGeoT1 Geo-Located tweets from the 2012 Sandy Hurricane](https://crisislex.org/data-collections.html#SandyHurricaneGeoT1)
- Contents: tweet ids for 6,556,328 tweets, representing all tweets from October 22nd, 2012 —the day Sandy formed— until November 2nd, 2012 — the day that it dissipated.
- Sampling method: tweets were geotagged and located in Washington DC or one of 13 US states affected by Sandy: Connecticut, Delaware, Massachusetts, Maryland, New Jersey, New York, North Carolina, Ohio, Pennsylvania, Rhode Island, South Carolina, Virginia,West Virginia. This filter was based on a set of bounding boxes that covered the desired area, which also covered small parts of adjacent states.
- Labels: no labels. The corpus contains tweets both relevant and irrelevant to Hurricane Sandy (no content based filter was applied).
- Data format: comma-separated values (.csv) files containing the tweet ID, the time stamp of the tweet, a field indicating whether the tweet contains word "sandy".

- [CrisisLex lexicon](https://crisislex.org/crisis-lexicon.html)
- Our recommended lexicon for Twitter querying contains an automatically-generated and human-curated list of terms found to be frequently related to disasters. This was done by studying terms frequency distribution in the CrisisLexT6 collection; looking for terms that were discriminative and frequent in crisis tweets, and common across various crises; and performing a crowdsourced curation step to curate the list. Details are given in [Olteanu et al. 2014].

This lexicon strikes a balance between precision (collecting mostly tweets related to crises) and recall (collecting most of the crisis-related tweets) when used to collect Twitter data. By introducing variations in the process that builds a lexicon, we can achieve different trade-offs between precision and recall, e.g. to emphasize one at the expense of the other. A number of other variants of this lexicon are included.

### About the API
- Using [Twitter API](https://developer.twitter.com/en/apply-for-access) keys to pull tweets using tweet ids. Need to apply for a key in order to use Twitter's API to obtain consumer key, consumer secret key, oauth token, oath secret.

- Each of us created Twitter Development accounts and submitted applications for the project.  by applying for more api keys we were able to pull tweets in tandem to allow for higher volume data collection.

[Twython](https://twython.readthedocs.io/en/latest/) (Python wrapper for the Twitter API)
Designed a Tweet Pull Function and While Loop to run through a list of tweet ids in chunks of 900 repeatedly.  Ran in tandem with multiple app keys

Training data:  Pulled all 180000 tweets from the peak disaster period (1 hour before landfall in NJ/NY to 2 hours after) in hopes  of getting a maximum number of critical tweets to train with

Test data:  Pulled a random sample of ~40000 of the two million tweets after that point to test on.

### Executive Summary:

Our primary takeaways in this project thus far are as follows:

Despite initial setbacks, we were able to arrive at a satisfying and effective two-phase process for identifying critical disaster tweets out of the sea of all incoming tweets on social media. We were pleased with how well we were able to isolate potentially relevant tweets from a sea of test data. We also successfully visualized what an interface for receiving geotagged tweets in real-time might look like, although we expect a more integrated and multi-functional mapping software than Tableau might be necessary for real-world implementation. Finally, we were able to demonstrate proof-of-concept on live-streaming capture of tweets. 

Given unrestricted access to the data available via Twitter, let alone Facebook, Snapchat, Instagram (all of which FEMA or a similar organization would likely have in the hypothetical scenario where they would implement this process), I feel we have demonstrated that it would be absolutely possible to build out a very useful and accurate geo-feed of emergency response information in the area of an ongoing disaster.

All of this bodes well for future expansion of the project. Other directions we might go with more time include attempting to involve another social media platform, or locate a database of tweets from a disaster scenario other than a hurricane to try and diversify our filtering process. We also would like to try and improve predictive accuracy by use of Words2Vec, which is well equipped to locate similar types of tweets (e.g. critical tweets) without explicit labeling.

Github directories of team:
[Alex Nguyen](https://github.com/aL1asWIN/) 
[Javier Martinez](https://github.com/eamonious)
[Eamon Fleming]()