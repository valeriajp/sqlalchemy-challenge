# SQLAlchemy-Challenge

# Instructions
Congratulations! You've decided to treat yourself to a long holiday vacation in Honolulu, Hawaii. To help with your trip planning, you decide to do a climate analysis about the area. The following sections outline the steps that you need to take to accomplish this task.

# Part 1: Analyze and Explore the Climate Data
In this section, you’ll use Python and SQLAlchemy to do a basic climate analysis and data exploration of your climate database. Specifically, you’ll use SQLAlchemy ORM queries, Pandas, and Matplotlib. To do so, complete the following steps:

1. Note that you’ll use the provided files (![Screen Shot 2024-12-16 at 16 40 09](https://github.com/user-attachments/assets/08f7fae9-52f2-412c-a626-c5f78419c0a6)
 and ![Screen Shot 2024-12-16 at 16 40 38](https://github.com/user-attachments/assets/19cc67c1-6032-4bbc-8d2e-b65e161441af) to complete your climate analysis and data exploration.

2. Use the SQLAlchemy ![Screen Shot 2024-12-16 at 16 41 08](https://github.com/user-attachments/assets/1bd56a42-62c1-4531-8b89-702c5a653047) function to connect to your SQLite database.

3. Use the SQLAlchemy ![Screen Shot 2024-12-16 at 16 41 30](https://github.com/user-attachments/assets/16539838-edb4-4aa2-b67d-2a634038a296) function to reflect your tables into classes, and then save references to the classes named ![Screen Shot 2024-12-16 at 16 41 56](https://github.com/user-attachments/assets/dfa0b879-d64e-4779-bf05-2427f7952c14) and ![Screen Shot 2024-12-16 at 16 42 26](https://github.com/user-attachments/assets/5bb666cb-5934-498c-8b6f-99530545267e).

4. Link Python to the database by creating a SQLAlchemy session.

IMPORTANT: Remember to close your session at the end of your notebook.

5. Perform a precipitation analysis and then a station analysis by completing the steps in the following two subsections.

# Precipitation Analysis

1.Find the most recent date in the dataset.

2. Using that date, get the previous 12 months of precipitation data by querying the previous 12 months of data. (Hint: Don’t pass the date as a variable to your query.)

3. Select only the "date" and "prcp" values.

4. Load the query results into a Pandas DataFrame. Explicitly set the column names.

5. Sort the DataFrame values by "date".

6. Plot the results by using the DataFrame plot method, as the following image shows:

![Screen Shot 2024-12-16 at 16 36 16](https://github.com/user-attachments/assets/1a88451c-1699-4f06-ac1f-caf15234aabb)

7. Use Pandas to print the summary statistics for the precipitation data.

# Station Analysis
1. Design a query to calculate the total number of stations in the dataset.

2. Design a query to find the most-active stations (that is, the stations that have the most rows). To do so, complete the following steps:

- List the stations and observation counts in descending order.
- HINT: You’ll need to use the ![Screen Shot 2024-12-16 at 16 43 08](https://github.com/user-attachments/assets/a3fa81db-ae5b-4336-bdd4-266402175219) function in your query.
- Answer the following question: which station id has the greatest number of observations?

3. Design a query that calculates the lowest, highest, and average temperatures that filters on the most-active station id found in the previous query.
4. Design a query to get the previous 12 months of temperature observation (TOBS) data. To do so, complete the following steps:
   - Filter by the station that has the greatest number of observations.
   - Query the previous 12 months of TOBS data for that station.
   - Plot the results as a histogram with ![Screen Shot 2024-12-16 at 16 39 23](https://github.com/user-attachments/assets/7a3197e3-6ad1-45c1-8aa8-65588f63efa5), as the following image shows:
     ![Screen Shot 2024-12-16 at 16 44 05](https://github.com/user-attachments/assets/f7be1eb8-b874-4e5c-8d6b-e89875c38a3f)
5. Close your session.

# Part 2: Design Your Climate App
Now that you’ve completed your initial analysis, you’ll design a Flask API based on the queries that you just developed. To do so, use Flask to create your routes as follows:

1. ![Screen Shot 2024-12-16 at 16 45 34](https://github.com/user-attachments/assets/e22f75d5-ecf7-4331-b6b8-230ada1e78ba)
   - Start at the homepage.
   - List all the available routes.
2. ![Screen Shot 2024-12-16 at 16 46 28](https://github.com/user-attachments/assets/7a84d266-7241-4105-887e-535246fd4b4d)
   - Convert the query results from your precipitation analysis (i.e. retrieve only the last 12 months of data) to a dictionary using ![Screen Shot 2024-12-16 at 16 47 59](https://github.com/user-attachments/assets/3e3d9fe4-1a4a-4845-a8f2-6bcbc6a8ceff) as the key and ![Screen Shot 2024-12-16 at 16 47 14](https://github.com/user-attachments/assets/6b353371-4550-4ebe-9806-371d557c5bad) as the value.
   - Return the JSON representation of your dictionary.
3. ![Screen Shot 2024-12-16 at 16 48 51](https://github.com/user-attachments/assets/e10cac1d-9647-462f-9f1a-a508dff56b64)
4.![Screen Shot 2024-12-16 at 16 49 11](https://github.com/user-attachments/assets/d87025b8-f722-445b-b657-57dc4fa34966)
5. ![Screen Shot 2024-12-16 at 16 49 30](https://github.com/user-attachments/assets/282e8cb7-8b85-432a-8895-8779b6f98d36) and ![Screen Shot 2024-12-16 at 16 49 51](https://github.com/user-attachments/assets/df85b705-6f08-4ae6-b0b4-9bc5b17c66c7)
- Return a JSON list of the minimum temperature, the average temperature, and the maximum temperature for a specified start or start-end range.
- For a specified start, calculate ![Screen Shot 2024-12-16 at 16 53 25](https://github.com/user-attachments/assets/1be322a5-567f-4503-ae01-48134d91a43a),![Screen Shot 2024-12-16 at 16 53 59](https://github.com/user-attachments/assets/426d95ba-fd24-4308-bdac-a2c10d76fc7b), and ![Screen Shot 2024-12-16 at 16 54 24](https://github.com/user-attachments/assets/cf8fef79-acba-4d7f-8a6d-973ec6272673)for all the dates greater than or equal to the start date.
- For a specified start date and end date, calculate ![Screen Shot 2024-12-16 at 16 53 25](https://github.com/user-attachments/assets/1be322a5-567f-4503-ae01-48134d91a43a),![Screen Shot 2024-12-16 at 16 53 59](https://github.com/user-attachments/assets/426d95ba-fd24-4308-bdac-a2c10d76fc7b), and ![Screen Shot 2024-12-16 at 16 54 24](https://github.com/user-attachments/assets/cf8fef79-acba-4d7f-8a6d-973ec6272673) for the dates from the start date to the end date, inclusive.

# Hints
- Join the station and measurement tables for some of the queries.
- Use the Flask ![Screen Shot 2024-12-16 at 16 55 46](https://github.com/user-attachments/assets/65ff2cf3-5809-42a1-a88f-cdfa06033333) function to convert your API data to a valid JSON response object.

# Requirements
# Jupyter Notebook Database Connection (10 points)
# To receive all points, you must
- Use the SQLAlchemy create_engine() function to connect to your SQLite database (1 point)
- Use the SQLAlchemy automap_base() function to reflect your tables into classes (3 points)
- Save references to the classes named station and measurement (4 points)
- Link Python to the database by creating a SQLAlchemy session (1 point)
- Close your session at the end of your notebook (1 point)
# Station Analysis (16 points)
# To receive all points, you must
- Design a query that correctly finds the number of stations in the dataset (9) (2 points)
- Design a query that correctly lists the stations and observation counts in descending order and finds the most active station (USC00519281) (2 points)
- Design a query that correctly finds the min, max, and average temperatures for the most active station (USC00519281) (3 points)
- Design a query to get the previous 12 months of temperature observation (TOBS) data that filters by the station that has the greatest number of observations (3 points)
- Save the query results to a Pandas DataFrame (2 points)
- Correctly plot a histogram with bins=12 for the last year of data using tobs as the column to count. (4 points)

# API SQLite Connection & Landing Page (10 points)
# To receive all points, your Flask application must
- Correctly generate the engine to the correct sqlite file (2 points)
- Use automap_base() and reflect the database schema (2 points)
- Correctly save references to the tables in the sqlite file (measurement and station) (2 points)
- Correctly create and binds the session between the python app and database (2 points)
- Display the available routes on the landing page (2 points)

# API Static Routes (15 points)
# To receive all points, your Flask application must include

A precipitation route that:
- Returns json with the date as the key and the value as the precipitation (3 points)
- Only returns the jsonified precipitation data for the last year in the database (3 points)

A stations route that:
- Returns jsonified data of all of the stations in the database (3 points)

A tobs route that:
- Returns jsonified data for the most active station (USC00519281) (3 points)
- Only returns the jsonified data for the last year of data (3 points)

# API Dynamic Route (15 points)
# To receive all points, your Flask application must include
A start route that:
- Accepts the start date as a parameter from the URL (2 points)

Returns the min, max, and average temperatures calculated from the given start date to the end of the dataset (4 points)
- A start/end route that:

Accepts the start and end dates as parameters from the URL (3 points)
- Returns the min, max, and average temperatures calculated from the given start date to the given end date (6 points)

# Coding Conventions and Formatting (8 points)
# To receive all points, your code must
- Place imports at the top of the file, just after any module comments and docstrings, and before module globals and constants. (2 points)
- Name functions and variables with lowercase characters, with words separated by underscores. (2 points)
- Follow DRY (Don't Repeat Yourself) principles, creating maintainable and reusable code. (2 points)
- Use concise logic and creative engineering where possible. (2 points)

# Deployment and Submission (6 points)
# To receive all points, you must
- Submit a link to a GitHub repository that’s cloned to your local machine and contains your files. (2 points)
- Use the command line to add your files to the repository. (2 points)
- Include appropriate commit messages in your files. (2 points)

# Comments (4 points)
# To receive all points, your code must
- Be well commented with concise, relevant notes that other developers can understand. (4 points)

# Grading
- This assignment will be evaluated against the requirements and assigned a grade according to the following table:
![Screen Shot 2024-12-16 at 17 02 56](https://github.com/user-attachments/assets/e231d84d-d3ff-4cb0-8b73-0c39a276f792)

# References
Menne, M.J., I. Durre, R.S. Vose, B.E. Gleason, and T.G. Houston, 2012: An overview of the Global Historical Climatology Network-Daily Database. Journal of Atmospheric and Oceanic Technology, 29, 897-910, https://journals.ametsoc.org/view/journals/atot/29/7/jtech-d-11-00103_1.xmlLinks to an external site.
