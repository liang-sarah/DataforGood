import pandas
df = pandas.read_csv('shared_data_read_only/Poverty Rate.csv') # read in Poverty Rate
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# list of countries w/ more than 50% of pop. below poverty line
pov_lst = data[['Country', 'Percent of Population Below Poverty Line']].where(data['Percent of Population Below Poverty Line'] > '50%')
pov_lst

import pandas
df = pandas.read_csv('shared_data_read_only/Food Insecurity.csv') # read in Food Insecurity
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# areas where more than 50% have prevalence of undernourishment
food_insec_lst = data[['Area', 'Prevalence of undernourishment (percent) (3-year average)']].where(data['Prevalence of undernourishment (percent) (3-year average)'] > '50%')
food_insec_lst

import pandas
df = pandas.read_csv('shared_data_read_only/Crop Production.csv') # read in Crop Production
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# area, item and area harvested of those that have more than 10000 hectares of harvested area
crop_prod_lst = data[['Area', 'Item', 'Area harvested - hectares']].where(data['Area harvested - hectares'] > 10000)
crop_prod_lst



import numpy

food_insec_area_lst = list(food_insec_lst['Area'])

pov_lst['Prevalence of undernourishment (percent) (3-year average)'] = food_insec_lst['Prevalence of undernourishment (percent) (3-year average)'] #add the food insec column from food_insec_lst to pov_lst
pov_lst['Match'] = numpy.where(str(pov_lst['Country']) in food_insec_area_lst, 'True', 'False') #create a new column in df1 to check if places match

pov_food_insec_lst = pov_lst
pov_food_insec_lst



import pandas
df = pandas.read_csv('shared_data_read_only/Crop Production.csv')
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
print(data)



import openpyxl
from pathlib import Path

xlsx_file = Path('shared_data_read_only', 'Copy of Data Dictionary.xlsx')
wb_obj = openpyxl.load_workbook(xlsx_file) 

# Read the active sheet:
sheet = wb_obj.active
print(sheet)
