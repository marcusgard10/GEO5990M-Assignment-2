# GEO5990M-Assignment-2
The code in this repository is a project that follows the key tenets of data science procedures (see below), in order to uphold its reproducibility and academic integrity. 

<img width="737" height="596" alt="image" src="https://github.com/user-attachments/assets/7e0ba84a-ad25-4597-926d-7ea2afea923a" />


This project aims to explores the relationship between housing prices and incidence of very bad health across Liverpool. To do this average housing prices are used as a proxy for socio-economic status of an LSOA to investigate if there is a relationship towards the incidence of very bad health across the city of Liverpool, UK.

The code is set up ready to first install and importing any relevant packages including geopandas, pandas, matplotlib and seaborn. Next the five relevant datasets are loaded which then undergo a process of data cleaning and exploration. After this an OLS regression model is ran between Average Housing Prices and Very Bad Health variables to investigate their statistical relationship. Finally, two visualisations are presented one non-spatial JointGrid made with Seaborn and a spatial subplot visualisation with Matplotlib.


Background information on incidence of poor health:
Across the 20th century saw the quality of healthcare and life expectancy increase dramatically for all in developed countries, but such a process occurred with distinct inequalities broadly characterised by poorer health outcomes for economically disadvantaged individuals (Feinstein, 1993). Since the 1980s, income inequality in the UK has risen according to the Gini coeffcient (Hassell et al., 2023). Evidence suggests that wealth inequality has risen, to a far greater extent than income, and is continuing to grow (Bourquin et al, 2024). For instance, between 2011 and 2019 Snell (2024) found that the wealth in the UK gap grew by 50%.

Simultaneously, new health challenges are emerging, most notably the rise of morbidity and mortality due to non-communicable diseases (Esquivel and Wharton, 2024). Evidence consistently shows that socioeconomically deprived individuals in England are generally at the greatest risk of developing poor health due to non-communicable disease (Ogunlayi et al., 2023). Furthermore, social-science research into health level and socioeconomic status continually shows links between deprivation and the development of poor health (Burns, 2016). Past health research into childhood obesity in Liverpool revealed stark socio-economic inequalities, characterised by those from the most deprived communities (measured by IMD) having the greatest likelihood of being obese and vulnerable to poor health (Noonan, 2018). Furthermore, Noonan et al (2016) found that children growing up in deprived neighbourhoods were exposed to environments that are unfavourable to creating healthy behaviours. Research has also found evidence that air pollution in Liverpool is unevenly affecting deprived areas of the city with detrimentally health impacts for residents of these areas (Higham et al., 2026). Therefore, a relationship has been demonstrated within Liverpool between incidence of poor health and deprivation. This research seeks to add to this area by testing whether the incidence of self-reported very poor health is linked to housing prices in Liverpool.

Housing prices context:
In the context of rising inequality, house prices have seen a major rise when adjusting for earnings from 3.54x the median income in 1997 to 7.71x in 2024. Research has found that this sharp increases in house prices has exacerbated already prevalent health inequalities, where lower income individuals’ health is being negatively affected while wealthier individuals see health benefits (Grewal, 2024). 
Liverpool has historically had lower house prices than the UK's average ( ). Although, the national increase in housing prices has been affecting prices in the city. Shown by the 6.5% increase in the average house price between Janurary 2025 and 2026 (ONS, 2026).

Past research using property prices as a proxy for socio-economic status by Coffee et al. (2013) showed that cardiovascular health along with obesity rates were lower in those of a higher status. Furthermore, the article highlights the importance of utilising housing prices as a measure of socio-economic status as generally the data is released alot more frequently than other types such as employment, education and income. 

Justifications of data cleaning and manipulation:
Firstly, the house pricing dataset was merged with the lookup file so that the values can be mapped on the newer 2021 LSOAs. This showed if LSOAs were unchanged, split or merged between the 2011-2021 datasets. The house pricing dataset was then cleaned so that a mean value for each LSOA in 2022 could be calculated. LSOAs that had merged between 2011-2021 needed attention as previously existing LSOAs were now one (6 LSOAs were identified as being merged), therefore the mean values of merged LSOAs were added together to harmonise the data. This process of harmonising is the standard procedure to maintain comparability to previous data and allows the data to kept (Ward et al., 2025).

There were two LSOAs (E01006732) and (E01033749 2011 code that merged to E01034404 in 2021) that had no house pricing data for 2022 and were dropped from the dataset. The E01006732 LSOA was also dropped from the health data set to keep consistency between datasets. E01034404 was an LSOA that merged into another LSOA between 2011-2021 meaning no action was taken, as it does not exist as a feature in the health data (which uses 2021 LSOAs). This a downside to my cleaning process as the E01034404 LSOA is only taking data from one of the merged LSOAs as E01033749 was dropped due to no data. This left the dataset with 301 of the 302 2021 LSOAs, with one missing LSOA (E01006732). The health data needed minimal cleaning bar splitting a column. 

Both the house pricing and health datasets were merged with the LSOAs geometry individually. Both datasets were also merged, with no geometry data, to allow for non-spatial visualisation and exploration. The final step was to add a new category in this merged data frame that sorted the LSOAs into by house price quintiles. This was informed by the data exploration stage, as it was clear that the data was unevenly distributed so quintiling the data enabled an even number of points to be contained in each category for analysis.

My results and findings:

OLS regression:
I chose to statistically model the relationship between housing prices and incidence of very bad health by using Ordinary Least Squared (OLS) regression. OLS regression is intended for continuous numeric data types and evaluates the relationship between variables (Ali and Younas, 2021). This fits the two chosen variables. Furthermore, OLS regression is a commonly used statistically modelling approach and is highly interpretable.
R-squared is commonly used to interpret regression models, by assessing the models fit from 0-1 and giving an output (Krieg, 2020). This OLS regression outputted an adjusted R-squared of 0.238. This suggests that that 23.8% of the variation in very bad health (dependent variable) is explained by housing prices. This was a statically significant finding given that the P Value is 0.000. Therefore, the model suggests a reasonably fit given the fact it only contains a singular variable. Although, it is also clear from this model that other factors are important in explaining the proportion of very bad health in LSOAs.

Intepretation of Non-spatial:


Interpretation of Spatial:


Justifications for non-spatial:
I utilised the Jointgrid function within Seaborn to create this visualisation, due to its key functionality allowing the user to include three graphical visualisations into one output. The main output was set to a scatterplot to give the ability to interpret individual data points and allow for visual exploration of the significance of the relationship between variables (Kirk, 2024). This seems appropriate given the relatively small dataset of 301 points (LSOAs) and meant that overcrowding of points, which may make interpretation of scatterplots challenging would not be such a dilemma. Furthermore, the scatterplot in seaborn has the built-in functionality to colouring these individual data points which allows for the house price quintiles to be displayed on the plot. The house pricing variable was split into quintiles to allow for quick interpretation of the key patterns between LSOAs proportion of individuals in very bad health. By doing this, the scatterplot communicates the general pattern that areas with higher house prices have lower proportions of individuals reporting very bad health and vice versa. The marginal plots were set to KDE plots on the side to further inform on the distribution of both datasets and to further illustrate the pattern between house price quintiles.
The colour scheme was carefully selected with colour deficiencies in mind, making the output accessible and interpretable. The colour palette was developed by incorporating recommendations from Phillips (2022). The final scheme utilised a mixture of Paul Tol's muted and Okabe and Ito's colour schemes to give a unique but accessible palette. A sequential colour scheme could have potentially been utilised for this visualisation, but this was tested and it made the output more complex and less interpretable.

 
Justification of the spatial:
Subplots from matplotlib was utilised to allow for both house prices and the prevalence of very bad health to be visualised. Both maps in the spatial visualisation were set to quantile data types to make them easily comparable, with each map having 5 categories. The visualisations were made cleaner and more informative by including many discrete but important items such as north arrows, scale bars, map frames, a background colour, offsetting the legend colour, including data sources.
The sequential blue colour scheme was created bespoke for this output, by utilising the 'Chroma.js' (Chroma.js, n.d.) tool that simulates viewing colour palettes as they would look if you had different types of colour deficiency. The design of this colour palette was made to be accessible and stylish, whilst also illustrating the ordinal type of data presented through a sequential colour palette that conveys the data’s sequence (Rey et al., 2023). This fits the house prices and very bad health proportion being visualised as both are on scales from low-high, whereby the darkest blue represents high house prices and high rates of very bad health. 
To further improve the outputs and to allow for geographical referencing Liverpool’s wards were added.  Although, the labelling of every ward was not included as the map became overcrowded due to the 64 different place names being displayed. Therefore, manually reference points were added instead so that the map still communicates some of the geographical localities across Liverpool. This allows for better and quicker interpretation.
This was done using the website grid reference finder (https://gridreferencefinder.com/) and by hand to find the correct easting and northing points.

The intended audience for both these visualisations is individuals in academia or public policy to encourage further research and policy change in combatting health-based socio-economic inequalities





A limitation of this research is that the health data is procured from Census 2021 data, which was during the COVID-19 pandemic and may impact how people were self-reporting their health status. 
A point of confusion when interpretating the maps may be that both maps have dark blue as showing high values. But high house prices and high proportion of very bad health have different interpretation connotations i.e. high house prices is positive but high proportion of very bad health is negative. 



Datasources:

ONS (2023) Mean house prices by lower layer super output area: HPSSA dataset 47 [Accessed: 13/04/26] Available at:https://www.ons.gov.uk/peoplepopulationandcommunity/housing/datasets/meanpricepaidbylowerlayersuperoutputareahpssadataset47 

ONS (2023b). General health England and Wales: Census 2021 [Accessed: 13/04/26] Available at: https://www.ons.gov.uk/peoplepopulationandcommunity/healthandsocialcare/healthandwellbeing/bulletins/generalhealthenglandandwales/census2021#general-health 

ONS (2024) Lower layer Super Output Areas (December 2021) Boundaries EW BFC (V10) [Accessed: 14/04/26] Available at: https://geoportal.statistics.gov.uk/datasets/ons::lower-layer-super-output-areas-december-2021-boundaries-ew-bfc-v10-2/about 

ONS (2024b) LSOA (2011) to LSOA (2021) to Local Authority District (2022) Exact Fit Lookup for EW (V3) [Online] [Accessed: 17/04/26] Available at: https://geoportal.statistics.gov.uk/datasets/ons::lsoa-2011-to-lsoa-2021-to-local-authority-district-2022-exact-fit-lookup-for-ew-v3/about 


ONS (2025) Boundaries UK BFC Wards (December 2025) [Accessed:14/04/26] Available at:https://geoportal.statistics.gov.uk/datasets/5afda580671b4416a4c338ddb1fe066d_0/explore 


References:
Ali, P. and Younas, A., 2021. Understanding and interpreting regression analysis. Evidence-based nursing, 24(4), pp.116-118.
Bourquin, P., Brewer, M. and Wernham, T., 2024. Trends in income and wealth inequalities. Oxford Open Economics, 3(Supplement_1), pp.i103-i146. DOI:
Burns, L., 2016. Creating a Health/Deprivation Geodemographic Classification System Using K-Means Clustering Methods. London: Sage Publications. DOI: https://doi.org/10.4135/9781473977839
Coffee, N.T., Lockwood, T., Hugo, G., Paquet, C., Howard, N.J. and Daniel, M., 2013. Relative residential property value as a socio-economic status indicator for health research. International journal of health geographics, 12(1), p.22.
Esquivel M. and Wharton G (2024) Acting Early on NCDs: Research and action for digitally-enabled health systems. [Online] [Accessed 14/04/26] Available at: https://www.lse.ac.uk/business/consulting/news/acting-early-on-NCDs
Feinstein, J.S., 1993. The relationship between socioeconomic status and health: a review of the literature. The Milbank Quarterly, pp.279-322.
Hassell, J., Rohenkohl, B., Arriagada, P. Ortiz-Ospina E. and Roser M. (2023) Economic Inequality. Our World in Data. [Online] [Accesed: 17/04/26] Available at: https://ourworldindata.org/economic-inequality .

Higham, J.E., Sinha, I.P., Olajide, O., Saleh, S., Lee, A.R. and Holden, K., 2026. Air pollution and deprivation: a double burden on Liverpool’s children. Archives of Disease in Childhood.

Grewal, A., Hepburn, K.J., Lear, S.A., Adshade, M. and Card, K.G., 2024. The impact of housing prices on residents’ health: a systematic review. BMC Public Health, 24(1), p.931.

Krieg, E.J. 2020. Statistics and data analysis for social science : for social science Second edition. Los Angeles, CA: SAGE Publications, Inc.

Noonan, R.J., Boddy, L.M., Knowles, Z.R. and Fairclough, S.J., 2016. Cross-sectional associations between high-deprivation home and neighbourhood environments, and health-related variables among Liverpool children. BMJ open, 6(1), p.e008693.

Noonan, R.J., 2018. Prevalence of childhood overweight and obesity in Liverpool between 2006 and 2012: evidence of widening socioeconomic inequalities. International Journal of Environmental Research and Public Health, 15(12), p.2612.

ONS, 2026. Housing prices in Liverpool. [Online]. [Accessed 14 April 2026]. Available from: https://www.ons.gov.uk/visualisations/housingpriceslocal/E08000012/#house_price

Ogunlayi, F., Coleman, P.C., Fat, L.N., Mindell, J.S. and Oyebode, O., 2023. Trends in socioeconomic inequalities in behavioural non-communicable disease risk factors: analysis of repeated cross-sectional health surveys in England between 2003 and 2019. BMC Public Health, 23(1), p.1442.

Snell, W. (2024) The UK’s wealth gap has grown by 50% in eight years – and poses a strategic risk to the nation. LSE Inequalities [Online] [Accessed: 17/04/26] Available at: https://blogs.lse.ac.uk/inequalities/2024/10/29/the-uks-wealth-gap-has-grown-by-50-in-eight-years/ 

Ward, C., Singleton, A., Robinson, C. and Rowe, F., 2025. Tracking spatio-temporal energy vulnerability: A composite indicator for England and Wales. Regional Studies, Regional Science, 12(1), pp.319-337.




