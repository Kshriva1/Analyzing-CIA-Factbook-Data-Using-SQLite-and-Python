# Analyzing-CIA-Factbook-Data-Using-SQLite-and-Python

In this project, we'll work with data from the [CIA World Factbook](https://www.cia.gov/library/publications/the-world-factbook/), a compendium of statistics about all of the countries on Earth. The Factbook contains demographic information like:

    population - The population as of 2015.
    population_growth - The annual population growth rate, as a percentage.
    area - The total land and water area.
    
    
We can actually query the database to get this information directly:
```
SELECT * FROM sqlite_master WHERE type='table';   
```

We can actually use pandas to run SQL queries and display the results neatly as a DataFrame object. We create a sqlite3.Connection instance as usual and then use pandas.read_sql_query(sql, con) to handle running the query and returning the results in a table:
```
import sqlite3

import pandas as pd

conn = sqlite3.connect("factbook.db")

q = "SELECT * FROM sqlite_master WHERE type='table';"

pd.read_sql_query(q, conn)
```

We're using pandas and matplotlib to display results neatly and visualize them because they let us focus on practicing thinking and working in SQL. We spend most of our time in SQL in this project and will inteface with pandas and matplotlib minimally.

We can download the database from [here](https://github.com/factbook/factbook.sql/releases)
