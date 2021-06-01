# Web Scraping 

* For this assignment I built a web application that scraped various websites for data related to the Mission to Mars and displayed the information in a single HTML page. 

## Scraping

Scraped using Jupyter Notebook, BeautifulSoup, Pandas, and Requests/Splinter.

### NASA Mars News

* Scraped the [NASA Mars News Site](https://mars.nasa.gov/news/) and collected the latest News Title and Paragraph Text. 

### JPL Mars Space Images - Featured Image

* Visited the url for JPL Featured Space Image [here](https://www.jpl.nasa.gov/spaceimages/?search=&category=Mars).

* Used splinter to navigate the site and find the image url for the current Featured Mars Image.

* Verified the image url was the full size `.jpg` image.

### Mars Facts

* Visited the Mars Facts webpage [here](https://space-facts.com/mars/) and used Pandas to scrape the table containing facts about the planet including Diameter, Mass, etc.

* Used Pandas to convert the data to a HTML table string.

### Mars Hemispheres

* Visited the USGS Astrogeology site [here](https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars) to obtain high resolution images for each of Mar's hemispheres.

* Saved both the image url string for the full resolution hemisphere image, and the Hemisphere title containing the hemisphere name. Used a Python dictionary to store the data using the keys `img_url` and `title`.

* Appended the dictionary with the image url string and the hemisphere title to a list. This list contained one dictionary for each hemisphere.

## Step 2 - MongoDB and Flask Application

Used MongoDB with Flask templating to create a new HTML page that display all of the information that was scraped from the URLs above.

* Converted the Jupyter notebook into a Python script called `scrape_mars.py` with a function called `scrape` to execute all of my scraped code from above and returned one Python dictionary containing all of the scraped data.

* Next, I created a route called `/scrape` that imported  `scrape_mars.py` script and called my `scrape` function.

  * Then I stored the return value in Mongo as a Python dictionary.

* Next I created a root route `/` that queried the Mongo database and passed the mars data into an HTML template to display the data.

* Finally, I created an template HTML file called `index.html` that took the mars data dictionary and displayed all of the data in the appropriate HTML elements. 

### Copyright

Trilogy Education Services © 2020. All Rights Reserved.
