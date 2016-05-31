## Week 1 Day 4

#### Objectives
- Use Psycopg2 to connect to Postgres from Python
- Explain how to run SQL queries from Python
- Explain how to create dynamic SQL queries through Python string formatting
- Python string formatting

## notes
- in ipynb, you can run command line commands, not just python commands
    - you have to use `!` and then the command for command line commands
    - ex. `!echo`

- psycopg2 is a way of using python to control SQL queries
- `cur.execute('DROP DATABASE IF EXISTS temp;')` will check to make sure that the `temp` database doesn't already exist, if it does, it deletes it
- with psycopg2 and ipynb's you have to make sure to `.commit()` your actions, otherwise nothing will actually be saved to memory
- you have to open and close connections to the psql server
