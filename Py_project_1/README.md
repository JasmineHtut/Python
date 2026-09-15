# Exercise 1 - Analyzing Data Science Job Demand
## Pandas Accessing datas
### Selecting data
  - df.loc[]: Select rows and columns by position or label.

## Pandas Data Cleaning
### Handling Missing Data
  - df.dropna(): Drop missing values.
  - df.fillna(): Fill missing values
  - drop_duplicates(): Remove duplicate rows.

## Pandas Data Management
  - copy(): Copy a DataFrame.
  - sample(): Random sample of items.

## Pandas Pivot Tables
  - pivot_table(): Create a pivot table as a DataFrame.
    - Syntax: pivot_table(values='column_to_aggregate', index='row_index', columns='column_index', aggfunc='mean')
  - Counting Job Titles
    - df.pivot_table(index='job_title', aggfunc='size')
  - Country & Job Title Analysis
    - df.groupby(['job_country', 'job_title'])['salary_year_avg'].agg(['max', 'median', 'min']).dropna()  

## Pandas Index Management
  - Index Attributes
    - index.name - name of the index
    - index.dtype - data type of the index
  - set_index(): Sets one or more existing columns as the index of the DataFrame. This is useful for timeseries data or when you want to index by specific attributes.

# Exercise 2 - Investigating Trending Skills
## Pandas Merge DataFrames
  - merge(): Combine DataFrames based on common columns or indices, similar to SQL joins (inner, outer, left, right).

## Pandas Concat DataFrames
  - concat(): Combine DataFrames by rows (axis = 0) or columns (axis=1).

## Pandas Exporting Data
  - to_csv(): Export DataFrame to CSV file.
  - to_excel(): Export DataFrame to Excel file.
  - to_sql(): Export DataFrame to SQL database.
  - to_parquet(): Export DataFrame to a parquet file.

## Pandas Applying Functions
  - apply(): Apply functions to columns or rows.
    - Used with lambda
      - df['salary_year_inflated'] = df['salary_year_avg'].apply(lambda salary: salary * 1.03)
     
## Pandas Explode
  - explode() - transforms each element of a list-like to a row
    - Expand list-like data within a DataFrame column into separate rows.

# Exercise 3 - Investigate High Paying Skills
## Matplotlib Formatting Charts
  - subplots(): Create multiple plots within a single figure.
    - fig, ax = plt.subplots(1,2) - Creates a figure with 1 row and 2 columns of subplots.
  - tight_layout(): automatically adjusts the spacing between subplots and the figure margins to prevent overlapping of axes labels, titles, and tick labels.
  - savefig(): Save the current figure.

## Matplotlib Pie Plots 
  - pie(): plot a pie chart.
    - plt.pie(df['data'], labels=df['category'], autopct='%1.1f%%', startangle=90, colors=['red', 'green', 'blue', 'yellow'], explode=(0.1, 0, 0, 0))

## Matplotlib Scatter Plots
  - scatter() - create a scatter plot of x vs y.
    - plt.scatter(df['x'], df['y'], s=df['size'], c=df['color'], alpha=0.5, marker='o')
  - text: Add text annotations to the plot.

## Matplotlib Advanced Customization
  - linestyle: Change the line style
  - color: Change the line color
  - colormap: Change the color sheme for all data points
  - linewidth: Change the line width
  - marker: Change the marker style
  - markersize: Change the marker size
  - xlim: Set the x-axis view limits
  - ylim: Set the y-axis view limits
  - grid: Add a grid to the plot

## Matplotlib Histograms
  - hist(): plot a histogram.
    - hist(x, bins=None, range=None)
   
## Matplotlib Box Plots
  - boxplot(): plot a box plot
    - boxplot(column=['column1', 'column2', ...], by=None, vert=False)
