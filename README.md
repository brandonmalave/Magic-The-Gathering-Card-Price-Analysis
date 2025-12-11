# Analysis of Magic: The Gathering card prices

This repository contains data, analytic code, and findings that support my arts and culture based capstone project regarding the proliferation of gambling like profit models in spaces that teenagers and children occupy.

## Data

This analysis uses pricing data scraped from MTGStocks.com API
(MTGstocks gets their pricing data from the tcplayer.com API, a secondary market owned by eBay)

## Methodology

The notebook [`mtg_scraper.ipynb`](notebooks/mtg_scraper.ipynb) performs the following analyses:
Comparing the average percent change in price of a Universes Beyond set since its release, with the average percent change of a set from
before the release of Universes Beyond until the present. Doing so reveals how Hasbro strategy shift in pruchasing licenses for franchises of popular culture like Final Fantasy and Lord of the Rings has introduced a 'fandom premium' to a niche card game. Cards that are printed that depict these icons of popular culture are significantly more expensive, and is the modern version of collectible baseball cards that is capitilzing on the explosion of nerd adjacent culture and their spending habits.

Because more players are drawn to the card game because of these unique collaborations, the prices of cards outside of the realm of these licesned cards are also increasing in price. This is making it difficult for players to keep up with the prices in order to play the game.

##### Part 1: Initial scrape and small scale data analyis

- Before I identified how to dynamically scrape MTGStocks, I used the glob library to scrape the links and card names for every single card by locally saving the html for each page of MTGStocks. This is inefficent, but did what I needed to do, which is build a list of API links for each individual card within a set.
- After building a list of API links, I just scraped the data of the most expensive card from two different sets to confirm my initial hypothesis regarding the price behavior since the release of Universes Beyond. The data frame created revealed that the time format was epoch time, so I also converted that into date-time which proved useful for the data visualization.
- Created a chart using the Matplotlib library for both cards to visualize my findings.

##### Part 2: Dynamically Scraping + Data Visualization

- Card sets are continuing to release, and it would be tiresome to have to locally download html pages for every release. Instead, you can dynamically scrape MTGStocks by plugging in the unique id for a card set into its API. 
- Running a for loop to scrape the market pricing data for every single card in a set, and building a database of pricing data for 500+ cards.
- Visualize the average percent price change for every single card within a set on a line graph.

## Outputs

The notebooks output this spreadsheet which contains a database of pricing data from release to 12/10/2025 for Universes Beyond: Final Fantasy and Ixal: [`output/mtg_price_data_ixal_market.csv`](output/tktktk.csv).

## Running the analysis yourself

You can run the analysis yourself. To do so, you'll need the following installed on your computer:

- Python 3
- The Python libraries specified in the mtg_scraper notebook.

## Licensing

All code in this repository is available under the [MIT License](https://opensource.org/licenses/MIT). The data file in the output/ directory is available under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0) license. All files in the data/ directory are released into the public domain.

## Feedback / Questions?

Contact YOUR NAME HERE at your.name@email.com.
