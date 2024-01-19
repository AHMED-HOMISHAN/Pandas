
# Let's go through each part of the code and explain what it does:

```python
import pandas as pd
df = pd.read_csv('Data.csv')
```
- Imports the pandas library and reads a CSV file named 'Data.csv' into a DataFrame called `df`.

```python
print(df.to_string()) 
```
- Prints the entire DataFrame as a string.

```python
df.head()
```
- Displays the first few rows of the DataFrame `df` to provide a quick overview of the data.

```python
df.tail()
```
- Displays the last few rows of the DataFrame `df`.

```python
df.info()
```
- Prints a concise summary of the DataFrame, including information on data types, non-null values, and memory usage.

```python
df["raisedhands"].fillna(df["raisedhands"].mode()[0], inplace=True)
```
- Fills missing values in the "raisedhands" column with the mode (most frequently occurring value) of that column. The `inplace=True` parameter modifies the DataFrame in place.

```python
df["raisedhands"].mean()
```
- Calculates the mean of the "raisedhands" column.

```python
df["raisedhands"].mode()
```
- Finds the mode (most frequently occurring value) of the "raisedhands" column.

```python
df.index
```
- Returns the index of the DataFrame.

```python
for index in df.index:
    if df.loc[index, "VisITedResources"] > 100:
        print(df.loc[index])
```
- Iterates through the rows of the DataFrame and prints the rows where the "VisITedResources" column value is greater than 100.

```python
for i in df.index:
    if df.loc[i, "VisITedResources"] > 100:
        df.loc[i, "VisITedResources"] = df["VisITedResources"].mode()[0]
```
- Similar to the previous loop, but in this case, it replaces the values in the "VisITedResources" column that are greater than 100 with the mode of that column.

```python
print(df.duplicated())
```
- Checks for duplicate rows in the DataFrame and prints a boolean Series indicating whether each row is a duplicate.

```python
df.drop_duplicates(inplace=True)
```
- Removes duplicate rows from the DataFrame in place.

In summary, this script loads a CSV file into a DataFrame, handles missing values, explores some basic statistics, identifies and modifies outliers in one column, and removes duplicate rows.

# Attributes Od DataSet
1 Gender - student's gender (nominal: 'Male' or 'Female’)

2 Nationality- student's nationality (nominal:’ Kuwait’,’ Lebanon’,’ Egypt’,’ SaudiArabia’,’ USA’,’ Jordan’,’
Venezuela’,’ Iran’,’ Tunis’,’ Morocco’,’ Syria’,’ Palestine’,’ Iraq’,’ Lybia’)

3 Place of birth- student's Place of birth (nominal:’ Kuwait’,’ Lebanon’,’ Egypt’,’ SaudiArabia’,’ USA’,’ Jordan’,’
Venezuela’,’ Iran’,’ Tunis’,’ Morocco’,’ Syria’,’ Palestine’,’ Iraq’,’ Lybia’)

4 Educational Stages- educational level student belongs (nominal: ‘lowerlevel’,’MiddleSchool’,’HighSchool’)

5 Grade Levels- grade student belongs (nominal: ‘G-01’, ‘G-02’, ‘G-03’, ‘G-04’, ‘G-05’, ‘G-06’, ‘G-07’, ‘G-08’, ‘G-09’, ‘G-10’, ‘G-11’, ‘G-12 ‘)

6 Section ID- classroom student belongs (nominal:’A’,’B’,’C’)

7 Topic- course topic (nominal:’ English’,’ Spanish’, ‘French’,’ Arabic’,’ IT’,’ Math’,’ Chemistry’, ‘Biology’, ‘Science’,’ History’,’ Quran’,’ Geology’)

8 Semester- school year semester (nominal:’ First’,’ Second’)

9 Parent responsible for student (nominal:’mom’,’father’)

10 Raised hand- how many times the student raises his/her hand on classroom (numeric:0-100)

11- Visited resources- how many times the student visits a course content(numeric:0-100)

12 Viewing announcements-how many times the student checks the new announcements(numeric:0-100)

13 Discussion groups- how many times the student participate on discussion groups (numeric:0-100)

14 Parent Answering Survey- parent answered the surveys which are provided from school or not
(nominal:’Yes’,’No’)

15 Parent School Satisfaction- the Degree of parent satisfaction from school(nominal:’Yes’,’No’)

16 Student Absence Days-the number of absence days for each student (nominal: above-7, under-7)

The students are classified into three numerical intervals based on their total grade/mark:
Low-Level: interval includes values from 0 to 69,

Middle-Level: interval includes values from 70 to 89,

High-Level: interval includes values from 90-100.
