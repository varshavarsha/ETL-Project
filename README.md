# ETL-Project

# Extract

  My project involved acquiring data regarding the top ten fictional Publishers Weekly best sellers for every year from 1895 to 2012. I was able to acquire data for the years 1895-1899 from the Project Gutenberg website, data for the years 1900 to 1999 from the 20th-Century American Bestsellers Database, and data from the years 2000 to 2013 from various Publishers Weekly Articles. I also acquired data for most of the bestsellers by using the Google Books API. Because the data from the 20th-Century American Bestsellers website was formatted in a table like manner, I was able to scrape it using Pandas and transferred the data from 1895 to 1999 and 2000 to 2012 to an excel workbook. 

http://www.gutenberg.org/wiki/Bestsellers%2C_American%2C_1895-1923_%28Bookshelf%29
https://bestsellers.lib.virginia.edu/
https://www.publishersweekly.com/pw/by-topic/industry-news/bookselling/article/74149-publishers-weekly-annual-adult-bestsellers-1990-2013.html
https://developers.google.com/books/

# Transform

  I initially concatenated the data from the 20th century with the older and newer data saved on the excel workbook. Once it was concatenated, I added a new column called “Year” and populated it with values of the years that the books were considered bestsellers. I then created new columns in preparation for loading the Google Books data into the data frame. I created a program that would give me the first Google Books query result given the book title and its author, ideally giving me the best match. 
  
  Once the API data was loaded into the data frame, I was able to compare the “Title” and “Title_Test”  and the “Author” and “Author_Test” columns to see if a mismatched book was loaded onto the data frame. If a book was mismatched, I made a note of the index number of the correct book within the results of the query given the same query information. Using that index information, I was able to replace the incorrect API data with the correct API data. I was also able to find out which books did not have any API data given the same query information. For those books, I cleared the data that was populated in the cells. After cleaning the data and making sure that it is accurate, I dropped the “Title_Test” and “Author_Test” columns. 

# Load

  The final step was taking my Pandas data frame of 1181 rows and exported it to an excel workbook named “Bestsellers_Data”. You will find this in the same repository. 
