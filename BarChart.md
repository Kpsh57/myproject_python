# myproject_python
#Project 1: Analyse live births using Matplotlib and Numpy libraries
#Generate a bar chart that shows the birth rates from the years 2006 to 2016 using the dataset, live-births.csv

import matplotlib.pyplot as plt           
import numpy as np

filename = 'live-births.csv'
data = np.genfromtxt(filename,  
                    skip_header=1, 
                    dtype=[('year','U10'), ('level_1','U50'), ('value','i8')], delimiter=",",
                    missing_values=['na'],filling_values=[-1])

                              
## Extract rows containing required keywords only
data_required = data[np.isin(data['level_1'], ['Total Live-Births'])]

## Perform filtering to extract years 2006 to 2016
data_year = data_required[np.isin(data_required['year'],['2006','2007','2008','2009','2010','2011','2012','2013','2014','2015','2016'])]

labels = data_year['year']
years = np.arange(0,len(labels))
values = data_year['value']

## Create bar chart showing the number of live births from year 2006 to 2016
plt.figure(1, figsize=(30,30))
plt.title('Live births over the years', fontsize = 40,fontweight='bold')
plt.bar(years,values,color='#d62728')
plt.ylabel('No. of live births', fontsize = 30, fontweight='bold')
plt.xticks(years, labels, rotation='vertical')
plt.show()
