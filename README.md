# Using Social Media Data to Understand the Impact of Promotional Information on Laypeople’s Discussions: A Case Study of Lynch Syndrome

This is the data repository for our Twitter paper published in JMIR, [Using Social Media Data to Understand the Impact of Promotional Information on Laypeople’s Discussions: A Case Study of Lynch Syndrome](https://www.jmir.org/2017/12/e414).
 
# Citation
* Please cite this article, if you use the data for your own studies
   * *Bian J, Zhao Y, Salloum RG, Guo Y, Wang M, Prosperi M, Zhang H, Du X, Ramirez-Diaz LJ, He Z, Sun Y. [Using Social Media Data to Understand the Impact of Promotional Information on Laypeople’s Discussions: A Case Study of Lynch Syndrome](https://www.jmir.org/2017/12/e414). J Med Internet Res 2017;19(12):e414. DOI: 10.2196/jmir.9266. PMID: 29237586*

> **Abstract:** 
Background: Social media is being used by various stakeholders among pharmaceutical companies, government agencies, health care organizations, professionals, and news media as a way of engaging audiences to raise disease awareness and ultimately to improve public health. Nevertheless, it is unclear what effects this health information has on laypeople.

Objective: This study aimed to provide a detailed examination of how promotional health information related to Lynch syndrome impacts laypeople’s discussions on a social media platform (Twitter) in terms of topic awareness and attitudes.

Methods: We used topic modeling and sentiment analysis techniques on Lynch syndrome–related tweets to answer the following research questions (RQs): (1) what are the most discussed topics in Lynch syndrome–related tweets?; (2) how promotional Lynch syndrome–related information on Twitter affects laypeople’s discussions?; and (3) what impact do the Lynch syndrome awareness activities in the Colon Cancer Awareness Month and Lynch Syndrome Awareness Day have on laypeople’s discussions and their attitudes? In particular, we used a set of keywords to collect Lynch syndrome–related tweets from October 26, 2016 to August 11, 2017 (289 days) through the Twitter public search application programming interface (API). We experimented with two different classification methods to categorize tweets into the following three classes: (1) irrelevant, (2) promotional health information, and (3) laypeople’s discussions. We applied a topic modeling method to discover the themes in these Lynch syndrome–related tweets and conducted sentiment analysis on each layperson’s tweet to gauge the writer’s attitude (ie, positive, negative, and neutral) toward Lynch syndrome. The topic modeling and sentiment analysis results were elaborated to answer the three RQs.

Results: Of all tweets (N=16,667), 87.38% (14,564/16,667) were related to Lynch syndrome. Of the Lynch syndrome–related tweets, 81.43% (11,860/14,564) were classified as promotional and 18.57% (2704/14,564) were classified as laypeople’s discussions. The most discussed themes were treatment (n=4080) and genetic testing (n=3073). We found that the topic distributions in laypeople’s discussions were similar to the distributions in promotional Lynch syndrome–related information. Furthermore, most people had a positive attitude when discussing Lynch syndrome. The proportion of negative tweets was 3.51%. Within each topic, treatment (16.67%) and genetic testing (5.60%) had more negative tweets compared with other topics. When comparing monthly trends, laypeople’s discussions had a strong correlation with promotional Lynch syndrome–related information on awareness (r=.98, P<.001), while there were moderate correlations on screening (r=.602, P=.05), genetic testing (r=.624, P=.04), treatment (r=.69, P=.02), and risk (r=.66, P=.03). We also discovered that the Colon Cancer Awareness Month (March 2017) and the Lynch Syndrome Awareness Day (March 22, 2017) had significant positive impacts on laypeople’s discussions and their attitudes.

Conclusions: There is evidence that participative social media platforms, namely Twitter, offer unique opportunities to inform cancer communication surveillance and to explore the mechanisms by which these new communication media affect individual health behavior and population health.

Contact person: Jiang Bian, ji0ng.bi0n@gmail.com
                Yunpeng Zhao, zhaoyunpeng111@gmail.com


Let us know if you have further questions.

# Dataset Collection
This repository contains the ids of the tweets we used in our paper (`Lynch_tweet_ids.json`).  To collect the actual data, follow the steps below.

## Step one. Install `tweetf0rm`

In order to run the code, you need python 3+. 
First, 
```
git clone git://github.com/bianjiang/tweetf0rm.git
```
Then install the required packages.
```
pip install -r requirements.txt
```

## Step two. Obtain your own Twitter API keys 

* First, you'll want to log onto the twitter dev site and create an applciation at https://dev.twitter.com/apps to have access to the Twitter API!
* Create an access token and grab your applications ``Consumer Key``, ``Consumer Secret``, ``Access token`` and ``Access token secret`` from the OAuth tool tab. Put these information into a ``config.json`` under ``apikeys`` (see an example below).

```json
{
        "apikeys": {
                "i0mf0rmer01": {
                        "app_key": "APP_KEY",
                        "app_secret": "APP_SECRET",
                        "oauth_token": "OAUTH_TOKEN",
                        "oauth_token_secret": "OAUTH_TOKEN_SECRET"
                }
        }
}

```

## Step three. Crawl tweets by tweet ids

In general,
* `-c`: the config file for Twitter API keys
* `-o`: the output folder (where you want to hold your data)
* `-cmd`: the command you want to run
* `-cc`: the config file for the command (each command often needs different config files, see examples below)
* `-wait`: wait `x` secs between calls (only in REST API access)

Run the following command to obtain the lynch syndrome data.
```
python twitter_tracker.py -c ./config.json -o data/tweets_lynch_syndrome -cc ./Lynch_tweet_ids.json -cmd tweets_by_id
```
