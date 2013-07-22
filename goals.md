# Goals

* Make it easy for a new user to get their own data into Neo4j, coming from data in CSV format, which is presumed to come from an RDBMS (the most important case) and possibly other databases
* Make it easy for a new user to load (and re-load) our own (Neo-curated) sample data sets when learning Neo4j
* Support an ecosystem of tooling, such that new contributions can come into being and easily be plugged in, and so that we pick the parts we like and add them to the tool over time
* This tool must load data into a running Neo4j database, preserving any existing data (i.e. it must not require an empty database in order to function; and it can't require the database to be shut down in order to load data)

# Approach

* Create one command-line tool to which a user can go to load data. Defer the eventual concern of exposing this through the Neo4j Browser
* In building this, document how a user might add code to create a new format

# Initial Scope

* Focus on small to medium data sets first (with transactional operation)
*  Don't (for now) take on the problem of data *export* from a non-Neo4j data source. Assume the data is already in the given format