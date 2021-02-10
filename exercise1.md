## Informal Exercise

## Exercises

## 1. Get a list of all the years in this data, without any duplicates. How many unique values are there, and what are they?
years = data['year'].unique()
print(years)
print('There are 12 Unique Years and they are', years)
## The years are 1952 1957 1962 1967 1972 1977 1982 1987 1992 1997 2002 2007

## What is the largest value for population (pop) in this data? When and where did this occur? 
## China in 2007
max_pop = data['pop'].max()
#max_pop
idx_pop = (data['pop'] == max_pop)
data_max = data[idx_pop]
data_max

## Extract all the records for Europe. In 1952, which country had the smallest population, and what was the population in 2007?
cont = 'Europe'
idxCont = data['continent'] == cont
def GetRecentDataByContinent(data,continent):
    idxCont = data['continent'] == cont
    temp = data[idxCont]
    year = temp['year'].max()
    idxYear = temp['year'] == year
    return temp[idxYear]

Europe_data = GetRecentDataByContinent(data,'Europe')
Europe_data

## Which country had the smallest population in 1952: Iceland
def GetEurope(data):
    data_europe = data[(data['continent'] == 'Europe') & (data['year'] == 1952)]
    min_pop = data_europe.loc[data_europe['pop'] == data_europe['pop'].min()]
    return min_pop
GetEurope(data)

## Iceland population in 2007: 301931
now = data[(data['country'] == 'Iceland') & (data['year'] == 2007)]
now
