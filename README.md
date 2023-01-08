# Energy Consumption in Berlin districts between 2018-2019
This project aims to determine whether there has been a change in heat consumption and power consumption for government buildings between the years 2018, 2019, 2020. Conducted an Anova Hypothesis Test for both heat and power to consumption whether such change took place. 
Here is my Tableau link for my presentation: https://public.tableau.com/app/profile/maxime.favreau/viz/MidtermProject_16729345172430/References?publish=yes

## Motivation
Decided to further enquire on this topic as when the Covid-19 pandemic hit us in 2020, most of us were forced to confine and work in our homes. Which ultimately let to an increase in prices for heat, power, water, and even internet. Schools, museums, and stadiums were closed for several months until late 2020, which let me to wonder whether these government buildings' consumption had been affected, as much as the general population's definitely was. 

## Build Status
The code for this Jupyter Notebook is divided into parts: 
  - __Data Cleaning:__ Divided in districts and years
  - __Analysis:__ Divided by binning the data into different categories, and Anova Hypothesis testing
  - Most of the code is repeated

## Code Style
Used both the Python 3 code style and SQL in my Jupyter Notebook.

## Screenhots
![Screen Shot 2023-01-08 at 2 36 20 PM](https://user-images.githubusercontent.com/117981133/211199008-d885637b-df64-4df7-b2c2-fd40240807be.png)
![Screen Shot 2023-01-08 at 2 36 05 PM](https://user-images.githubusercontent.com/117981133/211199014-9e95c7cf-df5b-428b-90dd-e796f0dccbbe.png)
![Screen Shot 2023-01-08 at 2 35 44 PM](https://user-images.githubusercontent.com/117981133/211199056-3760bf23-bec9-4cb9-b229-8b0504970712.png)

## Tech/Framework used
I used Python, SQL and ran the following librairies to help execute the code:
- import pandas as pd
- import matplotlib.pyplot as plt
- import seaborn as sns 
- import numpy as np
- import pymysql
- from sqlalchemy import create_engine
- from sqlalchemy import MetaData
- import pandas as pd

## Features
Feature that I would consider that stands out is running the Anova Hypothesis test in the Notebook. I also ran a long function to categorize the building types into separated bins. 

## Code Examples
_"p2018['heat_supply']= p2018['heat_supply'].fillna('Gas')"_
- This code helps fill all NaN values in a specific column in the database to 'Gas'.

_"z2019.drop(index=z2019.index[:3], 
        axis=0, 
        inplace=True)"_
- This code drops the first 3 rows in a dataset.

## Installation
I needed to install sqlalchemy from Anaconda-Navigator to run the SQL schema for this project. Otherwise the softwares Jupyter Notebook and MySQL Workbench were already installed on my computer. 
In Anaconda-Navigator you can find SQLalchemy in the "_Environment_" tab(on the left hand side, below "_Home_"), and either search for "_SQLalchemy_" or filter for "_Not Installed_".

## API reference
Didn't use an API reference for this project as it was not required. 

## Tests
Conducted an Anova Hypothesis Test to test whether the following is true:
- __Null Hypothesis (H0):__ In the years 2018 , 2019, 2020 facility types in Berlin districts consume the same amount of heat/electricity.
- __Alternative Hypothesis (H1):__ In the years 2018, 2019, 2020 facility types in Berlin districts consume different amounts of heat/electricity.

- Here is an example of the code:

- *_from scipy.stats import stats*_

- *_f_value_p, p_value_p =   stats.f_oneway*_(lsc_2018,lot_2018,lpl_2018,lsp_2018,lku_2018,lde_2018,lbu_2018,lwo_2018,lsc_2019,lot_2019,lpl_2019,lsp_2019,lku_2019,lbu_2019,lwo_2019,lsc_2020,lot_2020,lpl_2020,lsp_2020,lku_2020,lde_2020,lbu_2020,lwo_2020,psc_2018,pot_2018,ppl_2018,psp_2018,pku_2018,pde_2018,psc_2019,pot_2019,ppl_2019,psp_2019,pku_2019,pde_2019,psc_2020,pot_2020,ppl_2020,psp_2020,pku_2020,pde_2020,msc_2018,mot_2018,mpl_2018,msp_2018,mku_2018,mde_2018,mbu_2018,mwo_2018,msc_2019,mot_2019,mpl_2019,msp_2019,mku_2019,mde_2019,mbu_2019,mwo_2019,msc_2020,mot_2020,mpl_2020,msp_2020,mku_2020,mde_2020,mbu_2020,mwo_2020,zsc_2018,zot_2018,zpl_2018,zsp_2018,zku_2018,zde_2018,zbu_2018,zwo_2018,zsc_2019,zot_2019,zpl_2019,zsp_2019,zku_2019,zde_2019,zbu_2019,zwo_2019,zsc_2020,zot_2020,zpl_2020,zsp_2020,zku_2020,zde_2020,zbu_2020,zwo_2020,tsc_2018,tot_2018,tpl_2018,tsp_2018,tku_2018,tde_2018,tsc_2019,tot_2019,tpl_2019,tsp_2019,tku_2019,tde_2019,tsc_2020,tot_2020,tpl_2020,tsp_2020,tku_2020,tde_2020)

*_print(f_value_p, p_value_p)*_

- __P-value for heat:__ 0.12001258160006334
- __P-value for electricity/power:__ 0.10143594256638956
- __Results:__ We failed to reject the null hypothesis

## How to use?
I would recommend first reading the _"Readme"_ before opening the .ipynb file. When going through the latter file, it is apparent to see how and why I decided to keep and delete certain values when cleaning the data. Upon the analysis, I further bin/categorized the data to make it ease of use and to simplify the interpretenation on the different values of the code and _facility type_. Towards the end of the document, the reader will reach the _Anova Hypothesis Test_ and ultimately the result. 

## Contribute
You can contribute by opening the _"Readme"_ file, clicking on _"Edit"_ and leaving a comment at the bottom of the document with your github link and suggested comments. 
Here is my github repository link: https://github.com/mmmaxime?tab=repositories

## Credits
I used the following website for datasets:
- https://www.berlin.de/suche/?site=full&q=Energieverbrauchs%C3%BCbersicht
- https://www.berlin.de/ba-mitte/ueber-den-bezirk/zahlen-und-fakten/energieverbrauch-bezirklicher-gebaeude/
- https://www.berlin.de/ba-pankow/suche.php?q=Energieverbrauch+bezirklicher+Geb%C3%A4ude
- https://www.berlin.de/ba-steglitz-zehlendorf/
- https://www.berlin.de/ba-treptow-koepenick/politik-und-verwaltung/service-und-organisationseinheiten/facility-management/energieverbrauchsuebersicht-bezirklicher-gebaeude-769059.php

## License
Used Python 3 License. 
