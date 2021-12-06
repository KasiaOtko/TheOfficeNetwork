---
title: "Text analysis"
date: 2021-11-27T19:17:22+01:00
draft: false
---

## Sentiment analysis

In the first part of this analysis, we investigate the **sentiment of character dialogue from the entire TV series**, ie. all 9 seasons combined. A temporal analysis is given in the following section, where the dialogue from each season is handled separately.

To calculate the sentiments of dialogues using LabMT word list (dictionary-based approach) [1], we first preprocessed the dialogues and filtered out the tokens that are not available in the **LabMT** list. To calculate sentiments using **VADER** word list (the rule-based approach) [2], we did not do any preprocessing (except for removing symbols that are not alfanumeric from the sentences) but input sentence by sentence to calculate the average compound polarity. The reason we did not apply any preprocessing is that we wanted to preserve the punctuation and capitalization of words as well as their order. 

### Overall sentiment analysis

<img src="/Overall_Sentiment_analysis.png" width="90%">
<center><em>Histograms of the LabMT (to the left) and VADER (to the right) sentiment for the entire The Office dialogue from Season 1-9. </em></center>
&nbsp;

As seen in the above figures, the **majority of the characters' dialogue have positive sentiment** as compared to the neutral, which is 5.0 and 0.0 for LabMT and VADER, respectively. Furthermore, the distribution of sentiment scores has the shape of a normal distribution for both dictionaries. In order to better visualize and compare results, we will limit our scope to only the **15 main characters** (as defined by us). Their sentiments are ranked below using the two different approaches.

<img src="/Overall_Sentiment_analysis_vader.png" width="90%">
<center><em>In the plots above, main characters are ranked according to the LabMT and VADER sentiment score of their entire dialogue in Season 1-9.</em></center>
&nbsp;

The **most positive** main character across all season using the dictionary-based approach is Ryan and the **most negative** is Meredith. Pam, Michael and Jim are all in the top six, which we would expect based on our prior knowledge about the show, however, among characters with negative sentiment we would expect to see Angela and Stanley. This hints to the the LabMT method being inaccurate. The sentiment analysis following the rule-based approach (VADER) leads to a ranking that is better in line with our expectations. Stanley, Meredith and Angela often complain and express themselves negatively around the office, whereas Michael and Jim are extremely energetic and positive, which is clearly expressed in their language. 

In fact, **LabMT doesn't work well with our dataset**, since we have very short sentences after removing stop words and hereby lose part of the context of the conversation. The rule-based VADER method tries to take the context of a sentence into account, that is, the overall sentiment of a sentence/document might be intensified or decreased based on how one word is used in combination with others. Hence, the **rule-based approach is a stronger tool** and we will only apply the VADER sentiment in the following sections.
 

### Temporal analysis: Character sentiment per season

In this section we will perform **sentiment analysis on the seperate seasons** of The Office to provide a temporal dimension. The plot below illustrates how some selected character's mood has changed throughout the TV series.

<img src="/Sentiment_per_season_selected_main_characters.png" width="90%">
<center><em>Comparison of how the sentiment of selected characters changes across seasons.</em></center>
&nbsp;

In the comparison above, Meredith's sentiment generally drops, while Darryl becomes more and more postive for every season. Again, Stanley and Angela are constantly having low scores. Dwight also has a very monotonuous mood across seasons, however, he expresses himself more positively than the two aforementioned characters. Jim is generally quite happy, but Michael tops the list when it comes to high sentiment scores, and this is despite a slight drop in Season 6. The plots below give an even better understanding of how main character's sentiment has developed across the different seasons. There is a point for every season the character appeared in the show.

<img src="/Sentiment_per_season.png" width="90%">
<center><em>The figure above includes plots of how the sentiment of main characters has changed over time.</em></center>
&nbsp;


### Sentiment of 2 people conversations: 😍 vs. 😡

This sections tries to answer the question: How are the characters' **attitudes towards each other**? <br>
Thus, we have isolated the **scenes where only two characters appear** and analysed the words they speak to each other. We thereby make two key assumptions about the two characters in the scene:<br> 

1) Their speech is directed to one another <br>
2) The **sentiment** of one person's dialogue represents their **attitude** to the other person<br>

The heatmap below illustrates the results. Speakers (1<sup>st</sup> character in the scene) are plotted along the x-axis, and Receivers (2<sup>nd</sup> person in the scene) are plotted along the y-axis. As an example, Dwight has a negative attitude towards Kevin (sentiment score = -0.11) whereas Kevin's attitude towards Dwight is positive (score = 0.06). Some pairs of characters never shared a scene together resulting in a blank square in the heatmap.

<img src="/Two_ppl_conversation_heatmap.png" width="90%">
<center><em>Sentiment of two people conversations based on dialogue from scenes where only two characters appear, i.e. Speakers and Receivers.</em></center>
&nbsp;

The sentiment scores displayed in the heatmap above are **highly dependent on the number of lines** the two given characters have spoken to each other. Ryan and Angela, for example, had very little conversations but the few lines Angela said to Ryan have negative sentiment resulting in a very low score in the heatmap (-0.46).

### EXTRA: Finding all "That's what she said" jokes

A reoccuring joke in The Office is the *That's what she said*-joke. The line is used in response to statements that may sound sexual in nature when taken out of context. **Michael is a big fan** of this joke, in fact, out of a total of 31 times the joke appears in the series Michael spoke 21 of them! Here are some examples:

<span style="font-family:Courier New; font-size:1.2em;">

> **Doctor: Does the skin look red and swollen?**
>> Dwight: That's what she said.

> **Jim: No, thanks. I'm good.** 
>> Michael: That's what she said.

> **Kevin: Why did you get it so big?**
>> Michael: A, that's what she said.

> **Lester: And you were directly under her the entire time?**
>> Michael: That's what she said.

> **Kelly: Dwight, get out of my nook!**
>> Pam: That's what she said.

</span>

## Wordclouds

Now we know **how** the main characters talk to each other. It is time to get know them even better and see WHAT are they talking about :) For this purpose we calulated TF-IDF scores for every character who spoke at least 15 lines. The figure below presents wordclouds, each consisting of 15 words with the highest TF-IDF score.

![Wordclouds](/img/Wordclouds.png)

Not this is something! We think that everyone familiar with The Office should be able to distinguish most of the characters by their wordclouds wothout looking at the titles :D We can also see that there are indeed some important bigrams. Let's take a closer look at some of the examples:
* [Here's](https://screenrant.com/office-andy-big-tuna-nickname-jim-why-explained/) an explanation for why Andy used "tuna" word so often. We also see "cornell" which is his alma mater and this is something he is very proud of.
* [During one of the Christmas parties, Angela sang](https://www.youtube.com/watch?v=Wiwrs8pL1E0) a ["The Little Drummer Boy"](https://www.youtube.com/watch?v=plGj8VRTqJE) song, which is why we see "pum_pum" in her wordcloud :D Additionally, she's a cat lover and one of cats she owned and talked a lot about was named Sprinkle. 
* Darryl is another character who sang songs - https://www.youtube.com/watch?v=i-bZSTLHJm4, https://www.youtube.com/watch?v=bV8i6oCgiAM
* Toby and [Stanley](https://www.youtube.com/watch?v=o0Wjo3bX1n0) really like to talk about their vacations :D

![Toby](/img/Toby.png)

However, we also note that we are aware of the fact that in our case some of the documents and the resulting TF-IDF values were influenced by single episodes, where the supporting characters played more scenes than in an "average" episode that were focused around one theme. This is visible for example for Stanley and word "toaster", which was a theme for only one episode.

## References

[1] Dodds P. S., Harris K. D., Kloumann I. M., Bliss C. A., Danforth C. M. (2011). "Temporal Patterns of Happiness and Information in a Global Social Network: Hedonometrics and Twitter". PLoS ONE 6 (12): e26752. https://doi.org/10.1371/journal.pone.0026752.

[2] Hutto, C., & Gilbert, E. (2014). "VADER: A Parsimonious Rule-Based Model for Sentiment Analysis of Social Media Text". Proceedings of the International AAAI Conference on Web and Social Media, 8(1), 216-225. https://ojs.aaai.org/index.php/ICWSM/article/view/14550