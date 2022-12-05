# myproject_python
# Write a code code that uses the Numpy loadtxt method to read the contents of an external csv file and display pertinent information about the data inside the file 
# A CSV file called singapore-residents-by-ethnic-group-and-sex-end-june-annual was already downloaded from gov,sg website & saved in desktop

import numpy as np

### Read the csv file with the loadtxt() function
filename = "singapore-residents-by-ethnic-group-and-sex-end-june-annual.csv"
data = np.loadtxt(filename, skiprows=1,
                  dtype=[('year','i8'),('level_1','U50'), ('value','i8')],delimiter=",")

### Print out total rows of data in the file
print("There are altogether " + str(len(data))  + " rows of data in the file " + filename )

### Print out the number of years of data captured
data_years = data['year']                         # Only picks up the 'year' column
years = len(np.unique(data_years))                # Get the unique values from 'year' column
maxYr = data_totalresidents['year'].max()
minYr = data_totalresidents['year'].min()

### Extract only the rows with “Total Residents" in the “level_1” column
keyword = 'Total Residents'
column_to_search = data['level_1']
out = [i for i, v in enumerate(column_to_search) if keyword in v]     # Locates the 'level_1' column and look for keyword 'Total Residents'
data_totalresidents = data[out]

print("There are " + str(years) + " years of data captured from " + str(minYr) + " to " + str(maxYr))

### Print out the year which has the highest total number of residents
max = data_totalresidents['value'].max()
argmax = data_totalresidents['value'].argmax()

print("Year with the highest total number of residents: " + str(data_totalresidents[argmax]['year']))
print("Population Count: " + str(max))

### Print out the year which has the lowest total number of residents
min = data_totalresidents['value'].min()
argmin = data_totalresidents['value'].argmin()

print("Year with the lowest total number of residents: " + str(data_totalresidents[argmin]['year']))
print("Population Count: " + str(min))
