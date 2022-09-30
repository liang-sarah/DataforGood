import pandas
df = pandas.read_csv('shared_data_read_only/Poverty Rate.csv') # read in Poverty Rate
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# list of countries w/ more than 50% of pop. below poverty line
#data = data.apply(pandas.to_numeric, errors='coerce')
#pov_lst = data[['Country', 'Year', 'Percent of Population Below Poverty Line']].where(data['Percent of Population Below Poverty Line'].str.slice(stop=-1).astype(float) > 50)
pov_lst = data[['Country', 'Year', 'Percent of Population Below Poverty Line']].where(data['Percent of Population Below Poverty Line'].str.slice(stop=-1).astype(float) >50)
pov_lst = pov_lst[['Country', 'Year', 'Percent of Population Below Poverty Line']].where(pov_lst['Year']>2010)
pov_lst = pov_lst.drop_duplicates()

df2 = pandas.read_csv('shared_data_read_only/Agriculture Dataset.csv') # read in Agriculture Dataset (emissions)
data2 = pandas.DataFrame(df2)
pandas.options.display.max_columns = None
pandas.options.display.width=None
food_emissions_lst = data2[['Area', 'Year','Meat, cattle-Emissions intensity-kg CO2eq/kg product', 'Cereals excluding rice-Emissions intensity-kg CO2eq/kg product','Milk, whole fresh cow-Emissions intensity-kg CO2eq/kg product']].where(data2['Year']>2010)
food_emissions_lst = food_emissions_lst.drop_duplicates()

d1 = pandas.merge(pov_lst, food_emissions_lst, how='outer', on=['Country', 'Area'])
d1 = d1.dropna()
d1


# In[10]:


import pandas
df = pandas.read_csv('shared_data_read_only/Food Insecurity.csv') # read in Food Insecurity
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# areas where more than 50% have prevalence of undernourishment
#food_insec_lst = data[['Area', 'Year', 'Prevalence of undernourishment (percent) (3-year average)']].where(data['Area']=='Sierra Leone')
food_insec_lst = data[['Area', 'Year', 'Prevalence of undernourishment (percent) (3-year average)']].where(data['Prevalence of undernourishment (percent) (3-year average)'].str.replace('<', '').astype(float) > 50)
food_insec_lst = food_insec_lst[['Area', 'Year', 'Prevalence of undernourishment (percent) (3-year average)']].where(data['Year'].str.slice(stop=-5).astype(float) > 2010)
food_insec_lst = food_insec_lst.dropna()
food_insec_lst


# In[16]:


import pandas
df = pandas.read_csv('shared_data_read_only/Crop Production.csv') # read in Crop Production
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# area, item and area harvested of those that have more than 10000 hectares of harvested area
#crop_prod_lst = data[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(data['Area'] == 'Somalia')
crop_prod_lst = data[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(data['Area harvested - hectares'] >100099999)
crop_prod_lst = crop_prod_lst[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(crop_prod_lst['Year'] >2019)

#crop_prod_lst = data[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(data['Area harvested - hectares'] > 100000000)
#crop_prod_lst = crop_prod_lst[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(crop_prod_lst['Year'] == 2020.0)
crop_prod_lst = crop_prod_lst[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(crop_prod_lst['Area'] != 'World')
crop_prod_lst = crop_prod_lst.dropna()

df = pandas.read_csv('shared_data_read_only/Food Insecurity.csv') # read in Food Insecurity
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# areas where more than 50% have prevalence of undernourishment
#food_insec_lst = data[['Area', 'Year', 'Prevalence of undernourishment (percent) (3-year average)']].where(data['Area']=='Sierra Leone')
food_insec_lst = data[['Area', 'Year', 'Prevalence of undernourishment (percent) (3-year average)']].where(data['Prevalence of undernourishment (percent) (3-year average)'].str.replace('<', '').astype(float) < 20)
food_insec_lst = food_insec_lst.dropna()

df = pandas.read_csv('shared_data_read_only/Agriculture Dataset.csv') # read in Agrigule Database (emissions)
data = pandas.DataFrame(df)

crop_insec_lst = pandas.merge(crop_prod_lst, food_insec_lst, how='outer', on=['Area', 'Area'])
crop_insec_lst = crop_insec_lst.dropna()
crop_insec_lst = pandas.merge(crop_insec_lst, data, how='outer', on=['Area','Area'])
crop_insec_lst = crop_insec_lst.where(crop_insec_lst['Year']>2010)
#crop_insec_lst = crop_insec_lst.where(crop_insec_lst['Population']<100000000)
crop_insec_lst = crop_insec_lst.dropna()
crop_insec_lst


# In[33]:


import pandas
df = pandas.read_csv('shared_data_read_only/Crop Production.csv') # read in Crop Production
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# area, item and area harvested of those that have more than 10000 hectares of harvested area
#crop_prod_lst = data[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(data['Area'] == 'Somalia')
crop_prod_lst = data[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(data['Year'] >2019)

#crop_prod_lst = data[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(data['Area harvested - hectares'] > 100000000)
#crop_prod_lst = crop_prod_lst[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(crop_prod_lst['Year'] == 2020.0)
crop_prod_lst = crop_prod_lst[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(crop_prod_lst['Area'] == ('Togo'))
crop_prod_lst = crop_prod_lst.dropna()
crop_prod_lst


# In[8]:


import numpy
import pandas
df = pandas.read_csv('shared_data_read_only/Poverty Rate.csv') # read in Poverty Rate
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# list of countries w/ more than 50% of pop. below poverty line
#data = data.apply(pandas.to_numeric, errors='coerce')
# .str.slice(stop=-1).astype(float) > 50
pov_lst = data[['Country', 'Year', 'Percent of Population Below Poverty Line']].where(data['Percent of Population Below Poverty Line'].str.slice(stop=-1).astype(float) > 50)

pov_lst = pov_lst.dropna()


df2 = pandas.read_csv('shared_data_read_only/Food Insecurity.csv') # read in Food Insecurity
data2 = pandas.DataFrame(df2)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# areas where more than 50% have prevalence of undernourishment
food_insec_lst = data2[['Area', 'Prevalence of undernourishment (percent) (3-year average)']].where(data2['Prevalence of undernourishment (percent) (3-year average)'].str.replace('<', '').astype(float) > 50)
food_insec_lst = food_insec_lst.dropna()


pov_lst['Prevalence of undernourishment (percent) (3-year average)'] = food_insec_lst['Prevalence of undernourishment (percent) (3-year average)'] #add the food insec column from food_insec_lst to pov_lst
#pov_lst['Match'] = numpy.where(pov_lst['Country'] in food_insec_area_lst, 'True', 'False') #create a new column in df1 to check if places match

pov_lst.dropna()
pov_lst
#pov_food_insec_lst = pov_lst
#pov_food_insec_lst


# In[12]:


import pandas
df = pandas.read_csv('shared_data_read_only/Crop Production.csv')
data = pandas.DataFrame(df)
pandas.options.display.max_columns = None
pandas.options.display.width=None
crop_prod_lst = data[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(data['Area harvested - hectares'] > 10000000)
crop_prod_lst = crop_prod_lst[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(crop_prod_lst['Year'] > 2010)

crop_prod_lst = crop_prod_lst.dropna()
crop_prod_lst


# In[ ]:


import pandas
df1 = pandas.read_csv('shared_data_read_only/Crop Production.csv') # read in Crop Production
data1 = pandas.DataFrame(df1)
pandas.options.display.max_columns = None
pandas.options.display.width=None
# area, item and area harvested of those that have more than 10000 hectares of harvested area
crop_prod_lst = data1[['Area', 'Item', 'Year', 'Area harvested - hectares']]

#crop_prod_lst = crop_prod_lst[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(crop_prod_lst['Item'] == 'Coconuts')
#crop_prod_lst = crop_prod_lst[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(crop_prod_lst['Year'] >2019)

#crop_prod_lst = data[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(data['Area harvested - hectares'] > 100000000)
#crop_prod_lst = crop_prod_lst[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(crop_prod_lst['Year'] == 2020.0)
#crop_prod_lst = crop_prod_lst[['Area', 'Item', 'Year', 'Area harvested - hectares']].where(crop_prod_lst['Area'] != 'World')
#crop_prod_lst = crop_prod_lst.dropna()

df2 = pandas.read_csv('shared_data_read_only/Agriculture Dataset.csv') # read in Agriculture Dataset (emissions)
data2 = pandas.DataFrame(df2)
pandas.options.display.max_columns = None
pandas.options.display.width=None
food_emissions_lst = data2[['Area', 'Year', 'GDP  (2015 US$, mil)','Cereals excluding rice-Emissions intensity-kg CO2eq/kg product']]

emissions_yield = pandas.merge(crop_prod_lst, food_emissions_lst, how='outer', on=['Area', 'Area'])
emissions_yield = emissions_yield.where(emissions_yield['Year_x'] > 2010)
emissions_yield = emissions_yield.where(emissions_yield['Year_y'] > 2010)
#emissions_yield = emissions_yield.where(emissions_yield['Area'] == 'Zimbabwe')
emissions_yield = emissions_yield.where(emissions_yield['Area harvested - hectares'] > 10000000)
#emissions_yield = emissions_yield[['Area', 'Area harvested - hectares']].where(crop_prod_lst['Area harvested - hectares'] > 10000)
emissions_yield = emissions_yield.where(emissions_yield['Cereals excluding rice-Emissions intensity-kg CO2eq/kg product'] < 5)
emissions_yield = emissions_yield.where(emissions_yield['Meat, cattle-Emissions intensity-kg CO2eq/kg product'] < 5)
emissions_yield = emissions_yield.where(emissions_yield['Meat, chicken-Emissions intensity-kg CO2eq/kg product']<5)

#emissions_yield = emissions_yield.dropna()
#emissions_yield = emissions_yield.nsmallest(5, ['Cereals excluding rice-Emissions intensity-kg CO2eq/kg product'])
emissions_yield = emissions_yield.dropna()
emissions_yield


# In[151]:


import pandas
df = pandas.read_csv('shared_data_read_only/Agriculture Dataset.csv') # read in Agrigule Database (emissions)
data = pandas.DataFrame(df)
print(data)

# Cereals excluding rice-Emissions intensity-kg CO2eq/kg product
# Meat, cattle-Emissions intensity-kg CO2eq/kg product
# Meat, chicken-Emissions intensity-kg CO2eq/kg product
# Meat, goat-Emissions intensity-kg CO2eq/kg product
# Meat, pig-Emissions intensity-kg CO2eq/kg product
# Meat, sheep-Emissions intensity-kg CO2eq/kg product
# Milk, whole fresh cow-Emissions intensity-kg CO2eq/kg product
# Milk, whole fresh goat-Emissions intensity-kg CO2eq/kg product
# Rice, paddy-Emissions intensity-kg CO2eq/kg product 

# Food Transport - Emissions (CO2eq) (AR5) - kilotonnes


# In[19]:


import openpyxl
from pathlib import Path

xlsx_file = Path('shared_data_read_only', 'Copy of Data Dictionary.xlsx')
wb_obj = openpyxl.load_workbook(xlsx_file) 

# Read the active sheet:
sheet = wb_obj.active
print(sheet)
