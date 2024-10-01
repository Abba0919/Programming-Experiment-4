# Programming-Experiment-4

## Overview:
Daat wrangling is converting and translating data into more useful format.

## Intended Learning Outcomes:
1. To identify the codes and functions needed in cleaning and visualizing data
2. To be able to apply and use the different codes and functions in creating a Python program that will be used in data wrangling and data visualization

   
### Output 1:
ECE BOARD EXAM PROBLEM:

1. Create the following data frames based on the format provided:
a. Filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as
Instrumentation and hometown Luzon
Before starting the code, we need to open the syntax. 
#### Input
```python
df = pd.read_excel('board2.xlsx')
df
```

Then, inputing the code that locates the marks greater than 70 withing the column of Electronics
```python
instru = df.loc[(df['Track'] == 'Instrumentation') & (df['Hometown'] == 'Luzon') & 
        (df['Electronics'] > 70), ['Name', 'GEAS', 'Electronics']].reset_index(drop=1)
instru
```
The output should look like this.

#### Output
![image](https://github.com/user-attachments/assets/788c3d43-f61c-4201-bf1b-164a078c5e90)


b. Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is
constant as Mindanao and gender Female

### Input:

```python
# Calculate the average across Math, Electronics, GEAS, and Communication
df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)

# Filter the data for female students from Mindanao with an average >= 55
mindy = df.loc[(df['Gender'] == 'Female') & 
                  (df['Hometown'] == 'Mindanao') & 
                  (df['Average'] >= 55), 
                  ['Name', 'Track', 'Electronics', 'Average']].reset_index(drop=True)

# Display the filtered data
mindy
```

### Output:
![image](https://github.com/user-attachments/assets/ff160f57-f4c6-416f-991a-7fa39cee6f52)

This code first calculates the average scores of students across four subjects—Math, Electronics, GEAS, and Communication—by computing the mean for each student and storing it in a new column called 'Average'. Then, it filters the data to select female students from Mindanao who have an average score of 55 or higher. The filtered dataset contains only relevant columns like 'Name', 'Track', 'Electronics', and 'Average', and the index is reset for clarity. Finally, the filtered data is displayed, showcasing the selected students who meet the criteria.

2. Create a visualization that shows how the different features contributes to average grade. Doeschosen track in college, gender, or hometown contributes to a higher average score?

The code begins by importing the pyplot module from matplotlib and setting up the plot size to 8x6 inches.
### Input:
```python
import matplotlib.pyplot as plt

plt.figure(figsize=(8, 6))
bar_width = 0.35
plt.title('Electronics and Average Scores of Female Students from Mindanao')
plt.bar(df['Track'], df['Average'])
plt.bar(df['Gender'], df['Average'])
plt.bar(df['Hometown'], df['Average'])
```
### Output:

![image](https://github.com/user-attachments/assets/afc35fb1-6258-4ebd-ae07-f04fb18722d4)

This code titles the plot "Electronics and Average Scores of Female Students from Mindanao." It then tries to plot three bar charts: one using 'Track' and 'Average', another using 'Gender' and 'Average', and a third using 'Hometown' and 'Average'. However, plotting 'Gender' and 'Hometown' as bar charts is problematic, as they are categorical variables that need different handling.

