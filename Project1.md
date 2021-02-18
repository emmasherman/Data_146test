## Project 1
# **Describe what is a package? Also, describe what is a library? What are the two steps you need to execute in order to install a package and then make that library of functions accessible to your workspace and current python work session? Provide examples of how you would execute these two steps using two of the packages we have used in class thus far. Be sure to include an alias in at least one of your two examples and explain why it is a good idea to do so.**

A package is a bundle/ directory of python modules. A library is a group of packages or set of useful functions so that you do not have to write the code from scratch you can just use them after you import them. For example, pandas is a very useful function in data science because it is especially useful when working with data files. In Pycharm in order to execute a function you have to preferences and then python interpreter and install the packages that you want to use. From there in the terminal, you have to import the library that the user need.
For example:

From datetime import date

```
Import pandas as pd
Import numpy as np
Import math
```

By importing each of these libraries it allows the user to use the functions without having to write it themselves. Using an alias, such as when you are importing numpy and pandas allows people to use the alias, which is faster and shorter, when calling the functions that they want to use. Now instead of having to type out pandas every time the user only has to type out pd. 

# Describe what is a data frame? Identify a library of functions that is particularly useful for working with data frames. In order to read a file in its remote location within the file system of your operating system, which command would you use? Provide an example of how to read a file and import it into your work session in order to create a new data frame. Also, describe why specifying an argument within a read_() function can be significant. Does data that is saved as a file in a different type of format require a particular argument in order for a data frame to be successfully imported? Also, provide an example that describes a data frame you created. How do you determine how many rows and columns are in a data frame? Is there an alternate terminology for describing rows and columns?

A data frame is a table of data that is represented in rows and columns. The most useful library for working with data frames is pandas. To import data, you have to use the read read_csv() function. 

For example:

1.assign your file to an object so you can specify where the file is located: path = ‘gapminder.tsv’

2.import your data using the read_csv() function. Put the library and then the command itself and you do not want to forget to specify the argument to say that the file is tab separated: data = pd.read_csv(path, sep = ‘\t’)

Data that is saved in a different type of format needs an additional argument, which “sep=.”Specifying the “sep =” argument in the function helps python read in the dataframe. CSV files are usually comma separated files, so if you have a file that is .”.tsv” this means it is tab separated, so you would have to put “sep= ‘\t’”. The user must specify how the file is separated in order for it to be read in correctly

Creating my own dataframe:

```
import pandas as pd
data = ['song1', 'song2', 'song3','song4','song5','song6']
playlist = pd.Series(data, name='Depressing Dance Party', index = ['Intro', 'Dance 1', 'Dance 2', 'Dance 3', 'Dance 4', 'Dance 5'])
play_frame = pd.DataFrame(playlist)
play_frame'
```

To create my own data frame, I used the function pd.series. I put in my data from a list, named the data frame, and then created the index that lined the data up with its respective row. Then using pd.DataFrame I created it into a data frame. To determine how many rows and columns are in a data frame you can use data.shape[0], which gives the number of rows, and data.shape[1], which gives the number of columns.

The alternative terminology for row is an observation and a variable for a column.

# Import the gapminder.tsv data set and create a new data frame. Interrogate and describe the year variable within the data frame you created. Does this variable exhibit regular intervals? If you were to add new outcomes to the raw data in order to update and make it more current, which years would you add to each subset of observations? Stretch goal: can you identify how many new outcomes in total you would be adding to your data frame?

# you need to do this one

# Using the data frame you created by importing the gapminder.tsv data set, determine which country at what point in time had the lowest life expectancy. Conduct a cursory level investigation as to why this was the case and provide a brief explanation in support of your explanation. 

Rwanda in 1992 had the lowest life expectancy, which was 23.599. This low life expectancy was due to an ongoing civil war that started in 1990 and was still taking place in 1992. 

# Using the data frame you created by importing the gapminder.tsv data set, multiply the variable pop by the variable gdpPercap and assign the results to a newly created variable. Then subset and order from highest to lowest the results for Germany, France, Italy and Spain in 2007. Create a table that illustrates your results (you are welcome to either create a table in markdown or plot/save in PyCharm and upload the image). Stretch goal: which of the four European countries exhibited the most significant increase in total gross domestic product during the previous 5-year period (to 2007)?

# you need to do it

# You have been introduced to four logical operators thus far: &, ==, | and ^. Describe each one including its purpose and function. Provide an example of how each might be used in the context of programming.

The == is when a statement is true/equals. For example:

```x==5```

means that x equals 5.

| is for or, it helps to look and see if either or statement is true. For example:

```data_place = data[(data[‘continent’]==’South America’) | (data[‘Year’]==’1992’)] ```

This statement is true if either the data is from south America or 1992. It will return both rows with south America as the continent and 1992 as the year, both do not have to be true for every row. Both statements do not have to be true for the data to be returned. 

& is used when subsetting because it looks at a data frame one row at a time and evaluates both conditions for that row and then move to the next one. For example:

```data_place = data[(data[‘continent’]==’North America’) & (data[‘country’]==’United States’)]```

Data with both north America and united states will be returned. 

^ is XOR, this will return if either operation is true but not if both are true. For example:

```data_place = data[(data[‘continent’]==’South America’) ^ (data[‘Year’]==’1992’)]```

This will return data with South America or 1992 but not data with South America and 1992 in the row.

# Describe the difference between .loc and .iloc. Provide an example of how to extract a series of consecutive observations from a data frame. Stretch goal: provide an example of how to extract all observations from a series of consecutive columns.

.iloc is used when fetching data by its integer position, for instance if you want rows 3 through 6 you can say data.iloc[2:5]. .loc on the other hand fetches rows by their label. For example, if you want to see what data is from year 2003 you can say data.loc[2003].
# fix this one

# Describe how an api works. Provide an example of how to construct a request to a remote server in order to pull data, write it to a local file and then import it to your current work session.

# you need to do this one

# Describe the apply() function from the pandas library. What is its purpose? Using apply) to various class objects is an alternative (potentially preferable approach) to writing what other type of command? Why do you think apply() could be a preferred approach?

The apply() function allows the user to apply the input to this function to an entire data frame. These inputs can include anonymous functions or lamdas that you can apply to the entire data frame. Using apply() is a good alternative to writing a loop. This a much faster and more eifficent way than writing a loop for every function you want to use on your data frame. 

# Also describe an alternative approach to filtering the number of columns in a data frame. Instead of using .iloc, what other approach might be used to select, filter and assign a subset number of variables to a new data frame?

# you need to do this one

