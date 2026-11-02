### Experiment 1: EDA in IPL Dataset
### Aim:
To perform Exploratory Data Analysis (EDA) on the IPL matches dataset and derive insights about matches per season, winning teams, toss decisions, and top venues.

### Algorithm / Procedure:

**1.Import Libraries**
  Import pandas for data handling.
  Import matplotlib and seaborn for visualization.

**2.Load Dataset**
  Use pd.read_csv() to load the IPL matches dataset.
  Check dataset shape using .shape.
  View first 5 rows using .head().

**3.Matches per Season (Univariate Analysis)**
  Group data by season and count matches.
  Plot a bar chart to visualize growth/decline in matches.

**4.Top Winning Teams (Univariate Analysis)**
  Use value_counts() on the winner column.
  Plot top 5 winning teams in a bar chart.

**5.Toss Decisions (Univariate Analysis)**
  Count toss decision preferences (bat vs field).
  Plot results using a bar chart.
  
**6.Top Venues (Univariate Analysis)**
  Count matches per venue.
  Display top 5 venues with a horizontal bar chart.

**7.Draw Insights**
  Observe patterns in toss decisions.
  Identify teams with consistent winning trends.

```
DEVELOPED BY: HEMALISHA T
REG NO:       212225040123
```
  
### Program

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("matches.csv")

print("Dataset Shape:", df.shape)
print("\nFirst 5 Rows:")
print(df.head())
```

<img width="550" height="518" alt="image" src="https://github.com/user-attachments/assets/2dd37f42-7be6-4aa6-be43-8d108997b7f8" /> <br/>
<br/>
<br/>
Matches per Season
```python
plt.figure(figsize=(12, 5))
matches_per_season = df.groupby('season').size()

sns.barplot(x=matches_per_season.index,
            y=matches_per_season.values)

plt.title("Number of IPL Matches per Season")
plt.xlabel("Season")
plt.ylabel("Number of Matches")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

<img width="817" height="330" alt="image" src="https://github.com/user-attachments/assets/41ebf003-451a-44c7-a771-2a8759321553" /><br/>
<br/>
<br/>
Top 5 Winning Teams
```python
plt.figure(figsize=(10, 5))
top_teams = df['winner'].value_counts().head(5)

sns.barplot(x=top_teams.index, y=top_teams.values)

plt.title("Top 5 Winning Teams in IPL")
plt.xlabel("Teams")
plt.ylabel("Number of Wins")
plt.xticks(rotation=30, ha='right')
plt.tight_layout()
plt.show()
```
<img width="832" height="397" alt="image" src="https://github.com/user-attachments/assets/7e63b45e-ca11-4160-bc42-4d35d1804bad" /> <br/>
<br/>
<br/>
Toss Decisions
```python
plt.figure(figsize=(7, 5))
toss_decisions = df['toss_decision'].value_counts()

plt.bar(toss_decisions.index, toss_decisions.values)

plt.title("Toss Decision Preferences")
plt.xlabel("Toss Decision")
plt.ylabel("Number of Matches")
plt.show()
```
<img width="832" height="525" alt="image" src="https://github.com/user-attachments/assets/b4ab7b8c-8c2f-49d0-b8de-00e657ee2a9d" /> <br/>
<br/>
<br/>
Top 5 Venues
```python
plt.figure(figsize=(10, 5))
top_venues = df['venue'].value_counts().head(5)

sns.barplot(x=top_venues.values, y=top_venues.index)

plt.title("Top 5 IPL Stadiums Hosting Maximum Matches")
plt.xlabel("Number of Matches")
plt.ylabel("Stadiums")
plt.tight_layout()
plt.show()
```
<img width="828" height="407" alt="image" src="https://github.com/user-attachments/assets/8db855fb-b12d-42b6-8ab9-5b33284341f2" /> <br/>
<br/>
<br/>
Display Stadiums Hosting Maximum Matches
```python
print("\nTop 5 Stadiums Hosting Maximum Matches:")
print(top_venues)
```
<img width="422" height="177" alt="image" src="https://github.com/user-attachments/assets/2ce0062a-8b6d-4842-855b-4b1ddbaeefa2" /> <br/>
<br/>
<br/>
Draw Insights
```python
print("\nEDA INSIGHTS")
print("Total Matches:", len(df))
print("Most Successful Team:", df['winner'].value_counts().idxmax())
print("Most Preferred Toss Decision:", toss_decisions.idxmax())
print("Stadium Hosting Maximum Matches:", top_venues.idxmax())
```
<img width="402" height="120" alt="image" src="https://github.com/user-attachments/assets/23cd0c69-b2af-47fa-a702-d068eb1c7587" />  

### Result
This experiment is executed successfully.
