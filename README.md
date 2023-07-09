# Lede 2023 Project 02
Comparing the size of the Top 10 Anime/Manga fandoms on `fanfiction.net` and `archiveofourown.org` and looking at fanfiction.net's decline through the Madoka Magica Fandom

# Data sources
1. [Fanfiction.net - All Anime/Manga](https://www.fanfiction.net/anime/)
2. [Fanfiction.net - Madoka Magica](https://www.fanfiction.net/anime/Puella-Magi-Madoka-Magica-%E9%AD%94%E6%B3%95%E5%B0%91%E5%A5%B3%E3%81%BE%E3%81%A9%E3%81%8B-%E3%83%9E%E3%82%AE%E3%82%AB/)
3. [Archive of our own - All Anime/Manga](https://archiveofourown.org/media/Anime%20*a*%20Manga/fandoms)
4. [Archive of our own - Madoka Magica](https://archiveofourown.org/tags/Mahou%20Shoujo%20Madoka%20Magika%20%7C%20Puella%20Magi%20Madoka%20Magica/works?page=1)

# Analysis
- Fanfiction.net I used `Selenium`
- AO3.org I used `BeautifulSoup`
I had to enter the year_released manually since matching from the `animes.csv` file was too difficult (case sensitive, random character extra). 
I chose a smaller fandom (under 5k fics total) to make scraping faster and released around 2011-2012 to analyse the effect of the content purge. 

# Repository contents
1. `data` folder contains:
- cleaned csvs and xlsx of the contents scraped from the 2 websites.
2. the `notebooks` folder contains 2 notebooks
- `fanfictions.ipynb` contains the data the top 10 fandoms on both sites and the Madoka Magica data on ffnet
- `madoka_ao3_fics.ipynb` contains data for Madoka Magica on AO3 only. I split the files to test the code
3. the `docs` folder contains:
- contents for website include PNG I exported and cleaned using Figma2HTML

# Findings
1. `fanfiction.net` being an older site than ao3 has is more likely to have a large amount of fics from works released in the 90s and early 2000s. At its peak, the biggest ff.net fandom is bigger than the biggest ao3 fandom 
2. `archiveofourown` is now the de-facto site to read fanfiction, especially for works released within the past decade
3. looking at the Madoka Magica fandom showed that ff.net declined slowly, over about 4 years after the content purge 

# Data collection and analysis process
Steps of the data analysis process:
1. Use `Selenium` to load ff.net page dynamically 
split and substring to create dataframe
2. Use `BeautifulSoup` to load ao3.org page, used an [unofficial ao3 API](https://pypi.org/project/ao3-api/) to get publication dates but could not so I used updated dates instead 
- This is not a like-for-like comparison because I used `updated date` for AO3 and `published date` for ffnet because the API to get published date wasn't working. 
- Even the API worked as expected, ao3 allows users to edit/backdate the publish date so it would never be accurate compared to the non-editable date on ffnet


# Skills and learnings
1. Css selector and looking at the attribute of each element for ao3
2. Selenium using find xpath for ffnet

