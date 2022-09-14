# Challenge 7 ETF Analysis

## Introduction
The purpose of this project is to analyze ETF's using SQL querey's, hvplot and Pandas.

## Data
We breakout PYPL information using a SQL querey and then graph the results.
```
query = """
SELECT *
FROM PYPL
"""
```
![PYPL](/Images/pypl.PNG)

Here we join the 4 ETF's in order to analze their daily returns.
```
query = """
SELECT *
FROM GDOT
INNER JOIN GS
    ON GS.time = GDOT.time
INNER JOIN PYPL
    ON PYPL.time = GDOT.time
INNER JOIN SQ
    ON SQ.time = GDOT.time
"""
etf_portfolio = pd.read_sql(query, con=engine)
```
![what_a_mess](/Images/mess.PNG)

## Analysis
The cumulative daily return for the entire portfolio are calculated and graphed.
![cumulative](/Images/cumulative.PNG)