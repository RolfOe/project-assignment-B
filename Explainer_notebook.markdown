# project-assignment-B
**Project assignment B for Social Graphs**

While this project is about the videogame Crusader Kings 3 (CK3), it is more so a showcase of tools tought in the university course Social Graphs at DTU.
Therefore is must be remembered that tihs project is more of a techinal showcase of tools, then a study in medival politics.
Any additon of political theory is there to give context and spice to the datamanipulation and calculations, and should not be taken as valid facts.
This is espicially true when comparing the language use of modern wikipedia articles, to historical areas of strife and contestation. 
While the method of comparing language use to historical regions may one day be developed into something, this project is not nearly refined enough to give vaild accounts.

This being said i hope you enjoy the tour.




    Motivation

the dataset from on this website is based on the table of counties from the following gamewiki https://ck3.paradoxwikis.com/List_of_counties.

the game itself is a game about political intrigue and warfare set in the middelages, and does a good job of emulating the world of its time.
the reason i thought of useing this game as a part of my project is that the former iteration crusader kings 2. had a build in wikipedia buttom allowing for direct acess to the wikipediapage of whatever county or politicla character you selected in game. while this feature was much hated for being messy I.e not working or sending you to the wrong page, i was wondering what i might find if i used my newly learned tools of wikipedia scraping and graphthroy to take a look at the newest itteration of the game.  



overall


    Why did you choose this/these particular dataset(s)?
    


    What was your goal for the end user's experience?
The goal for this project was to shead some knew light, on the the already extenisve knowledgebase, used by the Paradox gamedeveoplers in making CK3.
and to sate my own curiosity on the useability of tools i was tought in the class. when i go onto some on the wilder analysis on the webpage. Discussing the oft cited/oft critized "Clash of Civilasations?" from 1993, by Samuel P. Huntington of Harvard University. a book which in short  posit that post-Cold War conflict would most frequently and violently occur because of cultural rather than ideological differences. While huntington talks in regard to the post-coldwar era world, i decided that digging into a gamefied and historically distant version of this "war of cultures" made me less likely to get into politics.


    Basic stats. Let's understand the dataset better

    introduction ot the data
As this was a solo project i knew i had to find a reasonbly clean dataset to work with. Therefore i chose the dataset from this website: https://ck3.paradoxwikis.com/List_of_counties. Freeing up time to work on the data analysis and implementation on the website.

The analysis is centered around the county, as it is the games own point of reference to what culture or religion is present somewhere geographicly. Much as in real life a county is oftentime administed by some larger order of unit say a kingdom or a duchy. 

    cleaning and preprocessing
I made and used a Wikipedia scraper to scrape the Wikipedia pages of the 2548 counties in the column called 'County'. an operation that gave me access to 1981 articles. a secondary scrape based on the 'ID' collum, from the same table increased that number to 2051. as some of the ID contained a more appropriate spelling of county names.
the linking of countys to larger units was nice in terms of creating a sensible network but lead to to some data cleaning, as administrative units oftentime are named after dorminant countys or citys for example Essex being both a duchy and a county or worse Finland being both a Kingdom and a county worst offernder was the middel eastern county of Turin being merged with an empire node also called Turin which made the county the appears in the top 20 best connected nodes in the network.
    Write a short section that discusses the dataset stats (here you can recycle the work you did for Project Assignment A)

    Tools, theory and analysis. Describe the process of theory to insight
Gephi

NLP/NLTK
    Talk about how you've worked with text, including regular expressions, unicode, etc.
    Describe which network science tools and data analysis strategies you've used, how those network science measures work, and why the tools you've chosen are right for the problem you're solving.
    How did you use the tools to understand your dataset?

    Discussion. Think critically about your creation

    What went well?,
    What is still missing? What could be improved?, Why?
One place for obvious improvement is in the Wikipedia scraping. here one could either manually check the spelling of the counties. Or find a tool that can translate uncommon characters into a more Wikipedia friendly format.  for the purpose of showcasing the thoughts of the site it was however deemed sufficient to continue without such labour. 

    Contributions. Who did what?
i did this assignment alone :(
