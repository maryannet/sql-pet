# Learning Goals and Use Cases

## Context: Why integrate R with databases using Docker?

* Large data stores in organizations are stored in databases that have specific access constraints and  structural characteristics.
* Learning to navigate the gap between R and the database is difficult to simulate outside corporate walls.
* R users frequently need to make sense of complex data structures using diagnostic techniques that shuld not be reinvented (and so would benefit from more public instruction and  commentary).
* Docker is a relatively easy way to simulate the relationship between an R/Rstudio session and database -- all on on a single machine.

## Learning Goals

After working through this tutorial, you can expect to be able to:

* Run queries against Postgres in an environment that simulates what you will find in a corporate setting.
* Understand some of the tradeoffs between queries aimed at exploration or informal investigation using dplyr and those where performance is important because of the size of the database or the frequency with which a query is run. You will be able to rewrite dplyr queries as SQL and submit them directly. You will have some understanding of techniques for assessing query structure and performance.
* Set up a Postgres database in a Docker enviornment and understand enough about Docker to swap databases, swap DBMS' (e.g., MySQL for Postgres, etc.)

## Use cases 

Imagine that you have one of several roles at **DVDs R Us** and that you need to:

* As a data scientist, I want to know the distribution of number of rentals per month per customer, so that the Marketing department can create incentives for customers in 3 segments: Frequent Renters, Average Renters, Infrequent Renters.
* As the Director of Sales, I want to see the total number of rentals per month for the past 6 months and I want to know how fast our customer base is growing/shrinking per month for the past 6 months.
* As the Director of Marketing, I want to know which categories of DVDs are the least popular, so that I can create a campaign to draw attention to rarely used inventory.
* As a shipping clerk, I want to add rental information when I fulfill a shipment order.
* As the Director of Analytics, you want to test as much of the production R code in my shop against a new release of the DBMS that the IT department is implementing next month.
* etc.

## Environment

This tutorial uses [the Postgres version of "dvd rental" database](http://www.postgresqltutorial.com/postgresql-sample-database/), which can be  [downloaded here](http://www.postgresqltutorial.com/wp-content/uploads/2017/10/dvdrental.zip).  Here's a glimpse of it's structure:
    
![Entity Relationship diagram for the dvdrental database](./screenshots/dvdrental-er-diagram.png)
