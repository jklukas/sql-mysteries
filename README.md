# SQL Mysteries Revealed

Window functions, Explain Plans, and Distributed Data

## Iterations

This talk has been presented at:

- 2018-10-27 @ [Columbus Code Camp](http://columbuscodecamp.com/presentations.html)

## Viewing content

This repo collects some Jupyter notebooks used for teaching.
You should be able to view the static notebooks directly in
GitHub without installing anything on your machine.

## Overview

While the examples given here use PostgreSQL and Amazon Redshift, the concepts
and syntax mostly adhere to the SQL standard, so are applicable to other
relational databases like MySQL and SQL server.

Here's the general flow of the talk:

- Define and get familiar with the small dataset we'll be using
- Review the syntax for SQL aggregations (function like SUM and COUNT)
- Introduce window functions as an extension of aggregations
- Use a window function to build a query for recreating current state of a table from a history of changes
- Introduce Amazon Redshift and data warehouses
- Iterate on our query and table structure to make them perform well with 1 TB+ of data

## Further reading

- I recommend the [SQL Performance Explained](https://sql-performance-explained.com/) book by Markus Winand which focuses on database performance from a developer's viewpoint and covers all the major SQL databases
- For more context on the case study presented here, see my post [A Change Data Capture Pipeline from PostgreSQL to Kafka](https://www.simple.com/engineering/a-change-data-capture-pipeline-from-postgresql-to-kafka) from the Simple engineering blog
- See the AWS documentation for a [Redshift system architecture overview](https://docs.aws.amazon.com/redshift/latest/dg/c_high_level_system_architecture.html)
- See the [comically long list of PostgreSQL-derived databases](https://wiki.postgresql.org/wiki/PostgreSQL_derived_databases)

## Setting up the environment

If you want to execute these notebooks, you'll need to 
have a few things installed.

First, you'll need python 3 installed (which is beyond the scope
of these instructions), then:

```bash
git clone https://github.com/jklukas/sql-mysteries
cd sql-mysteries/
python3 -m venv ./venv
source venv/bin/activate
pip install -r requirements.txt
```

Then fire up the Jupyter notebook server:

```bash
jupyter notebook
```

You'll also need an instance of Postgres to connect to.
A good option is to 
[install Docker](https://www.docker.com/get-started)
and then launch:

```bash
docker run -e POSTGRES_PASSWORD=mysecretpassword -d -p5432:5432 postgres
```

To delete the Postgres container:
```bash
docker ps  # Look to see what the CONTAINER ID for postgres is
docker stop f0a2e8b1a83e  # replace with the relevant id
docker rm f0a2e8b1a83e
```
