# -Final-Project-Info

Data Source and Collections
Where are you getting it from?
We obtained our primary data from the boxoffice-api package, which retrieves box office data from public film revenue databases, such as The Numbers and IMDb Box Office Charts.

How did you get it?
We wrote Python scripts using the boxoffice-api in a Jupyter Notebook. For each week (Weeks 17–21, 2019), we sent requests via the API to retrieve a dataset containing revenue, average per theater, and theater count. Each dataset was stored as a JSON, then converted into a pandas DataFrame.

What data type is it?
The data came as JSON (JavaScript Object Notation), which we converted into a pandas DataFrame for analysis. Columns included:

Movie title
Gross revenue (string → float)
Average per theater
Number of theaters
Week number

Restrictions of that data type (gaps, ethics, etc.):

JSON formats are flexible but messy—currency values came as strings with $, which required cleaning
Some weeks had missing values, such as nulls or improperly formatted entries
No individual-level data was used, so privacy and ethics concerns were minimal
API didn’t cover international revenue, so analysis is limited to domestic (U.S.) performance.

Data Cleaning Decisions
What choices did you make?
We cleaned currency values using .str.replace('$','') and .replace(',','')
Converted those cleaned strings into numeric data using .astype(float)
Filled missing entries (NaNs) with 0 using .fillna(0)
Combined five separate weekly DataFrames into one using pandas.concat()
Dropped unrelated columns (like movie rank) to focus on the dataset
Why?

These cleaning choices were necessary for accurate math, plotting, and weekly comparisons. Without this step, we would not be able to calculate revenue changes or plot trends correctly.

What visualizations did we use?
Line graphs to show weekly revenue trends

Bar charts for theater count per week

Percentage change charts to show week-to-week drop-offs

Why did we use these?
These visualizations helped highlight:

The initial surge in revenue
The pattern of steady decline
The importance of theater availability in maintaining revenue

What other visualizations are possible?

Scatter plot comparing tweet volume vs. weekly revenue
Pie chart of Endgame vs. other top 5 movies in each week
Timeline view to show both box office and Twitter sentiment chronologically

Relevance & Broader Impact

Where is this helpful?

For film studios, to analyze movie performance beyond opening weekend
For marketers, to understand how social media affects revenue
For data analysts, to practice cleaning, merging, and visualizing real-world API data
What conclusions can others draw?
High revenue isn’t just about launch but about retention and long-term interest
Clean, well-structured data is essential to draw accurate insights
Social media activity (tweet volume, sentiment) may help predict financial success

