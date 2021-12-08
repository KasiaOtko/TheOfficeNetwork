---
title: "About the data - basic stats"
draft: false
weight: 20
---

We based our analysis on two main data sources: [Dunderpedia](https://theoffice.fandom.com/wiki/Main_Page): the online encyclopedia about The Office and the [dialogues](https://www.kaggle.com/nasirkhalid24/the-office-us-complete-dialoguetranscript?select=The-Office-Lines-V4.csv) - a collection of all lines said in every single scene in 185 episodes.


To collect data that could serve as a source for our **network**, we extracted the raw HTML code behind the [pages](https://theoffice.fandom.com/wiki/Category:Characters) with a list of characters. As character attributes we used **gender**, list of **seasons** a character appeared in and a **Dunder Mifflin branch**.

From the figure below, it can be seen that we have 158 males, 106 females and 25 characters with unknown gender in our dataset.

![Gender distribution](/img/Gender_distribution.png)


The dialogues dataset consists of 54626 lines along with information about which `season`, `episode` and `scene` each line was said in and by whom (`speaker` column).

Below you can examine number of lines spoken broken down by a character. Even though **Michael** wasn't present in the 8th season, he still holds the highest number of lines! Apart from that we can see that **Dwight, Jim and Pam** are the most prominent characters in this show. The 5th person in terms of the number of lines spoken is **Andy Bernard**, who replaced Michael Scott and became boss in the 8th season. The rest of the main characters spoke more or less the same number of lines.

![DIalogues](/img/Dialogues.png)

We created a new column - `number_of_words` - which tells us how many words there are in a single line. We can see that **Michael** speaks the longest lines on average. The standard deviation is also the highest for him which might indicate that he had the highest number of monologues, i.e. scenes where he talked to the camera alone.  
**Kevin** speaks the shortest sentences (with the lowest standard deviation as well) which makes sense since this character is not the smartest and lacks communication skills. Kevin received a job as an accountant at Dunder Mifflin after applying for a job in the warehouse because Michael Scott had "a feeling about him."

| Speaker 	| Sum of words 	|    Mean  	| Standard deviation 	|
|:---:	|:---:	|:---:	|:---:	|
| Michael 	| 147523 	| 13.56 	| 16.27 	|
| Dwight 	| 75134 	| 11.06 	| 12.46 	|
| Jim 	| 57550 	| 9.19 	| 10.84 	|
| Pam 	| 44807 	| 8.94 	| 10.78 	|
| Andy 	| 43746 	| 11.72 	| 12.69 	|
| Angela 	| 13391 	| 8.63 	| 9.65 	|
| Erin 	| 12763 	| 8.93 	| 10.37 	|
| Kevin 	| 12292 	| 7.97 	| 8.77 	|
| Oscar 	| 11903 	| 8.78 	| 9.04 	|
| Ryan 	| 11624 	| 9.79 	| 10.43 	|