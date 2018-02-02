# Tweets related to lynch syndrome

In the following introduction you will learn how to use our tweets collecting tool (tweetf0rm) to fetch the Twitter data which is described in our twitter lynch paper, [Using Social Media Data to Understand the Impact of Promotional Information on Laypeople’s Discussions: A Case Study of Lynch Syndrome](https://www.jmir.org/2017/12/e414).
 

# Citation
* If you want to use our twitter lynch data or get an inspiration from our study, please cite this article:
   * *Bian J, Zhao Y, Salloum RG, Guo Y, Wang M, Prosperi M, Zhang H, Du X, Ramirez-Diaz LJ, He Z, Sun Y. [Using Social Media Data to Understand the Impact of Promotional Information on Laypeople’s Discussions: A Case Study of Lynch Syndrome](https://www.jmir.org/2017/12/e414). J Med Internet Res 2017;19(12):e414. DOI: 10.2196/jmir.9266. PMID: 29237586*

> **Abstract:** 
Objective: This study aimed to provide a detailed examination of how promotional health information related to Lynch syndrome impacts laypeople’s discussions on a social media platform (Twitter) in terms of topic awareness and attitudes.

> Methods: We used topic modeling and sentiment analysis techniques on Lynch syndrome–related tweets to answer the following research questions (RQs): (1) what are the most discussed topics in Lynch syndrome–related tweets?; (2) how promotional Lynch syndrome–related information on Twitter affects laypeople’s discussions?; and (3) what impact do the Lynch syndrome awareness activities in the Colon Cancer Awareness Month and Lynch Syndrome Awareness Day have on laypeople’s discussions and their attitudes? In particular, we used a set of keywords to collect Lynch syndrome–related tweets from October 26, 2016 to August 11, 2017 (289 days) through the Twitter public search application programming interface (API). We experimented with two different classification methods to categorize tweets into the following three classes: (1) irrelevant, (2) promotional health information, and (3) laypeople’s discussions. We applied a topic modeling method to discover the themes in these Lynch syndrome–related tweets and conducted sentiment analysis on each layperson’s tweet to gauge the writer’s attitude (ie, positive, negative, and neutral) toward Lynch syndrome. The topic modeling and sentiment analysis results were elaborated to answer the three RQs.


Contact person: Jiang Bian, ji0ng.bi0n@gmail.com
                Yunpeng Zhao, zhaoyunpeng111@gmail.com


Don't hesitate to send us an e-mail or report an issue, if something is broken (and it shouldn't be) or if you have further questions.

> This repository contains the tweet ids for fething the data we used in twitter lynch study. The file location is .... 

# Dataset Collection
## Step one. Install tweet crawler

In order to run the code, you need python 3+ 
just clone this and start using it.
```
git clone git://github.com/bianjiang/tweetf0rm.git
```

Then install required packages by command.
```
pip install -r requirements.txt
```
## Step two. Register your api key and secret 

* First, you'll want to login the twitter dev site and create an applciation at https://dev.twitter.com/apps to have access to the Twitter API!
* After you register, create an access token and grab your applications ``Consumer Key``, ``Consumer Secret``, ``Access token`` and ``Access token secret`` from the OAuth tool tab. Put these information into a ``config.json`` under ``apikeys`` (see an example below).

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

## Step three. Using command to crawl tweets by tweets' ids

In general,
* `-c`: the config file for Twitter API keys
* `-o`: the output folder (where you want to hold your data)
* `-cmd`: the command you want to run
* `-cc`: the config file for the command (each command often needs different config files, see examples below)
* `-wait`: wait `x` secs between calls (only in REST API access)


```
python twitter_tracker.py -c ../twittertracker-config/config_i0mf0rmer08.json -o data/tweets_id_range -cmd tweets_by_id -cc test_data/tweets_id.json
```
