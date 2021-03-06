# Real work with real data


## Some extra handy libraries

Here are some packages that we find handy in the preliminary investigation of a database (or a problem that involves data from a databse).

```r
library(glue)
```

```
## 
## Attaching package: 'glue'
```

```
## The following object is masked from 'package:dplyr':
## 
##     collapse
```

```r
library(skimr)
```

## Basic investigation

* R tools for data investigation
  + glimpse
  + str
  + View and kable

* overview investigation: do you understand your data
  + documentation and its limits
  + what's *missing* from the database: (columns, records, cells)

* find out how the data is used by those who enter it and others who've used it before
  + why is there missing data?

## Using Dplyr

We already started, but that's OK.

### finding out what's in the database

* DBI / RPostgres packaages
* R tools like glimpse, skimr, kable.
* examining dplyr queries (show_query on the R side v EXPLAIN on the Postges side)
* Tutorials like: https://suzan.rbind.io/tags/dplyr/ 
* Benjamin S. Baumer, A Grammar for Reproducible and Painless Extract-Transform-Load Operations on Medium Data: https://arxiv.org/pdf/1708.07073 

### sample query

* rental 
* date subset
* left join staff
* left join customer

### Subset: only retrieve what you need

* Columns
* Rows
  + number of row
  + specific rows
* dplyr joins in the R

### Make the server do as much work as you can

discuss this simple example? http://www.postgresqltutorial.com/postgresql-left-join/ 

* dplyr joins on the server side
* Where you put `(collect(n = Inf))` really matters

## What is dplyr sending to the server?

* show_query as a first draft

## Writing your on SQL directly to the DBMS

* dbquery
* Glue for constructing SQL statements
  + parameterizing SQL queries

## Chosing between dplyr and native SQL

* performance considerations: first get the right data, then worory about performance
* Tradeoffs between leaving the data in Postgres vs what's kept in R: 
  + browsing the data
  + larger samples and complete tables
  + using what you know to write efficient queries that do most of the work on the server
