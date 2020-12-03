# project-assignment-B
**Project assignment B for Social Graphs**

While this project is about the videogame Crusader Kings 3 (CK3), it is more so a showcase of tools tought in the university course Social Graphs at DTU.
Therefore is must be remembered that tihs project is more of a techinal showcase of tools, then a study in medival politics.
Any additon of political theory is there to give context and spice to the datamanipulation and calculations, and should not be taken as valid facts.
This is espicially true when comparing the language use of modern wikipedia articles, to historical areas of strife and contestation. 
While the method of comparing language use to historical regions may one day be developed into something, this project is not nearly refined wnough to give vaild accounts.

This being said i hope you enjoy the tour.




    Motivation

the dataset from on this website is baed on the table of counties from the following gamewiki https://ck3.paradoxwikis.com/List_of_counties.

the game itself is a game about political intrigue and warfare set in the middelages, and does a good job of emulating the world of its time.
the reason i thought of useing this game as a part of my project is that the former iteration crusader kings 2. had a build in wikipedia buttom allowing for direct acess to the wikipediapage of whatever county or politicla character you selected in game. while this feature was much hated for being messy I.e not working or sending you to the wrong page, i was wondering what i might find if i used my newly learned tools of wikipedia scraping and graphthroy to take a look at the newest itteration of the game.  


As the county is games the point of reference, as to what culture or religion is present it was chosen as primary node type in the graph analysis.
I made and used a Wikipedia scraper to scrape the Wikipedia pages of the 2548 counties in the column called 'County'. an operation that gave me access to 1981 articles. a secondary scrape based on the 'ID' collum, from the same table increased that number to 2051. as some of the ID contained a more appropriate spelling of county names.
overall


    Why did you choose this/these particular dataset(s)?
    What was your goal for the end user's experience?

    Basic stats. Let's understand the dataset better

    Write about your choices in data cleaning and preprocessing
    Write a short section that discusses the dataset stats (here you can recycle the work you did for Project Assignment A)

    Tools, theory and analysis. Describe the process of theory to insight

    Talk about how you've worked with text, including regular expressions, unicode, etc.
    Describe which network science tools and data analysis strategies you've used, how those network science measures work, and why the tools you've chosen are right for the problem you're solving.
    How did you use the tools to understand your dataset?

    Discussion. Think critically about your creation

    What went well?,
    What is still missing? What could be improved?, Why?
One place for obvious improvement is in the Wikipedia scraping. here one could either manually check the spelling of the counties. Or find a tool that can translate uncommon characters into a more Wikipedia friendly format.  for the purpose of showcasing the thoughts of the site it was however deemed sufficient to continue without such labour. 
    Contributions. Who did what?
i did this assignment solo
