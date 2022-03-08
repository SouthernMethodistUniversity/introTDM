---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.10.3
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Introduction to Python for Text and Data Mining


In this notebook:

- [Introduction to Python](#Introduction-to-Python)
- [Working with Data](#Working-with-Data)
- [Preliminary Text Analysis](#Preliminary-Text-Analysis)
- [Processing Text for Analysis](#Processing-Text-for-Analysis)
- [Advanced Text Mining Examples](#Advanced-Text-Mining-Examples)


# Introduction to Python


Python is a general use programming language popular amongst beginners and experts alike for its easy of use, readability, and flexibility. From it's origins as a language designed for teaching to being the primary language for machine learning applications, Python is capable of doing just about anything you need it to.

No language is perfect and Python is no exception. Python is rarely the fastest option or necessarily the cleanest option depending on your application. It also requires a good working knowledge of the assorted packages and libraries that make life so much easier as a programmer.

This notebook is designed to take you from no knowledge of python to a basic understanding of how to work with text data sets. It also demonstrates next steps and concepts to explore should you want to take your analysis further.


## Jupyter and Navigating the Notebook


This interface is called a Jupyter Notebook. It allows us to run python interactively while including text content. Python can also be run as a 'script' - a single set of instructions read in order (i.e. not interactively) - which is popular for finished code.


To operate this notebook, you will need to execute boxes of code, called cells. To do this you can either click the *Run* button on the toolbar or use [Shift]+[Enter].

Throughout this notebook you will see cells that are not code (like this one). These cells contain text in a language called Markdown. You can execute these cells to render formatted text. A cheatsheet for Markdown can be found [here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet). There will also be comments with in the code itself that give additional information about the operation of the code, describe functions or show you places where you might want to make changes. These comments are always preceded by an octothorp (#) and in most cases be a different color from the surrounding text.

Notebooks save automatically, however if you have made big changes your code, you can checkpoint it. This allows you to roll back changes to this point (or any previous checkpoints) should something break in the future.

There are a few useful [keyboard shortcuts](https://gist.github.com/kidpixo/f4318f8c8143adee5b40) for modifying the cells in a notebook. To use these, click on the far left side of the cell such that the outline changes color (to blue in most cases), press [Enter]] to return to editing the cell's contents.

-Add a cell **a**bove the current cell   [A]

-Add a cell **b**elow the current cell   [B]

-**D**elete the current cell   [D,D]

**Let's try it out!**


### Basic Math


Python can do simple mathematical operations just like a calculator.

```python
1+1
```

```python
2.5-2.0
```

## Variables and Objects


Calculations are nice but we really want to be able to store our calculations in memory so that we can access them later. We do that by assigning variables. 

```python
a=2
b=3
```

```python
a+b
```

Variables can be named just about anything

```python
Dallas=2
SMU=7
Texas_TX=3
```

```python
#Note: that if we assign a value to a variable, our notebook won't return that value to our screen.
#If we want it to show us the value, we can call that variable after it is assigned.
ouranswer = SMU*Dallas*Texas_TX
ouranswer
```

So far we have been doing all of our operations on numbers, integers and floats (decimals), but there are other useful objects we can use in Python.

Strings allow us to store and operate on text data. Strings in Python are surrounded by either single quotes '' or double quotes "".

```python
ourstring = "Here is a string in Python!"
ourstring
```

If we later want to see the value stored in a variable we can always use the built in **print** function. **Print** is recognized as a keyword by our notebook and so the color changes to make our lives as programmers easier.

```python
print(ourstring)
```

What if we want to have multiple strings stored at once but we don't want to assign a bunch of variables? Then we can use a list.

Lists are enclosed by brackets [] and separated by commas.

```python
ourlist = ['This', 'is', "a", "list", 'of', "strings"]
```

```python
print(ourlist)
```

To access individual elements in a list you call it by its reference number.

*__Note:__ In Python, counting starts with 0. Thus in the list [a,b,c], a is the 0th element and c is the 2nd*

```python
first = ourlist[0]
```

```python
# Notice we can call the last element by using a negative reference number. This lets us see the end without knowing how long the list is.
last = ourlist[-1]
```

```python
print(first,last)
```

```python
# If we did want to know the length of our list we can use the len() function
len(ourlist)
```

### Dictionaries


Dictionaries are a different way of storing data than lists. They rely on a key and value system as opposed to the order of the entries.

Dictionaries are enclosed in curly braces {}, the key and value are separated by a colon : and entries are separated by commas ,

Values can then be accessed by referencing the key.

Note that finding dictionary values does not go both ways, so using the value to find the key will cause an error.

```python
ourdictionary = {"Dallas":1345000,"Plano":286143,"Taos":5668,'Houston':2326000}
ourdictionary
```

```python
ourdictionary["Taos"] 
#NOTE: ourdictionary[5668] will NOT give you "Taos", but an error.
```

Here are the word counts for the *Lord of the Rings* books ([citation](http://lotrproject.com/statistics/books/wordscount)). We will use this data for some exercises below.

|__Book__|__Word Count__|
|---|---|
|The Silmarillion|130115|
|The Hobbit|95506|
|The Fellowship of the Ring|187726|
|The Two Towers|156147|
|The Return of the King|137037|


```python

tolkien = {"The Silmarillion":130115,"The Hobbit":95506,"The Fellowship of the Ring":187726, "The Two Towers":156147, "The Return of the King":137037}

bilbo=tolkien["The Hobbit"]

frodo=tolkien["The Fellowship of the Ring"]

print("The Fellowship of the Ring - The Hobbit")

print(frodo-bilbo)

print("Total Words for the Lord of the Rings Trilogy")

print(tolkien["The Fellowship of the Ring"]+tolkien["The Two Towers"]+tolkien["The Return of the King"])

```

## Loops and Functions


Computers are much better at doing simple repeatable tasks than humans are so to leverage this advantage, we will cover two different ways of writing these kind of repeatable instructions.


### Loops


Loops are a way of having Python complete a task over and over.

The most common form if a **for** loop. A **for** loop completes a task a fixed number of times by iterating a variable over the members of a sequence in order.

```python
#Example for loop
for i in [0,1,2]:
    print(i)
```

**Note**: The indention is important, it tells Python that the line *print(i)* belongs inside the loop.


### Functions


Sometimes it would be nice to be able to save a group of instructions in a single block, that way we won't need to rewrite several lines of code each time we want to do that set of operations.

To do this we define a **function**.

Functions allow us to define a more complicated set of instructions as a single entity and call that entire block of code directly.

Functions are defined (*def*), named (lowercase is a standard practice) and accept arguments (). They then can return a value if needed (*return*).

Python has several built in functions (*print()* is a good example) and when you combine external packages and libraries, there are functions for just about everything you could think of.

```python
# Example function
def square_me(n):
    return n*n
```

```python
square_me(4)
```

Putting loops and functions together is where python can become very powerful.

```python
# Looping over a function
for i in [0,1,2,3]:
    print(square_me(i)) # note that this is still tabbed in within the for loop
```

```python
# A function with a loop
def print_numbers(start,stop):
    for i in range(start,stop): #Here the range() function gives us all the values from start up to but excluding the stop value
        print(i) # this is indented twice, so Python knows it is within the loop within the function
```

```python
print_numbers(0,4)
```

## Libraries


Libraries are pre-written chunks of code designed to be integrated into projects for a specific purpose.  The idea is to keep people from having to reinvent the wheel every time they want to write a program.  When we encounter situations where a libary might be useful, we use the keyword *import* to tell the program that we want to use this pre-existing code.  As an example, in the next section you will use a library called Pandas which helps visualize data and make it easier to digest, which is very useful for us.  Because of this, we will import that code into this program simply by running the cell with the import that goes with that code.  Here is what you will see, only in commented code.

```python
#import pandas as pd

#by using the keyword *as* and giving pandas an alternative name (pd) in this program, it allows us to use the
#functions within pandas while only having to type our pd instead of pandas every time.
```

Most programming languages have libraries that allow you to import code this way, and it will save you a lot of time and allow you to quickly use many new functions that are highly polished.


## DataFrames and Pandas


Now it is time to use what we have learned to start doing some data science.

Pandas is the name of a library in which there are functions and tools for doing operations common in data analysis and data science. One particularly great feature is the DataFrame structure which allows us to work with an object similar to an Excel spreadsheet but with the flexibility and power of Python behind it.

First we will need to import the Pandas library and create a DataFrame. DataFrames are can also be created when you import files (like CSV's) or tables from a database (like SQL).

```python
import pandas as pd
```

```python
#Notice here the data is a dictionary, similar to the one we used above but with the titles and wordcounts as nested lists
d = {"Books":["The Silmarillion","The Hobbit","The Fellowship of the Ring","The Two Towers","The Return of the King"],
     "Words":[130115,95506,187726,156147,137037]
    }
df = pd.DataFrame(d)
df
```

Now we can operate on entire rows or columns in our DataFrame.

```python
df["Books"] #Selecting the column "Books"
```

```python
df[:2] #Selecting the first 2 rows
```

```python
df[2:4] #Selecting rows 2 up to 4
```

```python
df["Words"][2:4] #Selecting the second and third row from the "Words" column.
```

```python
df[2:4]["Words"] #Same result but from the opposite order
```

You can also operate on entire columns in your DataFrame. Just be careful because this can give you unexpected results. Rows are generally more consistent for elements within a DataFrame.

```python
total = sum(df["Words"])
total
```

## Plotting


Visualizing data is incredibly important when trying to convey findings. There are several libraries available for doing data visualization. Pandas has some built in plotting functionality, but we have provided access to MatPlotLib, Plotly and Seaborn as well.

```python
# This is only needed in this case because we wanted to show the names of the books. You could make a similar plot in Pandas.
import matplotlib as plt

%config InlineBackend.figure_format ='retina'
```

```python
plot = df.plot(kind='bar') # we are setting the type of plot to a bar graph
plot.set_xticklabels(df['Books']); #This lets us rename the x axis labels
```

## More Complex DataFrame Operations


To look at slightly more complex data operations, we need more complex data.

Below we have all the chapters from the Hobbit and Lord of the Rings books along with their word counts. Notice that each chapter is a list of information and then each of those list is an element in a larger list.


### More Complex Data

```python
chapters = [[0,1,'An Unexpected Party',8638,0],
            [0,2,'Roast Mutton',5257,0],
            [0,3,'A Short Rest',2876,0],
            [0,4,'Over Hill and Under Hill',4034,0],
            [0,5,'Riddles in the Dark',6967,0],
            [0,6,'Out of the Frying Pan into the Fire',6703,0],
            [0,7,'Queer Lodgings',9027,0],
            [0,8,'Flies and Spiders',10223,0],
            [0,9,'Barrels Out of Bond',5833,0],
            [0,10,'A Warm Welcome',3930,0],
            [0,11,'On the Doorstep',3001,0],
            [0,12,'Inside Information',7132,0],
            [0,13,'Not At Home',3909,0],
            [0,14,'Fire and Water',3236,0],
            [0,15,'The Gathering of the Clouds',3362,0],
            [0,16,'A Thief in the Night',2153,0],
            [0,17,'The Clouds Burst',3949,0],
            [0,18,'The Return Journey',2815,0],
            [0,19,'The Last Stage',2461,0],
            [1,-4,'Concerning Hobbits',3406,1],
            [1,-3,'Concerning Pipeweed',600,1],
            [1,-2,'Of the Ordering of the Shire',2431,1],
            [1,-1,'Note on the Shire Records',914,1],
            [1,1,'A Long-expected Party',10012,1],
            [1,2,'The Shadow of the Past',11311,1],
            [1,3,'Three is Company',9763,1],
            [1,4,'A Short Cut to Mushrooms',5957,1],
            [1,5,'A Conspiracy Unmasked',5196,1],
            [1,6,'The Old Forest',6502,1],
            [1,7,'In the House of Tom Bombadil',5501,1],
            [1,8,'Fog on the Barrow-downs',6694,1],
            [1,9,'At the Sign of the Prancing Pony',6251,1],
            [1,10,'Strider',5905,1],
            [1,11,'A Knife in the Dark',9468,1],
            [1,12,'Flight to the Ford',8805,1],
            [1,1,'Many Meetings',9085,2],
            [1,2,'The Council of Elrond',16360,2],
            [1,3,'The Ring goes South',10656,2],
            [1,4,'A Journey in the Dark',11501,2],
            [1,5,'The Bridge of Khazad-dum',5428,2],
            [1,6,'Lothlorien',9387,2],
            [1,7,'The Mirror of Gladriel',6896,2],
            [1,8,'Farewell to Lorien',6174,2],
            [1,9,'The Great River',7218,2],
            [1,10,'The Breaking of the Fellowship',6305,2],
            [2,1,'The Departure of Boromir',3397,3],
            [2,2,'The Riders of Rohan',11133,3],
            [2,3,'The Uruk-hai',7854,3],
            [2,4,'Treebeard',12876,3],
            [2,5,'The White Rider',8856,3],
            [2,6,'The King of the Golden Hall',9303,3],
            [2,7,"Helm's Deep",7575,3],
            [2,8,'The Road to Isengard',7899,3],
            [2,9,'Flotsam and Jetsam',7789,3],
            [2,10,'The Voice of Saruman',5663,3],
            [2,11,'The Palantir',6325,3],
            [2,1,'The Taming of Smeagol',8375,4],
            [2,2,'The Passage of the Marshes',7357,4],
            [2,3,'The Black Gate is Closed',5881,4],
            [2,4,'Of Herbs and Stewed Rabbit',6975,4],
            [2,5,'The Window on the West',10120,4],
            [2,6,'The Forbidden Pool',5179,4],
            [2,7,'Journey to the Crossroads',4266,4],
            [2,8,'The Stairs of Cirith Ungol',6793,4],
            [2,9,"Shelob's Lair",5209,4],
            [2,10,'The Choices of Master Samwise',7322,4],
            [3,1,'Minas Tirith',13100,5],
            [3,2,'The Passing of the Grey Company',8586,5],
            [3,3,'The Muster of Rohan',6951,5],
            [3,4,'The Siege of Gondor',11793,5],
            [3,5,'The Ride of the Rohirrim',4358,5],
            [3,6,'The Battle of the Pelennor Fields',5225,5],
            [3,7,'The Pyre of Denethor',3736,5],
            [3,8,'The Houses of Healing',6731,5],
            [3,9,'The Last Debate',5416,5],
            [3,10,'The Black Gate Opens',5204,5],
            [3,1,'The Tower of Cirith Ungol',9721,6],
            [3,2,'The Land of Shadow',8446,6],
            [3,3,'Mount Doom',7777,6],
            [3,4,'The Field of Cormallen',4721,6],
            [3,5,'The Steward and the King',7639,6],
            [3,6,'Many Partings',7440,6],
            [3,7,'Homeward Bound',4106,6],
            [3,8,'The Scouring of the Shire',11296,6],
            [3,9,'The Grey Havens',4791,6]
           ]
```

Now we can turn the list of the lists into a dataframe. We have also named our columns. This isn't necessary but it does make things clearer to work with.

```python
cols = ['CollectionNum','ChapterNum','ChapterName','WordCount','BookNum']
data = pd.DataFrame(chapters, columns=cols)
```

```python
data
```

Now we might want to apply the names of each of the traditional "books" you might think of when you think about the Lord of the Rings. To do this we want to apply a function to each value in a column and save it into a new column. In this example, our "function" is using our *CollectionNum* to reference a book name in our list *titles*.

```python
titles = ['The Hobbit','The Fellowship of the Ring', 'The Two Towers', 'The Return of the King']
data['CollectionName']=data['CollectionNum'].apply(lambda x: titles[x])
```

### [GroupBy](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.groupby.html)


Now that we have data for each of the chapters, we can group them using groupby. This lets us do aggregate operations like "add all the wordcounts for each book" or "count how many chapters there are in each book".

Groupby is a powerful tool but if you don't understand your data, it can quickly introduce errors.

```python
data.groupby(by='CollectionName').count()
```

```python
data.groupby(by='CollectionName').sum()
```

### Selecting (Advanced Slicing)


You can select slices of your dataframe using conditional logic as well.

```python
df
```

```python
# Select values based on exact matches
df[df['Books']=='The Hobbit']
```

```python
# Select values by negating a match
df[df['Books']!='The Hobbit']
```

```python
# Select values containing substrings
df[df['Books'].str.contains('ing')]
```

```python
# Select values on multiple conditions using different columns
df[(df['Books'].str.contains('ing')) & (df['Words']>150000)]
```

### Joining (Mixing Data Sets)


You can also merge 2 dataframes if you want. Merging allows you to combine datasets in new ways and is a great tool to have when working with complex datasets.


First we need a second dataframe to work with. Here, we have made a dataframe with the publication year of each of of our Tolkien books.

```python
df
```

```python
dates = pd.DataFrame({'Name':df['Books'],'Year':pd.Series([1977,1934,1954,1954,1954])})
dates
# NOTE: We named our column 'Name' for instructional purposes, but a better name would be 'Books' so that it matches my other dataframe.
#       Typically you want to use a unique identifier in your data and then merge based on that column.
```

Now we can merge our new dates dataframe with our existing dataframe.

We have done an inner join (only rows that match in both dataframes will appear in our join) where the column in the left dataframe is called "Books" and the column in the right dataframe is called "Name".

More documentation on merging dataframes can be found [here](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.merge.html).

```python
pd.merge(df,dates, left_on="Books", right_on="Name", how = 'inner')
```

Notice that our merge duplicated our matching column because they had different names. This would not happen if we had the same name for columns in both dataframes. However, will not always be the case, so you can clean up your dataframe by dropping one of the redundant columns.

```python
merged = pd.merge(df,dates, left_on="Books", right_on="Name", how = 'inner').drop(columns=['Name'])
merged
```

### More Complex Plotting


Lastly, we can combine several of the things we have learned into a single plot. Here we can group each book together and then look at the word counts by chapter throughout the story.


First, we want to come up with a way to step through the books in a linear way. We have provided a few ways to do this in increasing complexity.

```python
# Simple - add the collection number to the chapter number divided by 10
#data['BookChapter'] = data['CollectionNum']+0.1*data['ChapterNum']

# Much better - add the book number to the chapter number divided by 10
#data['BookChapter'] = data['BookNum']+0.1*data['ChapterNum']

# Best but complicated - add the book number to the chapter number scaled by 1/n where n is the max number of chapters in that book.
data['BookChapter']=data.apply(lambda x: x['BookNum']+(1/data.groupby(by='BookNum').max()['ChapterNum'][x['BookNum']])*x['ChapterNum'], axis=1)
```

```python
groups = data.groupby("CollectionName")

for name, group in groups:

    plt.pyplot.plot(group["BookChapter"], group["WordCount"],label=name)

plt.pyplot.legend()

```

 Notice that the prologue materials in *The Fellowship of the Ring* cause it to overlap with the *Hobbit*. If we wanted to resolve this, we would need to revisit our conventions in our data.


# Working with Data


## Text as Data


A type of data that has become especially popular and powerful to investigate is text. Turns out there is a lot that we can learn by looking at what we write down. We'll spend more time working with text later in the class but for now, we'll just load the data and do some basic parsing.

```python
example_text_file = "../example_data/folktales.csv"

df = pd.read_csv(example_text_file)
```

```python
df
```

### Exploring our Data


#### Question 1) What countries do we have stories from?

```python
df['Country of Origin'].values
```

```python
# How about a more compressed list
df['Country of Origin'].value_counts()
```

#### Question 2) What fraction of my stories were written by the Brothers Grimm?

```python
total_stories = len(df)
total_stories
```

```python
grimm = len(df[(df['Author'].str.contains('Grimm'))==True])
grimm
```

```python
grimm/total_stories
```

#### Question 3) How many titles contain animals?


How would I even do this?

```python
df['Title'].str.contains('animals').value_counts()
```

```python
df[df['Title'].str.contains('Wol')]['Title']
```

That clearly doesn't seem like what the question is asking... Maybe this isn't something we can answer. Why not? What would we need to answer this question?


## Working with Messy Data


Sometimes our data can be so messy that it is nearly impossible to work with.

```python
messy_file="../example_data/messy_data.csv"

messy = pd.read_csv(messy_file,delimiter=";")
messy
```

Let's just look at this data. How many data issues can you find that would hinder an analysis? How would you handle it?


## Tricks for messy data


#### Names


One common problem is that names tend to be really bad ways to identify people. Why is that?

A solution to this is to use something called a unique identifier (think your SMU ID number). A unique identifier can be used instead of a name because it will have a standard format and generally can be used to link an individual across multiple data sets. If used properly it can also be a good way to de-identify individuals.

```python
import random
messy['uID'] = [str(random.randint(0,1000)).zfill(4) for i in range(len(messy))]
messy
```

```python
messy[['uID','Age','Ship']]
```

There is a lot to unpack with what we did there, let's break that down:

- First we're generating a list using a single line for loop
- Our loop is over the elements in the range that goes from 0 to the length of our data frame - effectively saying make the list the same length as our dataframe
- Then our loop generates a random integer from 0 to 1000 but we needed to import python's random number generator to do that for us
- Then we want to convert our random integer to a string. We wouldn't want to accidentally do math with our unique ID numbers
- We want to make sure our IDs are all the same length using zfill to add 0s to the front of our string. This is common for numbers like this. Just think of your credit card number, social security number, SMU ID....
- Lastly, we assign our list to the new column in our dataframe 'uID'

```python
# The same code but unpacked
import random

ll = [] #initialize an empty list
length = len(messy)
for i in range(0,length):
    r = random.randint(0,1000)
    s = str(r)
    s4 = s.zfill(4)
    ll.append(s4) # This lets us add elements to a list
messy['uID']=ll
messy
```

#### Dates


Another common issue is that there are lots of formats for dates and times. This isn't just an issue with personal data but is one that can cause huge headaches when working with data sets. Even asking simple questions can become complicated when working with dates if you aren't sure of the formatting.

Think about all the steps your brain makes if I ask you what the date was 3 weeks ago?


Somewhat incredibly, pandas can actually recognize several forms of dates and guess what the date formats are and convert them to a standardize format using the function [to_datetime](https://pandas.pydata.org/docs/reference/api/pandas.to_datetime.html?highlight=to_datetime#pandas.to_datetime).

```python
messy['Date_Fixed'] = pd.to_datetime(messy['Air_Date'],errors='raise')
messy[['Air_Date','Date_Fixed']]
```

#### Missing Values


Another problem we can encounter is missing data. This happens all the time with "wild data" and can happen for numerous reasons, for example:
- no data should exist for a reason
- an error in the data creation
- an operation induced the missing data

Pandas has a simple function to handle this called [fillna](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.fillna.html).

```python
messy = messy.fillna('No Data Available') #Note this will change our data
messy
```

#### Case Sensitivity


Another common issue with dealing with messy data is case sensitivity. Since python sees 'A' and 'a' as two different characters, it is important to be aware of case sensitivity. The easiest way to do this is to send all the characters in a particular column to a single case pattern. Fortunately, pandas has a family of functions to do that for us. [lower](https://pandas.pydata.org/docs/reference/api/pandas.Series.str.lower.html?highlight=lower#pandas.Series.str.lower) is a good example.

```python
messy['Ship'] = messy['Ship'].str.lower()
messy
```

That might not actually be what we want but at least we can compare the values now.

```python
messy['Ship'].value_counts()
```

### Check Results


Let's look at our messy data before:

```python
before = pd.read_csv(messy_file,delimiter=";")
before
```

and after:

```python
messy[["uID","Name","Date_Fixed","Age","Height","Ship","Text"]]
```

# Preliminary Text Analysis


These are the basic libraries we will use in for data manipulation (pandas) and math functions (numpy). We will add more libraries as we need them.

As a best practice, it is a good idea to load all your libraries in a single cell at the top of a notebook, however for the purposes of this tutorial we will load them as we go.

```python
import pandas as pd
import numpy as np
```

```python
data = pd.read_csv(example_text_file) #if your filetype is not CSV, you may need to add " , sep = 'separating_character_here' " after the filename.  This may require extra manipulation, so be careful.
data.head() #We will use the .head() attribute to limit the amount of the DataFrame is displayed on screen. It is not necessary for computation.
```

Here we can see all the information available to us from the file in the form of a Pandas DataFrame. For the remainder of this tutorial, we will focus primarily on the full text of each data chunk, which we will name the *Story* column.  With your data set this is likely to be something very different, so feel free to call is something else.


### Counting Words and Characters


The first bit of analysis we might want to do is to count the number of words in one piece of data. To do this we will add a column called *wordcount* and write an operation that applies a function to every row of the column.

Unpacking this piece of code, *len(str(x).split(" ")*, tells us what is happening.

For the content of cell *x*, convert it to a string, *str()*, then split that string into pieces at each space, *split()*.

The result of that is a list of all the words in the text and then we can count the length of that list, *len()*.

```python
data['wordcount'] = data['Text'].apply(lambda x: len(str(x).split(" ")))
data[['Text','wordcount']].head()
```

We can do something similar to count the number of characters in the data chunk, including spaces. If you wanted to exclude whitespaces, you could take the list we made above, join it together and count the length of the resulting string.

```python
data = data.fillna("No Information Provided") #If some of our data is missing, this will replace the blank entries. This is only necessary in some cases

```

```python
data['char_count'] = data['Text'].str.len() ## this also includes spaces, to do it without spaces, you could use something like this: "".join()
data[['Text','char_count']].head()
```

Now we want to calculate the average word length in the data.

Let's define a function that will do that for us:

```python
def avg_word(sentence):
    words = sentence.split()
    return (sum(len(word) for word in words)/len(words))
```

We can now apply that function to all the data chunks and save that in a new column.

```python
data['avg_word'] = data['Text'].apply(lambda x: avg_word(x))
data[['Text','avg_word']].head()
```

We can then sort by the average word length.

```python
data[['Text','avg_word']].sort_values(by='avg_word', ascending=True).head()
```

### Count Stopwords


Stopwords are words that are commonly used and do little to aid in the understanding of the content of a text. There is no universal list of stopwords and they vary on the style, time period and media from which your text came from.  Typically, people choose to remove stopwords from their data, as it adds extra clutter while the words themselves provide little to no insight as to the nature of the data.  For now, we are simply going to count them to get an idea of how many there are.

For this tutorial, we will use the standard list of stopwords provided by the Natural Language Toolkit python library.

```python
import nltk
nltk.download('stopwords')
```

```python
from nltk.corpus import stopwords
stop = stopwords.words('english')
```

To count the number of stopwords in a chunk of data, we make a list of all the words in our data that are also in the stopword list. We can then just take the length of that list and store it in a new column

```python
data['stopwords'] = data['Text'].apply(lambda x: len([x for x in x.split() if x in stop]))
data[['Text','stopwords','wordcount']].head()
```

### Other Ways to Count


There are other types of counting we might want to do. These might be more or less relevant depending on the test you are working with.

For completeness, we have put them here but we will skip over them in this tutorial


#### Counting Special Characters


This is really only useful for Twitter or other Internet texts but you could imagine wanting to count quotations or exclamations with something similar.

```python
data['special_char'] = data['Text'].apply(lambda x: len([x for x in x.split() if x.startswith('#')]))
data[['Text','special_char']].head()
```

#### Counting Numbers


This counts the number of numerical digits in a text, which for strict text may not be helpful, but mostly numerical data will make more use of this.

```python
data['numerics'] = data['Text'].apply(lambda x: len([x for x in x.split() if x.isdigit()]))
data[['Text','numerics']].sort_values(by='numerics', ascending=False).head()
```

#### Counting Uppercase


Counting uppercase words could give us an indication of how many sentences or proper nouns are in a text but this is likely too broad to be used to classify either on its own.

```python
data['upper'] = data['Text'].apply(lambda x: len([x for x in x.split() if x.isupper()]))
data[['Text','upper']].head()
```

# Processing Text for Analysis


A major component of doing analysis on text is the cleaning of the text prior to the analysis.

Though this process destroys some elements of the text (sentence structure, for example), it is often necessary in order to describe a text analytically. Depending on your choice of cleaning techniques, some elements might be preserved better than others if that is of importance to your analysis.


## Cleaning Up Words


This series of steps aims to clean up and standardize the text itself. This generally consists of removing common elements such as stopwords and punctuation but can be expanded to more detailed removals.


### Lowercase


Here we enforce that all of the text is lowercase. This makes it easier to match cases and sort words.

Notice we are assigning our modified column back to itself. This will save our modifications to our DataFrame

```python
data['Text'] = data['Text'].apply(lambda x: " ".join(x.lower() for x in x.split()))
data['Text'].head()
```

### Remove Punctuation


Here we remove all punctuation from the data. This allows us to focus on the words only as well as assist in matching.

```python
data['Text'] = data['Text'].str.replace('[^\w\s]','')
data['Text'].head()
```

### Remove Stopwords


Similar to what we did earlier when we counted stopwords, we now want to remove the stopwords. We will again use the NLTK list of stopwords but this time keep a list of words that do not appear in the list of stopwords.

```python
from nltk.corpus import stopwords
stop = stopwords.words('english')
```

```python
data['Text'] = data['Text'].apply(lambda x: " ".join(x for x in x.split() if x not in stop))
data['Text'].head()
```

### Remove Frequent Words


If we want to catch common words that might have slipped through the stopword removal, we can build out a list of the most common words remaining in our text.

Here we have built a list of the 10 most common words. Some of these words might actually be relevant to our analysis so it is important to be careful with this method.

```python
freq = pd.Series(' '.join(data['Text']).split()).value_counts()[:10]
freq
```

We now follow the same procedure with which we removed stopwords to remove the most frequent words.

```python
freq = list(freq.index)
data['Text'] = data['Text'].apply(lambda x: " ".join(x for x in x.split() if x not in freq))
data['Text'].head()
```

### Remove Rare Words


By analogy, we can remove the most rare words. Some of these are strange misspellings or [hapax legomenon](https://en.wikipedia.org/wiki/Hapax_legomenon) (one off words that don't appear anywhere else in the text).

```python
freq = pd.Series(' '.join(data['Text']).split()).value_counts()[-10:]
freq
```

Again, removing words following the same process as the stopword removal.

```python
freq = list(freq.index)
data['Text'] = data['Text'].apply(lambda x: " ".join(x for x in x.split() if x not in freq))
data['Text'].head()
```

### Tokenization


Tokenization is the process of splitting up a block of text into a sequence of words or sentences.

For those familiar with R and the Tidyverse, this would be referred to as unnesting tokens

Here we show all the tokenized words from the first data chunk in our Dataframe.

```python
import nltk
nltk.download('punkt')
```

```python
from textblob import TextBlob

TextBlob(data['Text'][0]).words
```

## Stemming


Stemming is the process of removing suffices, like "ed" or "ing".

We will use another standard NLTK package, PorterStemmer, to do the stemming.

```python
from nltk.stem import PorterStemmer
st = PorterStemmer()
data['Text'][:5].apply(lambda x: " ".join([st.stem(word) for word in x.split()]))
```

As we can see "wonderful" became "wonder", which could help an analysis, but "deathbed" became "deathb" which is less helpful.


## Lemmatization


Lemmatization is often a more useful approach than stemming because it leverages an understanding of the word itself to convert the word back to its root word. However, this means lemmatization is less aggressive than stemming (probably a good thing).

```python
import nltk
nltk.download('wordnet')
```

```python
from textblob import Word
data['Text'] = data['Text'].apply(lambda x: " ".join([Word(word).lemmatize() for word in x.split()]))
data['Text'].head()
```

## Visualizing Text with Wordclouds


Now, we are going to make a word cloud based on our data set.

```python
import wordcloud
```

```python
from wordcloud import WordCloud, ImageColorGenerator
import matplotlib.pyplot as plt

stop_words = set(stop)
#stop_words.update(['see','saw','come','well','thought'])
```

If you want to update the stopwords after you see the wordcloud, type them into the empty list above and remove the # sign.

```python
word = " ".join(data['Text'])
wordcloud = WordCloud(stopwords=stop_words, background_color="black").generate(word)
plt.imshow(wordcloud, interpolation='bilinear')
plt.axis("off")
plt.show()
```

The above code creates a wordcloud based off all the words (except for stop words) in all of the stories. While this can be fun, it may not be as interesting as a wordcloud for a single story. Let's compare:

```python
for i in range(0, 3):
    word = data['Text'][i]
    wordcloud = WordCloud(stopwords=stop_words, background_color="white").generate(word)
    plt.imshow(wordcloud, interpolation='bilinear')
    plt.axis("off")
    plt.show()
```

# Advanced Text Mining Examples


In this section, we demonstrate more advanced techniques that can be used in text mining to extract more nuanced information and metrics than we can get with basic counting or wordclouds.


## Load the Data


This is the same dataset as above but we are starting this section with a clean load of the data.

```python
example_text_file = '../example_data/folktales.csv'

data = pd.read_csv(example_text_file)

data["Index"]=data.index
data.head()
```

## Selected Cleaning


Here we have only decided to do a limited cleaning on the data to assist in our analysis.


### Lowercase

```python
data['Text'] = data['Text'].apply(lambda x: " ".join(x.lower() for x in x.split()))
data['Text'].head()
```

### Remove Punctuation

```python
data['Text'] = data['Text'].str.replace('[^\w\s]','')
data['Text'].head()
```

### Remove Stopwords

```python
from nltk.corpus import stopwords
stop = stopwords.words('english')
data['Text'] = data['Text'].apply(lambda x: " ".join(x for x in x.split() if x not in stop))
data['Text'].head()
```

### Remove Frequent Words

```python
freq = pd.Series(' '.join(data['Text']).split()).value_counts()[:10]
freq
```

We now follow the same procedure with which we removed stopwords to remove the most frequent words.

```python
#freq = list(freq.index)
#data['Text'] = data['Text'].apply(lambda x: " ".join(x for x in x.split() if x not in freq))
#data['Text'].head()
```

## Lemmatization


Lemmatization is often a more useful approach than stemming because it leverages an understanding of the word itself to convert the word back to its root word. However, this means lemmatization is less aggressive than stemming (probably a good thing).

```python
from textblob import Word
data['Text'] = data['Text'].apply(lambda x: " ".join([Word(word).lemmatize() for word in x.split()]))
data['Text'].head()
```

At this point we have a several options for cleaning and structuring our text data. The next section will focus on more advanced ways to study text analytically.


## Applying Algorithms to Text


This section focuses on more complex methods of analyzing textual data. We will continue to work with our same DataFrame.


## N-grams


N-grams are combinations of multiple words as they appear in the text. The N refers to the number of words captured in the list. N-grams with N=1 are referred unigrams and are just a nested list of all the words in the text. Following a similar pattern, bigrams (N=2), trigrams (N=3), etc. can be used.

N-grams allow you to capture the structure of the text which can be very useful. For instance, counting the number of bigrams where "said" was preceded by "he" vs "she" could give you an idea of the gender breakdown of speakers in a text. However, if you make your N-grams too long, you lose the ability to make comparisons.

Another concern, especially in very large data sets, is that the memory storage of N-grams scales with N (bigrams are twice as large as unigrams, for example) and the time to process the N-grams can balloon dramatically as well.

All that being said, we would suggest focusing on bigrams and trigrams as useful analysis tools.

```python
from nltk.stem import WordNetLemmatizer
from textblob import TextBlob

index = 3

lemmatizer = WordNetLemmatizer()
n_grams = TextBlob(data['Text'][index]).ngrams(2)
```

```python
characters=[]
for i in ['wolf', 'cat', 'king', 'queen']:
     characters.append(lemmatizer.lemmatize(i))
```

```python
for n in n_grams:
    if n[0] in characters:
        print(n)
```

```python
from nltk import ngrams
from collections import Counter

ngram_counts = Counter(ngrams(data['Text'][index].split(), 2))
for n in ngram_counts.most_common(10):
    print(n)
```

## Term Frequency


Term Frequency is a measure of how often a term appears in a document. There are different ways to define this but the simplest is a raw count of the number of times each term appears.

There are other ways of defining this including a true term frequency and a log scaled definition. All three have been implemented below but the default will the raw count definition, as it matches with the remainder of the definitions in this tutorial.

|Definition|Formula|
|---|---|
|Raw Count|$$f_{t,d}$$|
|Term Frequency|$$\frac{f_{t,d}}{\sum_{t'\in d}f_{t',d}}$$|
|Log Scaled|$$\log(1+f_{t,d})$$|



```python
## Raw Count Definition
tf1 = (data['Text'][0:5]).apply(lambda x: pd.value_counts(x.split(" "))).sum(axis = 0).reset_index()

## Term Frequency Definition
#tf1 = (data['Story'][0:5]).apply(lambda x: (pd.value_counts(x.split(" ")))/len(x.split(" "))).sum(axis = 0).reset_index() 

## Log Scaled Definition
#tf1 = (data['Story'][0:10]).apply(lambda x: 1.0+np.log(pd.value_counts(x.split(" ")))).sum(axis = 0).reset_index() 

tf1.columns = ['words','tf']
tf1.sort_values(by='tf', ascending=False)[:10]
```

## Inverse Document Frequency


Inverse Document Frequency is a measure of how common or rare a term is across multiple documents. That gives a measure of how much weight that term carries.

For a more concrete analogy of this, imagine a room full of NBA players; here a 7 foot tall person wouldn't be all that shocking. However if you have a room full of kindergarten students, a 7 foot tall person would be a huge surprise.

The simplest and standard definition of Inverse Document Frequency is to take the logarithm of the ratio of the number of documents containing a term to the total number of documents.

$$-\log\frac{n_t}{N} = \log\frac{N}{n_t}$$


```python
for i,word in enumerate(tf1['words']):
    tf1.loc[i, 'idf'] = np.log(data.shape[0]/(len(data[data['Text'].str.contains(word)])))

tf1[:10]
```

## Term Frequency – Inverse Document Frequency ([TF-IDF](https://en.wikipedia.org/wiki/Tf%E2%80%93idf))


Term Frequency – Inverse Document Frequency (TF-IDF) is a composite measure of both Term Frequency and Inverse Document Frequency.

From [Wikipedia](https://en.wikipedia.org/wiki/Tf%E2%80%93idf):
"A high weight in TF–IDF is reached by a high term frequency (in the given document) and a low document frequency of the term in the whole collection of documents; the weights hence tend to filter out common terms"

More concisely, a high TD-IDF says that a word is very important in the documents in which it appears.

There are a few weighting schemes for TF-IDF. Here we use scheme (1).

|Weighting Scheme|Document Term Weight|
|---|---|
|(1)|$$f_{t,d}\cdot\log\frac{N}{n_t}$$|
|(2)|$$1+\log(f_{t,d})$$|
|(3)|$$(1+\log(f_{t,d}))\cdot\log\frac{N}{n_t}$$|

```python
tf1['tfidf'] = tf1['tf'] * tf1['idf']
tf1.sort_values(by='tfidf', ascending=False)[:10]
```

It is worth noting that the *sklearn* library has the ability to directly calculate a TD-IDF matrix.

```python
from sklearn.feature_extraction.text import TfidfVectorizer
tfidf = TfidfVectorizer(max_features=1000, lowercase=True, analyzer='word',
 stop_words= 'english',ngram_range=(1,1))
data_vect = tfidf.fit_transform(data['Text'])

data_vect
```

## Similarity

```python
from collections import Counter
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.metrics.pairwise import cosine_similarity
import warnings
warnings.filterwarnings("ignore", category=FutureWarning) # This suppresses a warning from scikit learn that they are going to update their code
```

One thing we can look at is how similar two texts are. This has a practical use when looking for plagiarism, but can also be used to compare author's styles. To do this there are a few ways we can measure similarity.


First we need to set up our two sets of texts. Here we have the ability to choose the size of our sets and whether we want the first n texts from our full data set or just a random sample. Keep in mind that if you want to use two dissimilar sets, you won't have a control value (something x itself).

```python
size=10
```

```python
## First n by First n
set1 = data[["Index",'Text','Title']][:size]
set2 = data[["Index",'Text','Title']][:size]

## Random X Itself
#set1 = data[["Index",'Story','Title']].sample(size)
#set2 = set1

## First n by Random
#set1 = data[["Index",'Story','Title']][:size]
#set2 = data[["Index",'Story','Title']].sample(size)

## Random X Random
#set1 = data[["Index",'Story','Title']].sample(size)
#set2 = data[["Index",'Story','Title']].sample(size)
```

```python
#To let us do a "cross join": Every row in one gets matched to all rows in the other
set1['key']=1 
set2['key']=1

similarity = pd.merge(set1, set2, on ='key', suffixes=('_1', '_2')).drop("key", 1)
```

### Jaccard Similarity


The first is using a metric called the [Jaccard Index](https://en.wikipedia.org/wiki/Jaccard_index). This is just taking the intersection of two sets of things (in our case, words or n-grams) and dividing it by the union of those sets. This gives us a metric for understanding how the word usage compares but doesn't account for repeated words since the union and intersections just take unique words. One advantage though is that we can easily extend the single word similarity to compare bi-grams and other n-grams if we want to examine phrase usage.

$$S_{J}(A,B)=\frac{A \cap B}{A \cup B}$$


```python
def jaccard(row, n=1):
    
    old=row['Text_1']
    new=row['Text_2']
    
    old_n_grams = [tuple(el) for el in TextBlob(old).ngrams(n)]
    new_n_grams = [tuple(el) for el in TextBlob(new).ngrams(n)]
        
    union = list(set(old_n_grams) | set(new_n_grams))
    intersection = list(set(old_n_grams) & set(new_n_grams))
    
    lu = len(union)
    li = len(intersection)
    
    return (li/lu,li,lu)
```

```python
for i in [1,2]: # Add values to the list for the n-gram you're interested in
    similarity['Jaccard_Index_for_{}_grams'.format(i)]=similarity.apply(lambda x: jaccard(x,i)[0],axis=1)
```

```python
similarity['Intersection']=similarity.apply(lambda x: jaccard(x)[1],axis=1)
```

```python
similarity['Union']=similarity.apply(lambda x: jaccard(x)[2],axis=1)
```

```python
similarity.head()
```

### Cosine Similarity


The second metric we can use is [Cosine Similarity](https://en.wikipedia.org/wiki/Cosine_similarity), however there is a catch here. Cosine similarity requires a vector for each word so we make a choice here to use term frequency. You could choose something else, inverse document frequency or tf-idf would both be good choices. Cosine similarity with a term frequency vector gives us something very similar to the Jaccard Index but accounts for word repetition. This makes it better for tracking word importance between two texts.

$$S_{C}(v_1,v_2)=cos(\theta)=\frac{v_1\cdot v_2}{||v_1||\times||v_2||}$$

```python
def get_cosine_sim(str1,str2): 
    vectors = [t for t in get_vectors([str1,str2])]
    return cosine_similarity(vectors)
    
def get_vectors(slist):
    text = [t for t in slist]
    vectorizer = CountVectorizer(text)
    vectorizer.fit(text)
    return vectorizer.transform(text).toarray()

def cosine(row):
    
    old=row['Text_1']
    new=row['Text_2']
    
    return get_cosine_sim(old,new)[0,1]   
```

```python
similarity['Cosine_Similarity']=similarity.apply(lambda x: cosine(x),axis=1)
```

```python
similarity.head()
```

### Visualize Similarity

```python
metric = 'Cosine_Similarity'
#metric = 'Jaccard_Index_for_1_grams'
```

```python
import numpy as np 
import matplotlib.pyplot as plt

index = list(similarity['Index_1'].unique())
columns = list(similarity['Index_2'].unique())
df = pd.DataFrame(0, index=index, columns=columns)

for i in df.index:
    sub = similarity[(similarity['Index_1']==i)]
    for col in df.columns:
        df.loc[i,col]=sub[sub['Index_2']==col][metric].iloc[0]
        
plt.pcolor(df)
plt.yticks(np.arange(0.5, len(df.index), 1), df.index)
plt.xticks(np.arange(0.5, len(df.columns), 1), df.columns)
plt.show()
```

```python
similarity[['Title_1','Index_1','Title_2','Index_2',metric]].sort_values(by=metric,ascending=False)
```

## [Bag of Words](https://en.wikipedia.org/wiki/Bag-of-words_model)


[Bag of Words](https://en.wikipedia.org/wiki/Bag-of-words_model) a way to represent text based on the idea that similar texts will contain similar vocabulary. There is a lot to this model and we provide merely a simple implementation of it here.

```python
from sklearn.feature_extraction.text import CountVectorizer
bow = CountVectorizer(max_features=1000, lowercase=True, ngram_range=(1,1),analyzer = "word")
data_bow = bow.fit_transform(data['Text'])
data_bow
```

## Sentiment Analysis


Sentiment is a way of measuring the overall positivity or negativity in a given text.

To do this we will use the built in sentiment function in the *TextBlob* package. This function will return the polarity and subjectivity scores for each data chunk.

```python
data['Text'][:5].apply(lambda x: TextBlob(x).sentiment)
```

Focusing on the polarity score, we are able to see the overall sentiment of each data chunk. The closer to 1 the more positive and the closer to -1 the more negative.

```python
data['sentiment'] = data['Text'].apply(lambda x: TextBlob(x).sentiment[0] )
data[['Text','sentiment']].head()
```

Here we have textted the sentiment scores for the first 10 chunks.

Notice they tend to be positive but not exceedingly so.

```python
plot_1 = data[['sentiment']][:10].plot(kind='bar',)
```

Now we have sorted and textted all of the sentiment scores for the chunks in our database.

We can clearly see that most of the text data is positive but not overwhelmingly so (as seen by the long tail of the distribution). However, the parts that are negative tend to be more polarized than the positive ones (a shorter tail and sharper peak).

```python
plot_2 = data[['sentiment']].sort_values(by='sentiment', ascending=False).plot(kind='bar')
```

## Using TF-IDF and Machine Learning


This is significantly more advanced than the rest of the tutorial. This takes the TF-IDF matrix and applies a [k-means clustering algorithm](https://en.wikipedia.org/wiki/K-means_clustering). This groups the texts into clusters of similar terms from the TF-IDF matrix. This algorithm randomly seeds X "means", the values are then clustered into the nearest mean. The centroid of the values in each cluster then becomes the new mean and the process repeats until a convergence is reached.

```python
import matplotlib.pyplot as plt
import matplotlib
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.cluster import KMeans
from sklearn.decomposition import PCA
from sklearn.manifold import TSNE

groups = 30

num_clusters = groups
num_seeds = groups
max_iterations = 300

cmap = matplotlib.cm.get_cmap("nipy_spectral", groups) # Builds a discrete color mapping using a built in matplotlib color map

c = {}
for i in range(cmap.N): # Converts our discrete map into Hex Values
    rgba = cmap(i)
    c.update({i:matplotlib.colors.rgb2hex(rgba)})

labels_color_map=c

pca_num_components = 2
tsne_num_components = 2

# calculate tf-idf of texts
tfidf = TfidfVectorizer(max_features=1000, lowercase=True, analyzer='word',stop_words= 'english',ngram_range=(1,1))
tf_idf_matrix = tfidf.fit_transform(data['Text'])

# create k-means model with custom config
clustering_model = KMeans(
    n_clusters=num_clusters,
    max_iter=max_iterations,
    precompute_distances="auto",
    n_jobs=-1
)

labels = clustering_model.fit_predict(tf_idf_matrix)
#print(labels)

X = tf_idf_matrix.todense()

# ----------------------------------------------------------------------------------------------------------------------

reduced_data = PCA(n_components=pca_num_components).fit_transform(X)
# print(reduced_data)

import matplotlib.patches as mpatches
legendlist=[mpatches.Patch(color=labels_color_map[key],label=str(key))for key in labels_color_map.keys()]

fig, ax = plt.subplots()
for index, instance in enumerate(reduced_data):
    #print(instance, index, labels[index])
    pca_comp_1, pca_comp_2 = reduced_data[index]
    color = labels_color_map[labels[index]]
    ax.scatter(pca_comp_1, pca_comp_2, c=color)
plt.legend(handles=legendlist)
plt.show()



```

```python
title_groups = np.transpose([labels,data['Title'],data['Author'],data['Index']])
```

These are the titles of the texts in each cluster. Keep in mind that each time you run the algorithm, the randomness in generating the initial means will result in different clusters.

```python
for i in range(len(title_groups)):
    data.loc[i,'Group'] = title_groups[i][0]
```

This is how the groups break down by number of texts in each.

```python
g_counts = data['Group'].value_counts()
ss = min(g_counts)
g_counts
```

Here we can look at a sample of the titles in a particular group and the TF-IDF data for that group.

```python
grp=13
data[data['Group']==grp]['Title'].sample(ss)
```

```python
group_ids = list(data[data['Group']==grp]['Index'])
group_tfidf = data[data['Index'].isin(group_ids)]['Text'].apply(lambda x: pd.value_counts(x.split(" "))).sum(axis = 0).reset_index()

group_tfidf.columns = ['words','tf']
group_tfidf.sort_values(by='tf', ascending=False)[:10]

for i,word in enumerate(group_tfidf['words']):
    group_tfidf.loc[i, 'idf'] = np.log(data.shape[0]/(len(data[data['Text'].str.contains(word)])))

group_tfidf['tfidf'] = group_tfidf['tf'] * group_tfidf['idf']
group_tfidf.sort_values(by='tfidf', ascending=False)[:10]
```

```python
text_index = 0
pd.Series(' '.join(data[data['Index']==text_index]['Text']).split()).value_counts()[:10]
```

Here we can look at all the groups along with the authors and the index for each story.

```python
for i in range(groups):
    print("")
    print("#### {} ###".format(i))
    print("")
    for el in title_groups:
        if el[0]==i:
            print("{} --- {} --- #{}".format(el[1],str(el[2]).strip(), el[3]))
```

```python

```
