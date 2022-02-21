# Week-3

# Creating a pandas Series object that holds the cumulative miles of a cyclist at the end of each day, while travelling from New York to Key West, Florida.
import pandas as pd

import numpy as np

# We need to initially create at numpy array which will be used to store the cumulative miles at the end of each day. In this scenario the total distance travelled will be approximately 1,436 miles for the cyclist to get to his destination.

Accumulated_miles = np.array([55, 120, 180, 215, 275, 325, 350, 400, 480, 536, 597, 615, 675, 750, 797, 834, 885, 920, 975, 1030, 1080, 1111, 1185, 1215, 1275, 1310, 1366, 1400, 1436])

# Converting to a panda series

Cumulative_series = pd.Series(Accumulated_miles)

#Creating an additional array to store the miles travelled each day. 

total_distance_per_day = np.array([Cumulative_series[0]])

# We now use a for loop that will iterate throughout the series and calculate the miles travelled per day.

for i in range(1, len(Cumulative_series)):

    total_distance_per_day = np.append(total_distance_per_day, Cumulative_series[i]-Cumulative_series[i-1])

#Converting the new array into a series and displaying the distance travelled each day by cyclist on his journey to Florida. 

print("Miles travelled by the cyclist each day:")

print(pd.Series(total_distance_per_day))
