# Nasa Project - Maria Yagual
#libraries
from collections import Counter
from matplotlib import pyplot as plt
import itertools

# open the file
file = open("NASA_access_log_July")

# create empty list to add values later on
ipAddress = []
dateT = []
timeOne = []  # list will be use to split after split the
directory = []

# for loops go through the entire list
#try and except statement due to Unicode Error
try:
    for lines in file:
        split_data = lines.split(" ")
        ipAddress.append(split_data[0])  # adds value to list
        dateT.append(split_data[3])  # adds value to list
        directory.append(split_data[6])  # adds value to list
except UnicodeError:
    pass
print(ipAddress)  # printing updated list
print(dateT)  # printing updated list
print(directory)  # printing updated list

# GRAPH 1
# Counting Values - First
ipAddressCount = Counter(ipAddress)
print(ipAddressCount) #Count how many times the DNS entered NASA

#iterating through list |only 10 dns will be displayed in graph|
sites = 10
ip_dict = dict(itertools.islice(ipAddressCount.items(), sites))

#graph format for 1
plt.rcParams["figure.figsize"] = [7.50, 3.50] #parameters
plt.rcParams["figure.autolayout"] = True
plt.title('How many times have these DNS entered NASA?') #title of graph
plt.xlabel('DNS - IP Address') # name for x axis
plt.ylabel('Times visited NASA') # name for y axis
plt.xticks(rotation = 15) # x-axis name rotated for better organization
plt.ylim(0,10) # limit of x and y-axis

#bar graph
plt.bar(sorted(ip_dict),range(len(ip_dict)), color='purple', alpha=0.5) # sorted from lowest to highest within 10 dns
plt.subplot() #function to display both graphs
plt.show()



# Graph 2 - Line Plot
# Counting Values - directory
directoryCount = Counter(directory)
print(directoryCount)

#iterating through list |only 10 dns will be displayed in graph|
sites = 10
dir_dict = dict(itertools.islice(directoryCount.items(), sites))


#graph format for 2
plt.title('How many times have specific route been visited ?', fontsize=15, color= 'darkmagenta', fontweight='bold') #title
plt.xlabel('Route/URL') # name for x axis
plt.ylabel('Amount of times visited') # name for y axis
plt.xticks(rotation = 15) # x-axis name rotated for better organization
plt.ylim(0,10) # limit of x and y axis
plt.grid() #adding grid to line plot

#line plot graph
plt.plot(sorted(dir_dict),range(len(dir_dict)),color='mediumorchid', alpha=1) # sorted from lowest to highest within 10 routes
plt.subplot()
plt.show()
