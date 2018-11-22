
A4: Final Project Plan <br/>
Margaret Stark <br/>
11/22/208 <br/>

## Presidential Election Voting Tendencies (Center)

### Background

#### Why I am planning to do this analysis?
Each election I see county voting statistics on turnout and county breakdowns.  I have not seen how or if county political voting patterns are changing.  Here, I will try to find geo-political trends in the US presidential elections since the 2000.  I hope to see how county, state, regional political leanings have changed and then to try an identify historical event that may have influenced that change (i.e. southern border counties being influenced by immigration or large population growth from a tech boom or a rise in unemployment). <br/>
Every four years the same conversations take place about swing states and turnout.
> “It’s not simply a handful of swing states that will decide the 2016 presidential election. The swing voters in the swing counties of the swing states will decide it. And if my calculations are correct, it is perhaps no more than 19 counties in 11 states…” - [David Schultz](https://www.minnpost.com/community-voices/2016/08/how-just-few-voters-few-us-counties-will-decide-presidential-election/) <br/>
For this reason, I hope to measure the weight of a vote in a state.   The datasets cover presidential elections from 2000 – 2016, during which electoral votes have been redistributed by population changes.  I would be interested in exploring how the weight of certain regions votes have changed.  In all but 2 states our electoral votes are awarded on a winner takes all system, so I’ll be comparing the number of votes per candidate in a state with the electoral result in order to measure weight.  The distribution of the weights will be a view into the fairness of the electoral vote distribution.

#### Why it is important?
While it is true that every voice is not equal in a presidential election it is important to understand preciesely how they differ in order to effectively communicate the information.  Another issue is voter turnout, and while I won’t explore the mechanic of this directly it is impacted by voters not feeling empowered and that their voice matters because not every vote is equal.  By continuing with the current system without trying to engage and change it, we continue to give more power to a few.  This sort of analysis is important for public understanding of the elections.  Things we don’t understand, we can't fight to change.
**** Human-centered design considerations?
I’ve chosen this analysis because it has many human-centered components, from the subject matter to the presentation.  The more transparency the public has on political elections the more informed voters we can become.  The results those votes have impacts on humans worldwide. 
*** Project Plan
**** Research Questions
1.	Political trends by county and state?
•	Which counties had the largest change in political leaning? Biggest red shift? Biggest blue shift? 
•	Are red and blue areas becoming more polarized (i.e. are liberal areas becoming more liberal and vise versa)? Are swing states remaining noisy?
•	How have southern border counties leanings changed from immigration and the talks of it?
2.	Is voting for third party candidates in presidential elections increasing?
3.	What impact, if any, does county unemployment rates have on political leanings?
4.	What is the weight of a vote by region?
**** Expected Results
While I have specific research questions, most of my analysis will be exploratory. I do expect rural regions to have higher voter weights and to be more red
*** Data Sources and Analysis
**** Data Sources
***** Electoral Votes
This data (https://www.archives.gov/federal-register/electoral-college/votes/2000_2005.html#2016) was retrieved from the National Archives and Records Administration and is licensed under Creative Commons CC0 1.0 Universal license https://creativecommons.org/publicdomain/zero/1.0/.  The licensing is specified in their privacy sections, here (https://www.archives.gov/global-pages/privacy.html). In order to use this data, I will need to aggregate it into a more useable format, as there is an election dataset per election with different columns based on the candidates. I will compile the final dataset and post it to my repository for easy reproducibility.
I’ll be focusing on 2000 – 2016 as that is the date range of the popular vote dataset.  
| Column | Datatype | Description |
| --- | --- | .--- |
| State| String | State Name|
| Electoral Vote of each State| Integer | Number Electoral Votes Available |
| For President - Republican | Integer | Number of Electoral Votes Won |
| For President - Democrat | Integer | Number of Electoral Votes Won |
| For President - Other | Integer | Number of Electoral Votes Won |
| For Vice President - Candidate 1 | Integer | Number of Electoral Votes Won |
| For Vice President - Candidate 2 | Integer | Number of Electoral Votes Won |
In the raw data, the last 5 are actual candidate names.  When I merge the datasets, I will be reducing them down to Republican, Democrat, and other.
***** Popular Votes
This data (https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/VOQCHQ) was retrieved from Harvard Dataverse and is licensed under CC0 (https://creativecommons.org/share-your-work/public-domain/cc0/).
| Column | Datatype | Description |
| --- | --- | .--- |
| Year| Integer | Presidential Election year|
| State | String | State Name |
| State_PO | String | State Abbreviation |
| County | String | County Name |
| FIPS | Integer | Federal Information Processing Standard Code (Unique to County) |
| Office | String | Office Election Counts are for (President in this dataset) |
| Candidate | String | Candidate Name |
| Party | String | Political Party Candidate is Affiliated with|
| Candidatevotes | Integer | Number of Vote the Candidate Received |
| Totalvotes | Integer | Total Votes in County Election |
| Version | Integer | Dataset Version Number |
***** Unemployment Rates
This data (https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/P8ZJAG) was retrieved from Harvard Dataverse and is licensed under CC0 (https://creativecommons.org/share-your-work/public-domain/cc0/).
| Column | Datatype | Description |
| --- | --- | .--- |
| Year| Integer | Calendar Year |
| Period | String | String M1 – M12 Representing Month of Year |
| PeriodName | String | Month Name |
| Value | Decimal | Unemployment Rate Percentage|
| SeriesID | String | Another String Unique to County |
| FIPS | Integer | Federal Information Processing Standard Code (Unique to County) |
| County| String | County Name |
| State | String | State Abbreviation |
**** Potential Limitations
•	The county naming in the popular vote dataset and the unemployment rate dataset is different but I should be able to join based on the FIPS.  I will have to test joining these.  If joining is too noisy, I will consider removing the unemployment rate analysis from this project.
**** Analysis
Most of my research questions can be answered by classical statistics.  I will try clustering the county vote count data to see the distribution of political lean, to see where they are highly focused versus more dispersed. 
*** References
1. https://www.minnpost.com/community-voices/2016/08/how-just-few-voters-few-us-counties-will-decide-presidential-election/
2. https://creativecommons.org/publicdomain/zero/1.0/
3. https://www.archives.gov/global-pages/privacy.html
4. https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/VOQCHQ
5. https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/P8ZJAG
