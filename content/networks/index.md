---
title: "Network analysis"
date: 2021-11-27T19:10:18+01:00
draft: false
---

In this section we applied different algorithms for community detection. By partitioning our network into communities we want to uncover hidden structure in the network and discover close relationships between our characters.  

<h4> Louvain algorithm for community detection </h4>
We can detect communities using variety of methods. The below visualisation shows communities detected by **Louvain algorithm**. The great part is that it is interactive - you can zoom in to investigate the links in more detail, click on the nodes to highlight the links or even drag the nodes! For the sake of clarity, only the names of the most prominnet characters are displayed.

<div align="center">
<iframe src="first_network.html" width=1000px height=600px></iframe>
</div>

Number of communities found is 9 and the corresponding modularity score is 0.36. In the context of this measure a partition is good when when there are **many edges within communities and only a few between them** [1] (nodes are densely connected within a community and sparsely connected with the rest of the graph [2]). According to [1], modularity above about 0.3 is a good indicator of significant community structure in a network in practice (network corresponds to a statistically surprising arrangement of edges).

One of natural questions that may come to one's mind - can this partition be done based on the branch that a character worked in? By investigating the above plot we can certainly say this is not the case, otherwise most of main characters should be assigned to one community representing Scranton branch. Let us then take a closer look at the most connected characters in each community. 

Below presented are **top 7 most connected characters** (in terms of a total node degree in a full network) **in each community**, represented as 3-column block (`Community`, `Name` and `Degree`), which is repeated for every detected community. Direction of reading of the below table is therefore from **left to right**.  
The aim is to see what are the most prominent members in each community, without distracting the reader with side- or guest characters that one might not recognize.
  
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-1wig{font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-amwm{font-weight:bold;text-align:center;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-amwm" colspan="2">Community 0<br>(n = 66)</th>
    <th class="tg-amwm" colspan="2">Community 1<br>(n = 32)</th>
    <th class="tg-amwm" colspan="2">Community 2<br>(n = 10)</th>
    <th class="tg-amwm" colspan="2">Community 3<br>(n = 25)</th>
    <th class="tg-amwm" colspan="2">Community 4<br>(n = 52)</th>
    <th class="tg-amwm" colspan="2">Community 5<br>(n = 39)</th>
    <th class="tg-amwm" colspan="2">Community 6<br>(n = 25)</th>
    <th class="tg-amwm" colspan="2">Community 7<br>(n = 6)</th>
    <th class="tg-amwm" colspan="2">Community 8<br>(n = 29)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-1wig">Name</td>
    <td class="tg-1wig">Degree</td>
    <td class="tg-1wig">Name</td>
    <td class="tg-1wig">Degree</td>
    <td class="tg-1wig">Name</td>
    <td class="tg-1wig">Degree</td>
    <td class="tg-1wig">Name</td>
    <td class="tg-1wig">Degree</td>
    <td class="tg-1wig">Name</td>
    <td class="tg-1wig">Degree</td>
    <td class="tg-1wig">Name</td>
    <td class="tg-1wig">Degree</td>
    <td class="tg-1wig">Name</td>
    <td class="tg-1wig">Degree</td>
    <td class="tg-1wig">Name</td>
    <td class="tg-1wig">Degree</td>
    <td class="tg-1wig">Name</td>
    <td class="tg-1wig">Degree</td>
  </tr>
  <tr>
    <td class="tg-0lax">Michael Scott</td>
    <td class="tg-0lax">139</td>
    <td class="tg-0lax">Jim Halpert</td>
    <td class="tg-0lax">104</td>
    <td class="tg-0lax">Kevin Malone</td>
    <td class="tg-0lax">43</td>
    <td class="tg-0lax">Ryan Howard</td>
    <td class="tg-0lax">42</td>
    <td class="tg-0lax">Andy Bernard</td>
    <td class="tg-0lax">90</td>
    <td class="tg-0lax">Dwight Schrute</td>
    <td class="tg-0lax">118</td>
    <td class="tg-0lax">Jan Levinson</td>
    <td class="tg-0lax">52</td>
    <td class="tg-0lax">Dawn Tinsley</td>
    <td class="tg-0lax">11.0</td>
    <td class="tg-0lax">Phyllis Vance</td>
    <td class="tg-0lax">55</td>
  </tr>
  <tr>
    <td class="tg-0lax">Toby Flenderson</td>
    <td class="tg-0lax">51</td>
    <td class="tg-0lax">Pam Beesly</td>
    <td class="tg-0lax">101</td>
    <td class="tg-0lax">Stacy</td>
    <td class="tg-0lax">8</td>
    <td class="tg-0lax">David Wallace</td>
    <td class="tg-0lax">40</td>
    <td class="tg-0lax">Erin Hannon</td>
    <td class="tg-0lax">42</td>
    <td class="tg-0lax">Angela Martin</td>
    <td class="tg-0lax">52</td>
    <td class="tg-0lax">Michael Scarn</td>
    <td class="tg-0lax">12</td>
    <td class="tg-0lax">Tim Canterbury</td>
    <td class="tg-0lax">9.0</td>
    <td class="tg-0lax">Stanley Hudson</td>
    <td class="tg-0lax">27</td>
  </tr>
  <tr>
    <td class="tg-0lax">Meredith Palmer</td>
    <td class="tg-0lax">35</td>
    <td class="tg-0lax">Cecelia Halpert</td>
    <td class="tg-0lax">24</td>
    <td class="tg-0lax">Brenda Matlowe</td>
    <td class="tg-0lax">6</td>
    <td class="tg-0lax">Karen Filippelli</td>
    <td class="tg-0lax">27</td>
    <td class="tg-0lax">Kelly Kapoor</td>
    <td class="tg-0lax">40</td>
    <td class="tg-0lax">Oscar Martinez</td>
    <td class="tg-0lax">49</td>
    <td class="tg-0lax">Astrid Levinson</td>
    <td class="tg-0lax">9</td>
    <td class="tg-0lax">Gareth Keenan</td>
    <td class="tg-0lax">8.0</td>
    <td class="tg-0lax">Clark Green</td>
    <td class="tg-0lax">21</td>
  </tr>
  <tr>
    <td class="tg-0lax">Holly Flax</td>
    <td class="tg-0lax">34</td>
    <td class="tg-0lax">Helene Beesly</td>
    <td class="tg-0lax">16</td>
    <td class="tg-0lax">Pizza Delivery Kid</td>
    <td class="tg-0lax">6</td>
    <td class="tg-0lax">Nellie Bertram</td>
    <td class="tg-0lax">17</td>
    <td class="tg-0lax">Darryl Philbin</td>
    <td class="tg-0lax">38</td>
    <td class="tg-0lax">Pete Miller</td>
    <td class="tg-0lax">24</td>
    <td class="tg-0lax">Gil</td>
    <td class="tg-0lax">8</td>
    <td class="tg-0lax">Lee</td>
    <td class="tg-0lax">6.0</td>
    <td class="tg-0lax">Todd Packer</td>
    <td class="tg-0lax">19</td>
  </tr>
  <tr>
    <td class="tg-0lax">Creed Bratton</td>
    <td class="tg-0lax">27</td>
    <td class="tg-0lax">Roy Anderson</td>
    <td class="tg-0lax">16</td>
    <td class="tg-0lax">Abby</td>
    <td class="tg-0lax">5</td>
    <td class="tg-0lax">Charles Miner</td>
    <td class="tg-0lax">16</td>
    <td class="tg-0lax">Robert California</td>
    <td class="tg-0lax">33</td>
    <td class="tg-0lax">Mose Schrute</td>
    <td class="tg-0lax">11</td>
    <td class="tg-0lax">Goldenface</td>
    <td class="tg-0lax">7</td>
    <td class="tg-0lax">Keith Bishop</td>
    <td class="tg-0lax">4.0</td>
    <td class="tg-0lax">Bob Vance</td>
    <td class="tg-0lax">18</td>
  </tr>
  <tr>
    <td class="tg-0lax">Hannah Smoterich-Barr</td>
    <td class="tg-0lax">11</td>
    <td class="tg-0lax">Phillip Halpert</td>
    <td class="tg-0lax">15</td>
    <td class="tg-0lax">Lynn</td>
    <td class="tg-0lax">2</td>
    <td class="tg-0lax">Josh Porter</td>
    <td class="tg-0lax">12</td>
    <td class="tg-0lax">Gabe Lewis</td>
    <td class="tg-0lax">31</td>
    <td class="tg-0lax">Robert Lipton</td>
    <td class="tg-0lax">11</td>
    <td class="tg-0lax">Hunter Raymond</td>
    <td class="tg-0lax">7</td>
    <td class="tg-0lax">Donna (UK)</td>
    <td class="tg-0lax">3.0</td>
    <td class="tg-0lax">Cynthia</td>
    <td class="tg-0lax">9</td>
  </tr>
  <tr>
    <td class="tg-0lax">Louanne Kelley</td>
    <td class="tg-0lax">11</td>
    <td class="tg-0lax">Betsy Halpert</td>
    <td class="tg-0lax">13</td>
    <td class="tg-0lax">Melissa Riley</td>
    <td class="tg-0lax">2</td>
    <td class="tg-0lax">Alan Brand</td>
    <td class="tg-0lax">6</td>
    <td class="tg-0lax">Deangelo Vickers</td>
    <td class="tg-0lax">20</td>
    <td class="tg-0lax">Cameraman</td>
    <td class="tg-0lax">9</td>
    <td class="tg-0lax">Carol Stills</td>
    <td class="tg-0lax">6</td>
    <td class="tg-0lax"></td>
    <td class="tg-0lax"></td>
    <td class="tg-0lax">Teri Hudson</td>
    <td class="tg-0lax">9</td>
  </tr>
</tbody>
</table>

Some of the key insights derived from the above table and visualisation:
* Michael Scott is a member of the biggest community (community 0), consisting of 66 people. It is reasonable that [Holly Flax](https://theoffice.fandom.com/wiki/Holly_Flax) (Michael's soulmate) is a member too. To our surprise, he is not connected with any of the main characters besides [Meredith](https://theoffice.fandom.com/wiki/Meredith_Palmer) and [Creed](https://theoffice.fandom.com/wiki/Creed_Bratton), who don't seem to have many friends outside the Scranton Branch and even within it they **did not establish many relationships**. Besides them, the r**est of members have very low degrees**.
* Community 1 seems to be **the best defined** as it is centered around the **relationship betweem Jim and Pam and their families** (we see characters with Beesly and Halpert surnames and [Roy Anderson](https://theoffice.fandom.com/wiki/Roy_Anderson) - former Pam's fiancé).
* Community 2 is a **small community centered around** [Kevin Malone](https://theoffice.fandom.com/wiki/Kevin_Malone) as it includes his sister, daughter, and girlfriends.
* Community 3 consists of employees working in different **Dunder Mifflin branches**, usually occupying (at some point) **managerial positions**, including [David Wallace](https://theoffice.fandom.com/wiki/David_Wallace) - company CFO and later CEO - and his family.

Remaining communities include the rest of main characters in different proportions which is also depenednt on how many different threads along the show they share. For example, in community 4 we have Dwight and Angela who had an affair at the beginning of the show. We also have Oscar who is an accountant just like Angela but he also had an affair with Angela's husband - Robert Lipton!

<h4> Networkx algorithms for community detection </h4>

However, the modularity score is not as high as presented in [3] or [4], which suggests that the communities are not very well defined. Therefore, we tried other algorithms to see if they are more suitable for this type of network.

Two other algorithms that we tested:
* `greedy_modularity_communities` - This function implements **greedy modularity maximization** algorithm described in [4] by Aaron Clauset, M. E. J. Newman and Cristopher Moore. It begins with each node in its own community and joins the pair of communities that most increases modularity until no such pair exists.
* `async_fluidc` - this function implements FLuid Communities algorithm desribed in [5] by Ferran Pares et al. It mimics the behaviour of several fluids (i.e., communities) expanding and pushing one another in a shared, closed and non-homogeneous environment (i.e., a graph), until equilibrium is found.

Below presented is a summary of modularities found by the three algorithms.

![Modularity comparison](/img/Modulairy_comparison.png)

As can be seen from the summary above, we **did not get significantly better results**. We have a slightly higher modularity for a partition returned by a greedy algorithm. However, the difference is at the level of 0.003 which we might by eliminated by rerunning Louvain algorithm as it is a **randomized** method.

One reason behind not so high modularity value might be the bias in the network originated from wiki pages. We need to keep in mind that there is a **tendency of mentioning only the most prominent characters in the description of every other character**. It is understandable that the texts do not include every single encounter or interaction as this is not the purpuse of this website. But we must be aware this fact "skews" the network significantly towards main roles in our tv series.

But is that all we can do to understand the structure of communities in The Office? Of course not :D In the following section we'll make use of our **dialogues dataset** to see if there's something more to be discovered.
  
<h4> Weighted network based on dialogues </h4>

Our dialogues dataset contains every line ever said in The Office. We also know who said it, and in what season, episode and scene. We used this information to create a weighted network. **A link between two characters is placed if they shared at least one scene and weight is the number of scenes shared**.

The resulting network is presented below:

<div align="center">
<iframe src="weighted_network.html" width=1000px height=500px></iframe>
</div>

After running the three algorithms on a weighted network, we obtained the following results:

![Modularity comparison weighted](/img/Modularity_comparison_weighted.png)

Unfortunately, the results are even **worse than for the basic network**, created from Wiki pages.  

But we can observe that this network also consists of many nodes with a very low degree - characters that played only in one or two scenes and are mostly connected only to the biggest hubs. What if we could remove these nodes in a specified manner, downgrade the role of hubs and focus our attention only on the most relevant connections? This is what the next section is going to be about.

<h4> Extracting backbone of a weighted network </h4>

This subsection exploits the idea presented in "Extracting the multiscale backbone of complex weighted networks" [5]. We aim at creating a reduced but more meaningful version of our initial weighted network and **focus our attention only on the most significant connections** to see if the community structure in such a representation will be better defined. 

<h3> References </h3>

[1] A. Clauset, M. E. J. Newman, C. Moore, (2004), "Finding community structure in very large networks", DOI: 10.1103/PhysRevE.70.066111, https://arxiv.org/abs/cond-mat/0408187.  

[2] F. Pares, D. Garcia-Gasulla, A. Vilalta et al. (2017), "Fluid Communities: A Competitive, Scalable and Diverse Community Detection Algorithm", https://arxiv.org/abs/1703.09307v3.  

[3] U. Brandes, D. Delling, M. Gaertler et al. (February 2008). "On Modularity Clustering". IEEE Transactions on Knowledge and Data Engineering. 20 (2): 172–188. https://dx.doi.org/10.1109/TKDE.2007.190689.  

[4] Newman, M. E. J. (2006). "Modularity and community structure in networks". Proceedings of the National Academy of Sciences of the United States of America. 103 (23): 8577–8696. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1482622/.  

[5] M. A. Serranoa, M. Boguñáb, A. Vespignani (2009), "Extracting the multiscale backbone of complex weighted networks", https://www.pnas.org/content/pnas/106/16/6483.full.pdf.  