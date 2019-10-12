# Web Scraping Steps

This is a brief guide for beginners.

[A First Web Scraping Exercise](https://nbviewer.jupyter.org/github/macloo/beginner-notebooks/blob/master/completed/scraping_first_time.ipynb)

## Preliminary

1. Decide what data you need to get. Maybe you can get it without scraping.
2. If you need to scrape, start with one web page to scrape first.
3. Determine whether you are scraping a set of URLs from this page, or other data (such as name, address, and current employer).
4. Make sure your selected page and website are suitable.
5. Make sure you have installed the libraries you will use, such as [Requests](https://requests.kennethreitz.org/en/master/), [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/), and/or [Selenium](https://www.seleniumhq.org/). If you're using a virtual environment, make sure these are available in your env.

## Scrape Basics

1. Set up your Jupyter Notebook or Python (.py) file.
2. Import the libraries you need (such as Beautiful Soup and Requests).
3. Capture the web page contents (e.g. translate its HTML into a variable named `soup` if using Beautiful Soup).
4. To initially explore the page contents, use Developer Tools (e.g. [Chrome Developer Tools](https://developers.google.com/web/tools/chrome-devtools)) and determine which HTML elements hold the data you want to scrape. Note, this step is the same whether you are scraping only URLs or scraping other data, such as names.
5. Run tests with the commands specific to your tool, such as Beautiful Soup's `.find()` and `.find_all()` commands. Test what is retrieved by (initially) printing it. This is a trial-and-error stage.
6. After your tests have shown you how to get all data you want from this page, add the data-storage method of your choice. For example, you can write the scraped data to [a CSV](https://docs.python.org/3/library/csv.html), to [a SQLite database](https://docs.python.org/3/library/sqlite3.html), or to [a plain-text file](https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files) with regular Python commands. This step will likely require a for-loop, as you will be writing sets of values into rows (or records).

## Scraping Multiple Pages

1. If you have perfected how to get the desired data from a single page, and now you want to go to multiple pages that have the same HTML structure to get the same set of data from all those pages, you need a list of URLs.
2. The list of URLs may be stored (in a CSV, in a plain-text file, etc.), or it may exist as a Python list or dictionary generated in your current script.
3. In either case, you need to work out how to loop over the URLs and, one at a time, scrape the page using the code you previously wrote (see "Scrape Basics," above).

It is possible that you will use the steps in "Scrape Basics" twice:

* Once to get the list of all URLs, and
* Once to get data from a page containing details, such as name, address, and current employer.
