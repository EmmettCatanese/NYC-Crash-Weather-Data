# NYC-Crash-Weather-Data
Unfinished data set compiling data from a variety of sources to understand correlations between car accidents, use, and weather in NYC.

**Data Sources**

Motor Vehicle Collisions - Crashes (NYC Open Data)
https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Crashes/h9gi-nx95/about_data

* This was the first set of data I observed. It is detailed, with each row being an individual crash. Including both injuries and fatalities for all groups of people including cyclists and pedestrians. It also includes other things like up to 5 points of fault in each accident and the location. For research purposes, I aggregated the data with a python script to instead sort together each day of data and gather fatalities, injuries and total amounts of accidents for each day. While this limited the ability of complex analysis, the data set would have otherwise been over 2 million rows of data and too complicated for accurate analysis. This data is completely from the NYPD which responds to 911 calls for accidents. This means that the data is largely limited by the man power and cooperation of the NYPD responding to 911 calls. 

Open Parking and Camera Violations (NYC Open Data)
https://data.cityofnewyork.us/City-Government/Open-Parking-and-Camera-Violations/nc67-uf89/about_data

* Many people are likely already familiar with the famous violations data set through the app howsmydriving.nyc. It has both parking violations which are gathered by NYPD parking enforcement as well as moving violations gathered by cameras like red light and school zone. Like the collision data set, each row is its own violation. It includes the person’s plate, as well as a location, date and time as well as other information about the violation payment. I did the same thing I did with the collision data, turning all rows for the same date in to a single row with the number of red light violations that day as well as number of school zone speed camera violations. One problem with the school zone speed camera violations is that until August 1st 2022 they were not recorded on the weekend. This results in incomplete data of beautiful summer weekend days where drivers might be more inclined to speed.

Daily Summaries (NOAA)
https://www.ncei.noaa.gov/cdo-web/search

* I utilized the Daily Summaries data set from the NOAA which contained the max and min temperature each day. The specific weather station I used was in Central Park. II also specifically viewed the maximum temperature because it gives you a better picture of the beauty of the day. Sure the night could be cold however I specifically want to analyze when the weather is beautiful and when drivers might be at their worst. Through the Daily Summaries data set I decided to limit the scope of analysis to July 1st, 2016, 4 years after the start of the accident data, however still somewhat recent.

Daily Traffic on Metropolitan Transportation Authority (MTA) Bridges and Tunnels (NYS Open Data)
https://data.ny.gov/Transportation/Daily-Traffic-on-Metropolitan-Transportation-Autho/cwhc-n4ek/about_data

* This data set includes the drivership of a variety of bridges and tunnels. Each day has two entries, one for the outbound traffic and one for the inbound traffic. I chose to use the Queens - Midtown tunnel because it is a good datapoint of traffic flowing through the city, with both points being within the city. I also combined the outbound and inbound traffic for a single number to go off.

NYPD Calls for Service (Historic) (NYC Open Data)
https://data.cityofnewyork.us/Public-Safety/NYPD-Calls-for-Service-Historic-/d6zx-ckhd/about_data

* A collection of 911 calls. It is collected through the database that 911 operators enter calls into. I believe it is all 911 calls however the wording in the Open Data is vague. Each row is a 911 call and contains a multitude of information including the date, location, time and radio code. I sorted by radio code to only include 53, which is the code for vehicle accidents. Then I added up all of the rows for each day to have a final daily count. 
