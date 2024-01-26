How It Works:

1. Docker Compose: Using the docker-compose.yaml file, a couple Docker containers are spun up:


A source PostgreSQL database with sample data.

A destination PostgreSQL database.

A Postgres database to store Airflow metadata

The webserver to access Airflow throught the UI

Airflow's Scheduler

2. ELT Process: Within Airbyte, you will input the information for both the source and destination databases to create a connection. From there, you'll take the connection ID from the Airbyte UI, plug it into the elt_dag.py file so that when you run Airflow, it can run the sync for you. After the sync is complete, Airflow will run dbt to run the transformations on top of the destination database.

3. Database Initialization: The init.sql script initializes the source database with sample data. It creates several tables and populates them with sample data.
