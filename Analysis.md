
Analysis mainpage 
--

So you came for the story. Good on you (: 
let me start you off with an explanation on what CK3 is. 
Crusader Kings 3 is a strategy and roleplaying game in which you take control of a historical figure starting in wither 867 or 1066. From here you decide what you want to do, but for the majority of players it involves creating a successful lineage that expands its influence over the medieval world. Spreading (and controlling) its culture and religion.
With this as the focus of the game, and the game developers trying their hardest to create a realistic staring point I got inspired to test out some modern day political theory on the game world and its somewhat easily available dataset. 
While this is fun enough by itself, I recalled from my own background in social science a theory of international politics from the article “clash of civilizations?”, published in 1993 by Harvard professor Samuel P Huntington of Harvard University. A theory that roughly states that post-Cold War conflict would most frequently and violently occur because of cultural rather than ideological differences.
Or as The LA times summarized Huntington’s later book with the same name: “He argued that in a post-Cold War world, violent conflict would come not from ideological friction between nation states, but from cultural and religious differences among the world’s major civilizations. “ [LA times summary](https://www.latimes.com/archives/la-xpm-2008-dec-28-me-huntington28-story.html) 

If it was the case that a world without overarching ideologies tended to have conflicts on based of the friction between cultures and I was sitting on a dataset approximating cultures in the medieval era. A time before ideologies it might indeed be interesting to see how pronounced this tendency for conflict is. 

### How do we find places of friction/conflict

First thing first we need to find a overview of the country, cultures and other significant attributes that might relate the game to the theory, thankfully the game developers have a wiki in place that provides us with just such a table [countylist](https://ck3.paradoxwikis.com/List_of_counties).

After downloading the table, I import it to the network visualization and investigation tool Gephi.
In Gephi datapoints are shown in an overview tab as two types of datapoints nodes and edges, or dots and lines in layman’s terms.

**Nodes and Edges**
In network analysis a node is any entity connected to other entities via a link/edge/or other line. In a unweighted network like mine, the relative importance of a given node is dependent on how many other nodes it is dependent on.  In the picture below a series of nodes are shown with a varying shading of green. The more nodes a node is connected to the greener it becomes.



<img src="images/actor network.png" alt="hi" class="inline"/>

The same function of “inherited” importance or relevance can be used in our CK3 network of  countys, cultures and empires. It can also be used to form groupings.
As I import the table to Gephi I specify that I want county to be linked to their default groups: Duchys, Kingdoms, Empires, Cultures and Religions. 
An overall picture of what this grouping looks like can be seen on the following link:
[grouping] (indsæt link til circle pack)
Here we see each empire in the game colored by itself. I have however additionally used something called modularity to cluster all the nodes. Modularity is a tool design to calculate what connected nodes are most likely to belong to the same group, additional information on how this is done, can be found in the [Explainer notebook](https://rolfoe.github.io/project-assignment-B/Explainer_notebook.md). What it means here is simply that empires that share more nodes tend to cluster more together. Share nodes here meaning sharing: counties that be themselves share links to cultures and religions.
This is a nice map to get an idea of what we are looking at, but it does not show us what the most important places are. At this point one would be forgiven for thinking the most important node is simply the largest unit as it has most other nodes connecting it. likely some sort of empire, religion, or culture.
But since these terms are but names given to a cluster of counties they cannot carry much conflict in and of themselves. After all geography is determined at the county level. 
Thanks to network science we do however have other ways of investigating the network. There are several ways of finding a node that carries importance in a network in this projects we will be using “betweenness centrality”.
** betweenness centrality**
betweenness centrality is a way of measuring how many times each node part of the shortest bridges between two other nodes in the same network. You literally calculate the shortest path between every pair of nodes in you network. The fraction of times each node is found on such a path, divided by the total number of pairs. Is then the betweenness centrality of that node.
For our purpose, as no two countries are connected by themselves, but all counties a connected via attributes such as region empires and culture, this means that the county with the highest betweenness centrality is the county not only between two attribute nodes. But it is also on the shortest path between other county nodes. Making it  a measurement  of friction and contestation insofar as culture, religion, or administration can be considered too increase friction and contestation like the theory predicts. 
The link to the map below has been created with that in mind. First by calculating betweenness centrality of all nodes, and the manually setting the betweenness centrality of all non-counties to 0.

[Betweenness centrality map](https://rolfoe.github.io/project-assignment-B/CK3-County-Network-Force%20Atlas-%20betweenness%20centrality/#)

The way these nodes are spread around is done via an algorithm native to Gephi called “Force-Atlas-2. Which pushes all nodes away from one another, but attracts those linked via an edge

Does these counties have something in common, well a quick look, eyeballing if you will, at the data attributes shows us that they all have unconventional mixes of culture and religion or are a minority in their empire. 
<indsæt link til betweenness centrality table>
This is as expected as we by betweenness centrality are measuring those that link the most different nodes together, and being the only Picts in a Norse religion as is the case of the Shetland isles, means that they are connecting all the Pictish counties to counties following the Norse religion.
The very top node I terms of betweenness centrality is the node Tunis, a Catholic county in an Muslim empire, with a culture that usually is found among countys much further west. Positioning them as very much a bridge between a great many things

So now we have a network map of what counties ought to be the most conflict prone, as we have list showing the county with the highest betweenness centrality.
But are they actually more prone to conflict?
Enter Natural Language Processing (NLP) and the least scientifically part of this project website as you will see.
### NLP
Natural Language Processing is a way to interact with text and text corpuses via code. What is done here is a quantifying of the number of times a word appear in a text and comparing that to how often it does so in another.
During the course mentioned at the top of the page, was made aware of a text corpus where people had rated 10.000 words as being more or less positive and negative. A corpus which correlated negative words strongly with conflict and war. Meaning I could compare this corpus to a text corpus about my counties.  
What text do I have of my county’s? well the best place for archaic knowledge online of course, Wikipedia! 
The following step is scraping the Wikipedia page of all the counties in the list above and comparing it to the supposedly more conflict prone ones from the table above.

While the NLP I am about to do is good in and of itself several issues emerge. first off, the Wikipedia pages are of the countries today and not in the year 1066, second not all of the countries are immediately scrapable, as the scraper I use cannot abide non-latin characters as it simply look up the web-URL. Neither does it deal well with page redirects, meaning that even when I do get it to scrape a non-conventional url-character, the content I get can end up looking like this: “#REDIRECT [[Baqen]]” as is the case for the county of “Baqên”.
In other words, don’t take these results as something important.



