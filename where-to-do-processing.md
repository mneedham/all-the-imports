# Where to do the processing of the data?

## Client Side

* Generate cypher statements client side and stream them to the server
* Seems like it would at least make sense to do some validation of the file client side before sending to the server

+ Can use [transactional API](http://docs.neo4j.org/chunked/preview/rest-api-transactional.html) to process those cypher queries 

## Server Side

* Create new end point that takes CSV files as input and then convert those into nodes/relationships in the database

- Security around uploading files
	* Virus scanning server side
- Need to make changes in two places - can't just write a standalone tool and have it work with an existing installation


## What do other tools do?

* [MySQL LOAD DATA INFILE](http://dev.mysql.com/doc/refman/5.1/en/load-data.html) 
	* you specify a file on the client side or on the server and then it does the processing on the server side.
* [Oracle paper on data loading](http://www.oracle.com/technetwork/database/bi-datawarehousing/twpdwbestpractices-for-loading-11g-404400.pdf)
	* you put files somewhere that the server has access 
* [mongoimport](http://docs.mongodb.org/manual/reference/program/mongoimport/)
	* processes client side and then sends a compressed version of the JSON file from what I can tell