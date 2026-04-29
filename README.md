# GEO5990M-Assignment-2
The code in this repository is a project that follows the key tenets of data science procedures (see below), in order to uphold its reproducibility and academic integrity. 

This project aims to explores the relationship between housing prices and incidence of very bad health across Liverpool. To do this average housing prices are used as a proxy for socio-economic status of an LSOA to investigate if there is a relationship towards the incidence of very bad health across the city of Liverpool, UK.

The code is set up ready to first install and importing any relevant packages including geopandas, pandas, matplotlib and seaborn. Next the five relevant datasets are loaded which then undergo a process of data cleaning and exploration. After this an OLS regression model is ran between Average Housing Prices and Very Bad Health variables to investigate their statistical relationship. Finally, two visualisations are presented one non-spatial JointGrid made with Seaborn and a spatial subplot visualisation with Matplotlib. 
# Datasource table 
<img width="737" height="596" alt="image" src="https://github.com/user-attachments/assets/7e0ba84a-ad25-4597-926d-7ea2afea923a" />

For transparency and reproducibility purposes a table on all the data sources is shown above. All the data for this project is avaiable at a national level for England and Wales meaning that more reasearch could follow a similar approach as undertaken in this project but with a focus on another city or geographic area.

# Background information on incidence of poor health:
Across the 20th century saw the quality of healthcare and life expectancy increase dramatically for all in developed countries, but such a process occurred with distinct inequalities broadly characterised by poorer health outcomes for economically disadvantaged individuals (Feinstein, 1993). Since the 1980s, income inequality in the UK has risen according to the Gini coeffcient (Hassell et al., 2023). Evidence suggests that wealth inequality has risen, to a far greater extent than income, and is continuing to grow (Bourquin et al, 2024). For instance, between 2011 and 2019 Snell (2024) found that the wealth in the UK gap grew by 50%.

Simultaneously, new health challenges are emerging, most notably the rise of morbidity and mortality due to non-communicable diseases (Esquivel and Wharton, 2024). Evidence consistently shows that socioeconomically deprived individuals in England are generally at the greatest risk of developing poor health due to non-communicable disease (Ogunlayi et al., 2023). Furthermore, social-science research into health level and socioeconomic status continually shows links between deprivation and the development of poor health (Burns, 2016). Past health research into childhood obesity in Liverpool revealed stark socio-economic inequalities, characterised by those from the most deprived communities (measured by IMD) having the greatest likelihood of being obese and vulnerable to poor health (Noonan, 2018). Furthermore, Noonan et al (2016) found that children growing up in deprived neighbourhoods were exposed to environments that are unfavourable to creating healthy behaviours. Research has also found evidence that air pollution in Liverpool is unevenly affecting deprived areas of the city with detrimentally health impacts for residents of these areas (Higham et al., 2026). Therefore, a relationship has been demonstrated within Liverpool between incidence of poor health and deprivation. This research seeks to add to this area by testing whether the incidence of self-reported very poor health is linked to housing prices in Liverpool.

# Housing prices context:
In the context of rising inequality, house prices have seen a major rise when adjusting for earnings from 3.54x the median income in 1997 to 7.71x in 2024. Research has found that this sharp increases in house prices has exacerbated already prevalent health inequalities, where lower income individuals’ health is being negatively affected while wealthier individuals see health benefits (Grewal, 2024). 
Liverpool has historically had lower house prices than the UK's average ( ). Although, the national increase in housing prices has been affecting prices in the city. Shown by the 6.5% increase in the average house price between Janurary 2025 and 2026 (ONS, 2026).

Past research using property prices as a proxy for socio-economic status by Coffee et al. (2013) showed that cardiovascular health along with obesity rates were lower in those of a higher status. Furthermore, the article highlights the importance of utilising housing prices as a measure of socio-economic status as generally the data is released alot more frequently than other types such as employment, education and income. 

A limitation of this research is that the health data is procured from Census 2021 data, which was during the COVID-19 pandemic and may impact how people were self-reporting their health status. 
A point of confusion when interpretating the maps may be that both maps have dark blue as showing high values. But high house prices and high proportion of very bad health have different interpretation connotations i.e. high house prices is positive but high proportion of very bad health is negative. 



# Datasources:

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




