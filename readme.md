# Anime analysis

This is repo for analysing anime from big anime databases.
The main datasource will be MyAnimeList (MAL), and maybe later some others.

Anime sources:
- There is official API for MAL
    - docs: https://myanimelist.net/modules.php?go=api

- and then there is unofficial one which provides more information
    - release post and docs: https://myanimelist.net/forum/?topicid=1616529
    - apiary docs: https://jikan.docs.apiary.io/
    
- Taiga - desktop app which stores anime data offline in xml file
    - main info here: https://myanimelist.net/clubs.php?cid=21400
    - here is thread wilh xml data https://myanimelist.net/forum/?topicid=1358410

- there is one unofficial API https://classes.soe.ucsc.edu/cmps161/Winter12/proposals/bbtran/proposal/malunofficialapi.html#read_anime_list
    - but it is not working
    
- there is kaggle CSV dataset 
    - https://www.kaggle.com/CooperUnion/anime-recommendations-database
    - scripts for datamining from MAL https://www.kaggle.com/CooperUnion/anime-recommendations-database/discussion/47500
        - the github repo: https://github.com/Dibakarroy1997/myanimelist-data-set-creator

- other kaggle dataset
    - https://www.kaggle.com/canggih/anime-data-score-staff-synopsis-and-genre
        - but probably not much useful, probably as inspiration
        
User sources:
As the first source, I am using the Dibakarroy1997/myanimelist-data-set-creator repo, for that I need user IDs.
So I need user ids (ideally active users) for scrapping ratings per user.
So far I am scraping forum topics to get user ids:

command for scrapping with sample id: `python .\createUserListFromPost.py 1582476 user-lists/UserListPost1582476.txt`
Topics scraped so far:
- https://myanimelist.net/forum/?topicid=1582476
- https://myanimelist.net/forum/?topicid=1696289
- https://myanimelist.net/forum/?topicid=1469513
- https://myanimelist.net/forum/?topicid=1469515


Previous analyses - for baseline:
very basic, but good for very first data scraping validity - https://graph.anime.plus/s/globals
seems nice, yet simple - https://aquabluesweater.wordpress.com/2010/03/06/compilation-of-top-anime-of-the-decade-lists-around-the-internet-series/
totally offtopic, yet interesting - http://aja.gr.jp/english/japan-anime-data
nice temporal analysis, only for moe - https://aquabluesweater.wordpress.com/2010/12/31/genre-over-time-moe/
nice SAO analysis and score analysis per score - https://www.datasciencecentral.com/profiles/blogs/anime-reviews-and-scores
    - source code: https://github.com/nycdatasci/bootcamp007_project/tree/master/Project3-WebScraping/YisongTao
recommendation of anime based on kaggle dataset: https://www.slideshare.net/imcinstitute/anime-recommendation-big-data-certification6
other recommendation based on same dataset: https://medium.com/learning-machine-learning/recommending-animes-using-nearest-neighbors-61320a1a5934
anime gender preferences reddit post: https://www.reddit.com/r/anime/comments/6w60ru/gender_differences_in_anime_preferences/
anime gender preferences tables: https://www.reddit.com/r/anime/comments/6w60ru/gender_differences_in_anime_preferences/dm5rzdz/


nápady:
- zjistit velké rozdíly v hodnocení anime, s velkým rozptylem, kde je hodnotí hodně lidí velmi kladně a hodně lidí velmi záprně
- podívat se na rozdíly mezi hodnoceními v čase
- rozdíl mezi lidmi co hodnotili málo a co hodnotili hodně anime, co viděli a co hodnotili za díla
- korlace score, žánrů, sledovanosti, a času, a lidí, co sledují hodně, málo
- rozclusterovat lidi na málohodnotící, a hodně hodnotící, podle střední hodnoty hodnocení apod.