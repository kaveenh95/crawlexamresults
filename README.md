# crawlexamresults
A scrapy project to scrape exam results of scholarship, ordinary level and advanced level examinations from doenets.lk. Web crawling is executed parallely.


  
For each exam(scholarship,advanced level and ordinary level), 4 scrapy spiders were created.
The index numbers are distributed in these 4 spiders.
Scrapy is created with Twisted, and this framework already has its way of running multiple processes.
So if I try to integrate parallel procesing inside the spiders its incompatible.
Therefore, the 4 seperate spiders were created for each exam and these 4 spiders were executed parallely.
The implementation of the parallel executions for scholarship, advanced level, and ordinary level exams can be seen in crawl_scholarship.py, crawl_advancedlevel.py and crawl_ordinarylevel.py respectively in the directory ./examresults/spiders.

The scraped data are stored in sql databases(grade5.db, advancedlevel.db, ordinarylevel.db) in the directory ./examresults/spiders

To bypass restrictions, user-agents python library was integrated into this project

Steps to scrape exam results
----------------------------

1) Install the requirements in requirements.txt
2) cd into examresults/spiders
3) run scripts, to scrape scholarship : python crawl_scholarship.py
		to scrape advanced level: python crawl_advancedlevel.py
		to scrape ordinary level: python crawl_ordinarylevel.py	
4) Data will be stored in the respective databases(grade5.db/grade5_tb, advancedlevel.db/advancedlevel_tb, ordinarylevel.db/ordinarylevel_tb)




NOTE: Since I executed the code in my own PC, I interrupted the execution after some time beacause my PC started to heat and .
      Data stored upto that executions are stored in the databases.
      ordinarylevel.db is empty because when I interrupted, none of the index numbers were used in the exam(I guess most of the numbers are in 90000000-99999999 range).
