# Learning Python

These will be my forays into learning Python for data science. I'll track my
projects here with a quick note on what each project does.

##Twitter Counter

This code connects to the Twitter API and searches for tweets based on a
keyword provided by the user. It then gets the text of the tweets and counts
all the words (filtering the most common words like "of" or "the") and prints
a word count for the N most common words in tweets that match the search.
There is also an example of using the Twitter API to look up a users stream
and then search through their tweets to get their most commonly used words.

## TOAES Webscrape/Highlight Words

This code loads a webpage and accesses the paragraph tags or finds the text of the book and then deconstructs that into a series of words
and once again counts the occurences of each word. This was designed to reuse
much of the idea from the Twitter Counter, but apply it to data picked out of
a webpage using the BeautifulSoup Library. It also applies the common word
filter. A major improvement this time was to modularize most of the code so it
can be imported. wordCountMaker.py contains all of the code for making the
html, the image, and manipulating the dictionaries built out of the words.
This can be imported and then the user only needs to provide the text from the
beautiful soup library to the dictionary; since this must be done on a page by
page basis.

The Highlight Words addition takes these word counts and creates a dictionary
from the words found (technically two: one with formatting removed and one
with formatting in tact). It then calculates for each word that number of
times it appears relative to the most common word and assigns a color based on
this frequency compared to the sample's mode. It then creates an HTML file
where each word is colored and placed back in order; the colors are currently
in bins of 10%. So if a word is in the top 10% most common words, it will be
red. If it's in the 10-20% most common words, it will be orange. And so on,
until we get to the words that appear with very little frequency, which are
left as black and unbolded, so that there is a contrast. All words that are in the top 
80% most common words are bolded. This macro also makes a plot of the N most common words 
(N is set in the plot making function as "limit"). This also makes a plot of the words and their counts and places it in the HTML page. The most common words in the King James Version of the Bible available in project Guttenburg is shown below.

![60 Most Common Words in KJV](wordCounter/img/bibleWordCountPlot.png)
