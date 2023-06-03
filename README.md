# python-CHALLENGE
# Import the pathlib and csv library
from pathlib import Path
import csv
import os 

current_dir = os.getcwd() # get current working dir
print(current_dir)

path_budget_data = os.path.join(current_dir,"budget_data.csv") # get the csv file path
print(path_budget_data)



# Initialize variable to hold profits
profits = 0

# Initialize line_num variable
line_num = 0

# Initialize metric variables
max_Profit = 0
min_Profit = 0
avg_Profit = 0
total_Profit = 0
count_profits = 0
changes = []
max_change = 0
max_month = ""
min_change = 0
min_month = ""

# Open the input path as a file object
with open(path_budget_data, 'r') as csvfile:

 # Print the datatype of the file object
    print(type(csvfile))
 # Pass in the csv file to the csv.reader() function
    # (with ',' as the delmiter/separator) and return the csvreader object
    csvreader = csv.reader(csvfile, delimiter=',')
    # Print the datatype of the csvreader
    print(type(csvreader))
    # Go to the next row from the start of the file
    # (which is often the first row/header) and iterate line_num by 1
    header = next(csvreader)
    line_num += 1
    # Print the header
    print(f"{header} <---- HEADER")
    # Read each row of data after the header
    for row in csvreader:
        # Print the row
        
        # Set Profit variable equal to the value in the 2nd column of each row
        profit = int(row[1])
        profits += profit
        count_profits += 1
        
        if count_profits > 1:
            change = profit - previous 
            changes.append(change)
            if change > max_change:
                max_change = change 
                max_month = row[0]
            if change < min_change:
                min_change = change
                min_month = row[0]
            
        previous = profit
# Sum the total and count variables
 
    

# Logic to determine min and max Profit
   
print(f"Total Months: {count_profits}")
print(f"Total: ${profits}")
print(f"Average  Change: ${sum(changes)/len(changes)}")
print(f"Greatest Increase in Profits: {max_month} (${max_change})")
print(f"Greatest Decrease in Profits: {min_month}  (${min_change})")

/Users/amarsen/Downloads
/Users/amarsen/Downloads/budget_data.csv
<class '_io.TextIOWrapper'>
<class '_csv.reader'>
['Date', 'Profit/Losses'] <---- HEADER
Total Months: 86
Total: $38382578
Average  Change: $-2315.1176470588234
Greatest Increase in Profits: Feb-2012 ($1926159)

Greatest Decrease in Profits: Sep-2013  ($-2196167)

# Reference -
Class Activities 
Git Lab examples 
