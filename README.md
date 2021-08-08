# Twitter-Data-Wrangling-Project

The data was provided from 3 different sources: 1. Excel Document 2. Web URL 3. Twitter
Extraction for each source varied, as it required its own method for extracting to Pandas Dataframe, which was later be used for analysis and cleaning purposes.

Excel document, twitter-archive-enhanced.csv, was simply extracted by ensuring the document is in the same local as the jupyter notebook and a simple pandas function read_csv was
performed to extract. 
The web url required the use of pythons requests library that allows us to retrieve the html response in JSON format. This information was later saved as .tsv file and was
later extracted in to a pandas dataframe using the read_csv function with delimiter set to identify tabs. Extracting data from Twitter needed an twitter account to be created 
in order to access their API. Once API authentication credential was accesible, the python library for twitters API(tweepy) was used for the ease of extraction.
The extracted file was stored in JSON format and was later extracted using the read_json function.
Most of data gathered from twitter had data that was not required for this project except for the count of favourites and retweets asscociated to the tweet ID, 
as they were meaninful insights. This data was extracted and merged to the main Twitter Archive dataframe later on. The twitter archive dataframe had many quality and tidyness 
issues that was identified in the project, some of the most important ones include:

1. The poor extraction of the dog ratings where both numerator and denominator was not correctly extracted
2. Multiple retweets which is not necessary for this project
3. Poor extraction of dog names resulting false records.

For the image predictions dataframe, the names of the prediction did not follow a proper naming form, with underscores used to seperate words instead of spacings.
Each of these issues was identified through manual review and computational checks. Once they were identifed, both quality and tidyness of each dataframe was tackled to ensure 
they were appropriately cleaned. Once the dataframes were cleaned, they were then merged to one data frame, Twitter Archive Master, based on their tweet id.
