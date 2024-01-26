How It Works:
1.Docker Compose: Using the docker-compose.yaml file, three Docker containers are spun up:

A source PostgreSQL database with sample data.
A destination PostgreSQL database.
A Python environment that runs the ELT script.

2.ELT Process: The elt_script.py waits for the source PostgreSQL database to become available. Once it's available, the script uses pg_dump to dump the source database to a SQL file. Then, it uses psql to load this SQL file into the destination PostgreSQL database.

3.Database Initialization: The init.sql script initializes the source database with sample data. It creates several tables and populates them with sample data.
