[Please note!!! a fully rendered version of the Project Workbook can be viewed at this link](https://nbviewer.jupyter.org/gist/eamonious/5f9780bc4c0f7ed8aa77c497d1cef699)


# Utilizing Social Media to alert about new disasters and their nature

### Data Science Problem:
During disasters, many people are in situations where first responders that need urgent  help. Ex: many people call 911 or manually scour through twitter data looking to filter through which situations need immediate assistance or not.

How can we utilize social media to design a tool that will identify disaster  events in real time using geo-location to bring attention to urgent disaster tweets?

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

Our primary takeaways in this project were as follows:

Despite initial setbacks, we were able to arrive at a satisfying and effective two-phase process for identifying critical disaster tweets out of the sea of all incoming tweets on social media. We were pleased with how well we were able to isolate potentially relevant tweets from a sea of test data. We also satisfying visualized what an interface for receiving geotagged tweets in real-time might look like, although we expect a more integrated and functional mapping software than Tableau might be necessary for real-world live implementation. Finally, we were able to demonstrate proof of concept on live-streaming capture of tweets. Given time to fully utilise the scope of the Sandy dataset, we could have made improvements on our existing model. But more to the point, given unrestricted access to the data of Twitter, let alone Facebook, Snapchat, Instagram (all of which FEMA would likely have in the hypothetical scenario where they would implement this process)... I feel we have demonstrated that with sufficient access, it would be possible to build out a very useful and accurate geo-feed of emergency response information in the area of an ongoing disaster.

All of this bodes well for future expansion of the project. Other directions we might go with more time include attempting to involve another social media platform, or locate a database of tweets from a disaster scenario other than a hurricane to try and diversify our filtering process. We also would like to try and improve predictive accuracy by use of Words2Vec, which is well equipped to locate similar types of tweets (e.g. critical tweets) without explicit labeling

Github directories of team:
[Alex Nguyen](https://github.com/aL1asWIN/) 
[Javier Martinez](https://github.com/eamonious)
[Eamon Fleming]()