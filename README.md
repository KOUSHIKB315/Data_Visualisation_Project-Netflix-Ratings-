# Data_Visualisation_Project-Netflix-Ratings-


NETFLIX PROJECT


import matplotlib.pyplot as plt  :- 
                                                             Here we are importing matplotlib library in python from which we are importing pyplot module. Now  Matplotlib is a comprehensive library for creating static, interactive, and animated visualizations in Python. It provides a wide variety of plotting options, including line plots, scatter plots, bar plots, histograms, and more. 
Here we are using matplotlib for data visualization of our data outputs.
Pyplot :- The pyplot module is a collection of functions in Matplotlib that make it easy to create common types of plots quickly. It provides a simple and convenient interface for creating figures, axes, and various types of plots.
We are using this module here for a convenient interface for creating the plots.
We summarized it as “plt” to make it easy to call.
Import pandas as pd :- 
                                             We are using pandas library here as Pandas is a powerful and widely-used open-source data manipulation and analysis library for Python. It provides data structures for efficiently storing and manipulating large datasets and tools for working with structured data seamlessly.
And we are using it because we need to analyze the data in the provided data set.
We are making it easier to call by summarizing pandas as “pd  
Import numpy as np :-
                                    We are importing NumPy, which stands for Numerical Python, is a fundamental package for scientific computing in Python. It provides support for large, multi-dimensional arrays and matrices, along with a wide collection of high-level mathematical functions to operate on these arrays.
We are using it because of efficient array processing and integration with another libreries  and mathematical functions.
np is abbreviation of numpy.
Import seaborn as sns :-
                                              We use seaborn library brecause Seaborn is a Python data visualization library based on Matplotlib. It provides a high-level interface for creating attractive and informative statistical graphics. While Matplotlib is very powerful, it can sometimes be a bit verbose or complex for common statistical plots, which is where Seaborn does better.
We are using it here to plot the statistical plots here. And it integrates with pandas. 
sns is abbreviation of seaborn 
from google.colab import drive:-
                                                                here we are importing drive module from the google colab pakage . This module contains functionality related to Google Drive integration within Colab.
drive.mount('/content/drive'):-
This line calls the mount function from the drive module to mount the Google Drive on the Colab environment. When we run this code, it will prompt us to authorize Colab to access the Google Drive. After authorization, the Google Drive will be mounted at the specified path, which in this case is '/content/drive'.
df = pd.read_csv("/content/drive/MyDrive/Netflix_Dataset_Rating.csv"):- 
This line reads a CSV (Comma-Separated Values) file from the specified path and creates a DataFrame named df to store the data. The pd.read_csv function is a Pandas function used for reading data from a CSV file. In this case, the CSV file is located in the Google Drive path "/content/drive/MyDrive/Netflix_Dataset_Rating.csv".

"/content/drive/MyDrive/Netflix_Dataset_Rating.csv":- 
This is the file path to the CSV file in your Google Drive. Adjust this path according to the location of your dataset in Google Drive.


data.info() :-
this function in Python, when used with a Pandas DataFrame, provides a concise summary of the DataFrame. This includes information about: 1. Index range  2.column -information  3. Non-null counts   4. data types  5. Memory usage 
it gives summarized ovferview of the given file.
We use it because we want to have an overview of the file.
sample_movieID = df[df["Movie_ID"]==3]
sample_movieID :-
this code snippet filters df to create a new DataFrame sample_movieID that contains only the rows where the value in the "Movie_ID" column is 3. 
sorted_User_ID=sample_movieID.sort_values('User_ID')
sorted_User_ID :-
the code sorts the DataFrame sample_movieID by the 'User_ID' column in ascending order and stores the sorted DataFrame in a new variable called sorted_User_ID. The sorted DataFrame is then displayed.
Upmost_User_ID=sorted_User_ID.head()
Upmost_User_ID :-
Upmost_User_ID DataFrame now contains the first 5 rows of the sorted_User_ID DataFrame. This is  useful for the quickly inspecting the beginning of a large sorted dataset to understand its structure or to perform a quick check of the sorting results. 
.head() method is a built-in function in Pandas that is used to select the first few rows of a DataFrame. By default, if no argument is given to head(), it selects the first 5 rows. 
x=Upmost_User_ID['User_ID']:- This line creates a variable x, which stores the values from the 'User_ID' column of the Upmost_User_ID DataFrame. These values will be used as the x-coordinates for the plot.
y=Upmost_User_ID['Rating']:-  here this line creates a variable y, which contains the values from the 'Rating' column of the Upmost_User_ID DataFrame. These will serve as the y-coordinates for the plot. 
plt.plot(x, y, marker='.'):-  Here, plt.plot is a function from Matplotlib that creates a line plot.

x, y are the data points to be plotted. x is plotted on the horizontal axis, and y on the vertical axis.
marker='.' specifies the type of marker used for each data point.
plt.title("Uppermost User Rating"):- here this line adds a title to the plot. The title here is "Uppermost User Rating". 
plt.xlabel("User ID") and plt.ylabel("Rating"): - These lines add labels to the x-axis and y-axis, respectively. 'User ID' is set as the label for the x-axis, and 'Rating' for the y-axis. 
sorted_User_ID.tail():- we are taking the last 5 rows in the sorted_User_ID. 
.tail() is used for taking last n numbers of rows.
lowermost_User_ID = sorted_User_ID.tail():-

This line of code assigns the result of sorted_User_ID.tail() to a new DataFrame named lowermost_User_ID.
As a result, lowermost_User_ID contains the last 5 rows of the sorted_User_ID DataFrame.
lowermost_User_ID:-

This line displays the DataFrame lowermost_User_ID.
by this we can view and verify the contents of these last few rows.
x=lowermost_User_ID['User_ID']:-  here this line assigns the values from the 'User_ID' column of the lowermost_User_ID DataFrame to the variable x. These values will be used as the x-coordinates for the plot.
y=lowermost_User_ID['Rating']:- here this line does the same for the 'Rating' column, assigning its values to the variable y, which will serve as the y-coordinates for the plot.
plt.plot(x, y, marker='.'): - This line creates the line plot.
x, y are the data points to be plotted, with x being the horizontal axis and y the vertical axis. 
plt.title("Lowermost User Rating"):- Adds the title "Lowermost User Rating" to the plot.

plt.xlabel("User ID") and plt.ylabel("Rating"):- These lines add labels to the x-axis and y-axis, respectively, with 'User ID' as the label for the x-axis and 'Rating' for the y-axis.
fivestar_rating = sample_movieID[sample_movieID["Rating"]==5]
fivestar_rating:- sample_movieID["Rating"]==5 is a condition that checks which rows in the Rating column of sample_movieID have a value of 5. This condition generates a boolean Series where each item is True if the Rating is 5, and False otherwise.
fivestar_rating DataFrame contains only those rows from sample_movieID where the movie has a rating of 5. This operation is typical in data analysis when we need to extract and examine a subset of the data based on identifying all instances of a particular rating.
fivestar_rating.describe():-fivestar_rating is a filtered DataFrame containing only rows where the Rating is 5, the describe() method will provide these statistical summaries for this subset. However, considering that all ratings in this DataFrame are 5, the mean, min, 25%, 50%, 75%, and max values for the Rating column will all be 5. The standard deviation will be 0 as there is no variation in the Rating. Other numerical columns in the DataFrame, if any, will be summarized with their respective statistics.  
fourstar_rating = sample_movieID[df["Rating"]==4]
fourstar_rating :-it creates a dataframe  fourstar_rating, which contains rows from the sample_movieID DataFrame where the Rating is 4. 
fourstar_rating.describe():-fourstar_rating.describe() is a helpful method for getting a quick statistical overview of the fourstar_rating DataFrame, particularly useful for understanding the distribution of numeric data within this filtered subset.
threestar_rating = sample_movieID[df["Rating"]==3]
threestar_rating :- threestar_rating will be a DataFrame containing rows from sample_movieID where the movies have a 3-star rating.
This DataFrame can be used for further analysis or manipulation specific to the subset of data that meets the condition of having a 3-star rating. 
threestar_rating.describe() :- describe() method will provide these statistical summaries for this subset of data. If Rating is the only numeric column and its value is consistently 3, the mean, min

, 25%, 50%, 75%, and max values for the Rating column will all be 3, and the standard deviation will be 0, indicating no variation in the Rating. However, if there are other numeric columns in the threestar_rating DataFrame, the describe() method will provide their respective statistical summaries as well. 
twostar_rating = sample_movieID[df["Rating"]==2]
twostar_rating  :- twostar_rating will be a DataFrame containing rows from sample_movieID where the movies have a 2-star rating.
This subset of data can be
used for further analysis specific to the 2-star ratings. 
twostar_rating.describe():-describe() method will provide these statistical summaries for all numeric columns in the DataFrame.
If Rating is the only numeric column, and all its values are 2 (given the filtering criteria), then the mean, min, 25%, 50%, 75%, and max values for the Rating column will all be 2, and the standard deviation will be 0, indicating no variation in the Rating. 

onestar_rating = sample_movieID[df["Rating"]==1]
onestar_rating :- onestar_rating will be a DataFrame that contains rows from sample_movieID in which movies received a 1-star rating.
onestar_rating.describe():-describe() will provide statistical summaries for these columns. This can offer insights into the distribution and central tendencies of these features within the subset of data corresponding to 1-star ratings.
