# An Analysis of Voting Polarization and Power

## Goal
The purpose of this analysis is to explore the county voting polarization and state voting power distribution in U.S. Presidential Elections. I used 3 research questions to do so:

* _Question 1: Can we see a voter polarization? This is, are red areas becoming redder and vice versa._ 
Yes, we were able to see both red and blue counties in american are polarizing and winning Presidential elections with high margins.
  
* _Question 2: Is the proportion of people voting for third parties increasing?_
Simply, no. There is no conclusive pattern in the proportion of third party votes year over year. Rather the spikes indicate votes dissatisfaction in the main two-party candidates. 

* _Question 3: What is there bias in the voting power distribution?_ 
The symmetry of the distribution between red and blue states doesn't indicate a bias in the distribution of voter power. Though is just show the inequity of voting power amongst states.

More data and analysis is necessary to better answer questions 1 and 2. It's important to note that even though our conclusion to question 3 was that there wasn't a bias in the distribution of power amongst red and blue states doesn't mean there is no bias in the electoral college as this was just one way of exploring potential bias.

This analysis was done for the University of Washington's DATA 512 final project. More information about the class can be found [here](https://wiki.communitydata.cc/Human_Centered_Data_Science_(Fall_2018)).

The [Jupyter Notebook](https://github.com/mag3141592/data-512-final-project/blob/master/final_project_analysis.ipynb) will walk you through the full analysis.

## Directory
> data-512-a2/

| Filename | Purpose |
| --- | --- |
| data/... | All source data used in the analysis. |
| iamges/... | All images generated in the analysis. |
| LICENSE | A standard MIT license. |
| README.md | What you're currently reading. |
| final_project_analysis.ipynb | The source code. |
| final_project_plan.md | The intial plan for the analysis. |

## Data Acquistion
Three datasets were used in this analysis.

1. County popular vote data from 2000 - 2016, [here](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/VOQCHQ).

| Column | Datatype | Description |
| --- | --- | --- |
| Year| Integer | Presidential Election year |
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

2. State electoral vote date from 2000 - 2016, [here](https://www.archives.gov/federal-register/electoral-college/votes/2000_2005.html#2016). The data is listed as tables online, so I've aggregated the data into into a more readable format, [here](https://github.com/mag3141592/data-512-final-project/blob/master/data/electoralpres_2000-2016.csv). Additionally I ignored votes for Vice Presidents and reduced specific candidates into their corresponidng parties.

| Column | Datatype | Description |
| --- | --- | --- |
| State | String | State Name |
| Election_Year | Integer | Presidential Election Year|
| State_Electoral_Votes | Integer| Number of State Electors |
| Republican | Integer| Number of Electors Given to Republican Candidate |
| Democrat | Integer| Number of Electors Given to Democratic Candidate |
| Other_1 | Integer| Number of Electors Given to a Third Party Candidate |
| Other_2 | Integer| Number of Electors Given to a Third Party Candidate |
| Other_3 | Integer| Number of Electors Given to a Third Party Candidate |

3. State population data can be found [here](https://www.census.gov/data/tables/2017/demo/popest/state-total.html). This dataset has quite a few columns so the ones relevant to this analysis are:

| Column | Datatype | Description |
| --- | --- | --- |
| State | Integer | Number to define state. State = 0, could mean country or regional population estimates. |
| Name | Sting | State Name|
| Popestimate2016 | Integer| Population estimated from 2010 Census and population growth rates |

## Licensing
The source datasets are not included in this repository due to the following licensing and copyright concerns.
1. County popular vote dataset is licensed under [CC0](https://creativecommons.org/share-your-work/public-domain/cc0/).
2. The state electoral vote dataset is licensed under [Creative Commons CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) license. The licensing is specified in their privacy sections, [here](https://www.archives.gov/global-pages/privacy.html).
3. State population data is from the U.S Census Bureau and has an [open data policy](https://www.census.gov/about/policies/open-gov/open-data.html). 

The code in this repository is licensed under a [MIT](https://opensource.org/licenses/MIT) license.

## Reproducibility
This work is aimed at being reproducible, in order reproduce all figures in the analysis use the source data found [here](https://github.com/mag3141592/data-512-a2/blob/master/data).  It is unlikely historical counts should change, however using the sources provided will reduce effort needed to get the electoral data into the desire format.
