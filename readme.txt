Hello!


-- What I have done--
1. I pulled stock tickers for the S&P 500 from wikipedia.com
2. I did an api call for each ticker. The call pulled in two days worth of closing prices and then later calculated biggest gainers and ranked the data set by this.
3. I scraped morningstar.com to get articles directly related to the tod 10 gainers during the period I scraped. 


--Here are some things I would change if I were to do this again--

* I would import the top 20 gainers from a website instead of using the S&P500. This would also fix the fact that I did biggest price change as apposed to the correct value which would have been percentage change. This would eliminate the middle step of having to scrape the stock stats and find the difference and so shorten the program by 2 hours. 

* The formatting on Morning star(where I am getting my articles) is a bit odd so I would write a text cleaning portion into the scrapers for loop.

* I would also import some charts showing how the stock has done over the last year.

* I would add a date to the mongo DB insert section so that I would be building a data base with date info.

* If morning star does not have a article about the company for some reason I would like to pull one from another news source.

* On the api call for ticker prices I did not write out the name of the stocks that had errors and so did not know which of the 505 to drop to get the row lengths to match. I had to drop a random 17 tickers as I did not want to run the 3 hours api call for a 3rd time. 


--Note on the article collection code--
When I was trying to get articles about the top performing stocks I found that the different stock exchanges was a way that morning star seperated out its stocks. This caused me to have to write a try and except block in my articel scraping section. If I were to make this more robust I could do if/elif blocks to check which exchange the ticker was on, I could write many try blocks so that each exchange had it's own block or I could addend the stock exchange info to include which exchange each stock is found on and then it would be down to one block of scraping code without any try blocks. Unless I add a try block simply for error handling. 


--References--
*LIST OF S&P500 companies
    https://en.wikipedia.org/wiki/List_of_S%26P_500_companies
*ticker prices
    polygon.com
*articles
    morningstar.com