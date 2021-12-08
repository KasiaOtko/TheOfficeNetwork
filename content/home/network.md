---
title: "About the network - brief introduction"
draft: false
weight: 30
---

Based on the content of Wiki pages, we built our first directed network. After removing isolated nodes and extracting the largest connected component, it consists of 284 nodes and 1241 links between them.  
Top 5 in-degree nodes are: Michael Scott (113), Dwight Schrute (94), Jim Halpert (81), Pam Beesly (77) and Andy Bernard (57).  
Top 5 out-degree nodes are: Andy Bernard (33), Michael Scott (26), Phyllis Vance (26), Pam Beesly (24) and Dwight Schrute (24).

![Wiki pages network](/img/wiki_pages_network.png)

Degree distribution of the out-degrees of our network (right) shares similarities to the degree distribution of a **random Erdős–Rényi network**. The in-degree distribution (left) is quite different from the Poisson distribution characterizing random networks and seems to follow a **power law**, which is the defining characteristic of a scale-free network.  
The reason for this difference may lay in a way the wiki pages are written, that is, there is no detailed description of who exactly a particular character interacted with in every single scene and this description is mainly limited to the connections to the main characters like Michael, Dwight, Pam and Jim, who have the highest in-degree (which means that they are mentioned in a lot of character pages).

![Distribution](/img/Degree_distribution.png)

To investigate the relationship between in- and out-degree values for each node, we created the below visualisation. It shows a **clear positive relationship** between the in-degree and out-degree values on the log(1+x) scale, which is reflected in a Pearson correlation equal to 0.75. This means that a node with a lot of in-coming links will also have a lot of out-going edges. Additionally, third plot presenting the excess degree defined as k_ex = k_in - k_out [1] shows that <b>for most characters in-degree is usually close to out-degree</b>. We can see some exceptions in a form of a long right tail - these are of course hubs - main characters like Michael, Jim, Dwigt and Pam who have a lot of in-coming links and much fewer out-coming ones.

![In_out_degree](/img/In_out_degree.png)

<hr>

<div align="left">
<h5>Authors:</h5> 
Maja Jønck Hjuler (s164590)  <br>
Katarzyna Otko (s202872)  <br>
Malthe Andreas Lejbølle Jelstrup (s184291)<br>
<br>

### References

[1] Liu XF, Liu YL, Lu XH, Wang QX, Wang TX (2016) The Anatomy of the Global Football Player Transfer Network: Club Functionalities versus Network Properties. PLOS ONE 11(6): e0156504. https://doi.org/10.1371/journal.pone.0156504.