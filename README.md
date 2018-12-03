# Pres-Proj

Group 35 -- Section 2


## A description of what has been implemented:
# Objective:

Sentiment of presidential speeches and their effect on major American stock market indices


- Scrap data from a website to populate a dataframe with presidents, their respective parties, presidential speeches and their respective dates
- Do sentiment analysis on each speech and include the scores in the dataframe
- Merge this dataframe with a separate dataframe of dates and daily %Change in stock market indices
- Analyse the dataframe for correlation and significance 


### Installation instructions 

Python packages are listed appropriately in requirements.txt

### Run instructions

We have 3 files main files which will run the whole analysis

1.- Final Data Acquisition.ipynb: When running this file, the libraries will be imported
                                  then, you will be able to run the next cell, which will
				  open an internet browser(Preferably Google Chrome) which
				  will run a minute or so, please don't interrupt this process.
				  A good internet connection is required. Finally, you will be 
                                  able to run the rest of the code in this file freely, waiting
				  until it finish the process. This file will create a pickle with
				  the dates, speeches and president data.
				  

2.- Final Sentiment Analysis.ipynb: You can run this file freely but this file will take some processing
				    time. The purpose of this file is to tokenize and analyze the speeches
				    adding 3 columns to the data created previously.

3.- Final Data Merge.ipynb: As the second file you can just run the jupyter notebook, it will grab the
			    data from the financial csv files (which need to be on the same folder) and
			    merge the financial dataframe with the one created in the second file. 
			    

4.- Regression.ipynb: Run this file and the output will be a regression analysis over the financial data
		     and the compound from the sentiment analysis file.

5.-Word Cloud Analysis, Party Stripplot: This files should be run in the end of the process. they
					 only generate png images. 
## Difficulties

We wanted to add this additional part to describe some of the issues we faced and how we worked through or around them. I hope this section
could clarify few of the decisions we had to make during coding.

### Data scraping

The website we use to gather our data about the presidential speeches is "https://millercenter.org/the-presidency/presidential-speeches"
It is a website with a nice UI and we considered it to be easy to work with initially. It has the Infinite Scroll feature which seems to be getting more common. While this feature did look difficult to work with we thought it would be a fair and a realistic challenge. 

Selection of presidents lead to an issue where the website would not filter more than three presidents. So we were not able to use the websites select president feature. Instead we had to scrap all the data and than filter the portion we wanted to use. 
For certain speeches context of the website would change which lead us to add an additional for loop for those exceptions.
There are also frequent typos in the speech transcripts. Unfortunately these typos include the dates. For example there was an entry of the 21st president, Chester A. Arthur(1829-1886) giving a speech on December 6th 1981. 

### Merging with Financial data

One issue we faced combining the data was due to dates. Presidential speeches can happen any day however the major American stock market indices we were looking at, do not have entries over weekends and holidays. To work around this we first decided to connect a speech to the closes working day. A speech that took place on saturday would be matched with the following monday stock market index %change. However this led to further issues in few exceptions where we had multiple speeches over a holiday period as two speeches ended up being assigned the same dates %change. We decided to ignore the speeches that took place on dates that do not match a major American stock market indices entry.













