# SuperheroU
Data Analysis report 
API → Storage → Cleaning → Dashboard

We started by pulling impression-level data from multiple ad platforms like Google Ads and Facebook Ads. 
I wrote Python scripts to connect to their APIs and schedule daily data pulls into Azure DataLake rawlayer.
For platforms without APIs, I manually downloaded reports and standardized the format using SQL.

Next,
Used Azure Data Factory to ingest raw data from SQL and API sources into Azure Data Lake rawlayer
Then, in Databricks, I used PySpark to further validate schema, removing nulls, duplicates, and standardizing columns like campaign_id, adgroup_id, and timestamps.
once data is cleaned using ADF cleaned data is pushed into Azure Data Lake Cleanlayer

Then in Power BI, I built a dashboard comparing key ad metrics like impressions, CTR, eCPM, and conversions by platform.

One insight stood out: a particular DSP had high impressions but a low CTR (0.4%) and poor ROI.
We flagged this for the marketing team, and pausing it allowed us to reallocate budget, resulting in a 20% boost in ROI and 25% better budget efficiency.
