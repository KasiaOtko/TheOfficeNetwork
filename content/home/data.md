---
title: "About the data"
draft: false
weight: 10
---

We based our analysis on two main data sources: [Dunderpedia](https://theoffice.fandom.com/wiki/Main_Page): the online encyclopedia about The Office and the [dialogues](https://www.kaggle.com/nasirkhalid24/the-office-us-complete-dialoguetranscript?select=The-Office-Lines-V4.csv) - a collection of all lines said in every single scene in 185 episodes.


To collect data that could serve as a source for our **network**, we extracted the raw HTML code behind the [pages](https://theoffice.fandom.com/wiki/Category:Characters) with a list of characters. As character attributes we used **gender**, list of **seasons** a character appeared in, **Dunder Mifflin branch**, and whether a character is a **warehouse worker** or not.

From the figure below, it can be seen that we have 158 males, 106 females and 25 characters with unknown gender in our dataset.

![Gender distribution](/img/Gender_distribution.png)

The dialogues dataset consists of 54626 lines along with information about which `season`, `episode` and `scene` each line was said in and by whom (`speaker` column).