# COVID Visualization fbProphet 
 This model visualizes COVID-19 Trends at various levels using FbProphet and predicts trends up to 30 days  
 Note: Only outputs are shown in the final model. Source code is in individual directories :-)   
## PURPOSE  
The purpose of this project is ambitious but simple: to use machine learning libraries to predict future COVID-19 trends at the county-level. In order to do this accurately, the project utilizes multiple datasets from a central source, The New York Times. These datasets are utilized to visualize macro and micro level trends, which are then run through ML models to predict future cases.  

## MODELS  
When analyzing retroactive data to predict future trends, a ML model with strong autoregressive capabilities would be the most capable.
Given this, the project incorporates Facebook’s Prophet library, which utilizes autoregressive modeling in time series forecasts
To ensure the accuracy of these forecasts, the scikit-learn library’s sklearn metrics are utilized. 
Visuals are constructed from matplotlib using data from NYT GitHub CSV’s 
CSVs are read by pandas into dataframes and converted for plotting and metrics with NumPy  

## FINDINGS  
The project found that the country with the most cases is USA,  with the states with most cases being CA, TX, Fl, NY, and IL. 
The counties with most cases are LA, NYC, Maricopa, Cook, and Miami-Dade. 
Within these counties the model was able to predict future trends with R2 scores ranging from 0.97-0.999. 
Mask data is used as a potential factor as well

## CONCLUSIONS  
The United States beats all countries in terms of cases
Densely populated counties will have the most cases by far
COVID-19 patterns follow a regressive trend in the populated counties
Mask use bears no real statistical significance when plotted 
  
## OVERVIEW:  
 The world is now over a year into the COVID-19 pandemic. Despite vaccinations being available in many countries for almost half a year now, cases continue to grow all around with no solid end in sight. Countries that underestimate future cases often pay a fatal price, creating an unprecedented global problem. How can a country predict a rise in cases before they happen?  
	Well, what if data science could be used to lend insight into this problem? All COVID-19 data is openly accessible, with real-time CSVs posted on GitHub by The New York Times every morning. As a data scientist, the thought of seeing such data in a CSV is already a reassuring feeling. Using the power of pandas, these CSVs can be shaped and perfected into polished dataframes.  
	These dataframes alone don’t show much, until NumPy is utilized to mold the data into the suitable parameters needed for visualization. Matplotlib has powerful plotting tools to bring these plain looking dataframes to life, creating interactive figures that dynamically adapt to new data. In order to be truest to the results, we go from the global level down to the county level. This is done since all macro-level changes are influenced by the aggregate of micro-level changes. By analyzing these tiny but impactful trends, data science can be used to detect and predict cases going up or down relatively early.  
	Using the power of autoregressive modeling, Prophet’s library forecasts predictions for any time series data set that it is properly fed. Since it would be redundant to forecast and display every county in the United States, only the top 5 cases will be analyzed in this project. The proper metrics from Sklearn will be tested on each model to see if they are statistically significant.  
	Using data from county level mask data, we can test to see if there is a statistical significance between cases. If there is, it could be incorporated as a confounding variable. Analyses will then determine how accurate the model is, and if there is a way to correlate mask use with cases.  
	The end goal is a model capable of predicting the trends of COVID cases in a county for 30 days at least, without losing statistical significance.  
 
##  METHODS:  
The methods focus on cleaning, reshaping, plotting, and predicting the data:  
- Cleaning: pandas commands are used to convert CSVs into dataframes  
- Reshaping: NumPy is mainly used to properly get values in the right formats  
- Plotting: Plotting data mainly utilizes matplotlib, with plotly elements for interaction  
Predicting: The Prophet library is the primary tool for ML in this project  
- Fitted Models and forecasted models are visualized  
- Metrics: Sklearn metrics on each forecast as a final test of accuracy, as well as gauging hypothesis  
- Analysis: An objective analysis of the results, and what can be understood from them  

## ANALYSIS:  
When analyzing the data, unsurprisingly, USA was the country with the most cases across the world. This made it easy to find datasets that were trustworthy, such as the NY times dataset. As we analzye the state-level data, we see the expected states appear in the top 10: CA, TX, FL, NY, IL, PA, OH, NJ, NC.  
  However, these are big states, so finding the specific counties in them with these numbers would probably be of more use. When doing that, I looked for counties above 500k people, a metric I believe is ideal for a good population mix. The counties in these criteria were Los Angeles County, New York County, Maricopa County, Cook County, and Miami-Dade county. 
  Notably, Maricopa county is ranked 3rd in the nation yet Arizona does not even make the top 10 states. Once we  send the county data into training sets, the Prophet library creates models and estimates to visualize the future trends. These trends can be quantified for accuracy using Sklearn to test R-squared metrics. Other metrics are tested too, although they are not specifically analyzed unless anomalous.
