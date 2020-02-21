# Identifying Language Trends Among Queer Communities
### By: Q Leedham

This project was originally assigned to me as part of the General Assembly Data Science Immersive course.

## Problem Statement

A linguistic professor recently approached me about a project looking into the language used by various members of the queer community. Specifically, they're interested in seeing if there's any difference in the language different subcommunities use when talking amongst themselves. They asked me to help looking into the language used by the trans and queer women (or lesbian) communities, as I fit into both of those. The question I'm looking to answer is: is there a meaningful difference between the language the used in the trans community and the language used in the lesbian communities?

I will use data scraped from the r/traaaaaaannnnnnnnnns and r/actuallesbians to explore this question. I'll use various classification models to answer the question, and use accuracy to select my models.

## Data Dictionary

|Feature|Type|Description|
|---|---|---|
|title|Object|Title of the post found on Reddit|
|selftext|Object|Text of the post, if any|
|subreddit|Object|The subreddit the post came from. Either r/traaaaaaannnnnnnnnns or r/actuallesbians|
|created_utc|Int|The UTC timestamp of the post|
|author|Object|Author of the post|
|author_flair_text_|Object|Flair text of the author of each post, if any|
|score|Int|The score of the post on Reddit|
|is_self|bool|Whether the post contains selftext|
|timestamp|Object|The date the post was made|


## Executive Summary

The goal of this project is to find out if it's possible to classify posts made by the trans community and the lesbian community using posts shared on Reddit. Codeswitching, the act of changing your vocabularly and mannerisms when you're in a group of like people compared to society at large, can happen in the queer community, but does it happen in subcommunities within it? I tried to see if this is the case using various classification methods.

For the most part, the posts on in the two subreddits I looked at did not have any selftext, or body text, so the models used only the titles of the posts that were scraped.

The best model for this was a Multinomial Naive Bayes model, though many other classification models came close in terms of accuracy. Despite the potential overlap of the two communities I looked at, the models were able to successfully classify posts with some accuracy. They can be used to help show the difference in language used within these two subgroups.

![top words in r/actuallesbians](/images/top_words_les.png)

All of the top words in r/actuallesbians are single words, despite the model's ngram range of (1, 3), so there are no common phrases that are often repeated on the subreddit. The top words in the community do say a lot about the tone of the discussion there. Both "lesbian" and "lesbians" are included in the top list of words, along with words like "love," and "girlfriend." The word choice seems to indicate that the community tends to be very individualized with members talking about themselves of the people they're close to.

![top words in r/traaaaaaannnnnnnnnns](/images/top_words_trans.png)

Unsurprisingly, the most common word used in r/traaaaaaannnnnnnnnns is "trans." The word is also used in a few phrases that are included in the list of top words or phrases. There is a lot of talk about trans rights in r/traaaaaaannnnnnnnnns, with the phrase "says trans rights" appearing often enough to be high on the list of most frequently used words or phrases. The phrase is often used to indicate that a [person or company supports trans rights](https://knowyourmeme.com/memes/trans-rights). The phrase is usually paired with an image of something in the colors of the trans flag (blue, pink, and white).


## Conclusion

While it is possible to classify posts from r/actuallesbians and r/traaaaaaannnnnnnnnns with decent accuracy, there doesn't appear to be many stand out words that seperate the two groups. After running through several models we were only to accurately predict lesbian-specific posts 76.8% of the time and trans-specific posts about 78.1% of the time. Beyond the words "trans" and "rights," there are no uncommon words that are specific to either community.

From this we can say that there is a difference in how the two communities speak amongst themselves, but that difference is smaller than we may have thought before working on this project. This could potentially be due to overlap in the two groups. While r/traaaaaaannnnnnnnnns is dedicated to trans and non-binary individuals, many would still be welcome in r/actuallesbians which accepts cis, trans, lesbian, bisexual, and pansexual people who feel they fit in the category of "queer woman."

## Recommendations 

As mentioned in the conclusion, there is the potential for a lot of overlap between the two subreddits chosen for this project. While sticking to Reddit, it might be beneficial to choose other queer communities on the platform to see if there are bigger differences between queer men and queer women, for example. There would be much less overlap between two such communities.

Further research could also examine how queer communities talk to themsleves compared to how they talk to other people. A good example of this would be using r/traaaaaaannnnnnnnnns (or another subreddit for trans people, made by trans people) to something like r/asktransgender, a subreddit where (mostly) cis or questioning people can ask questions of the trans community. There might be similar word choices in such a scenario, but there has the potential to be some code-switching that happens when trans people speak to an assumed cis audience versus speaking to an assumed trans audience.