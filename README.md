# Create and fill a PostgresDB with Docker Compose

This project utilizes Docker, create tables and fill the tables in a Postgres database.

## DB Variables

Set the variables in sql/fill_tables.sql

| Parameter	      | Description                                       |
|-----------------|---------------------------------------------------|
| number_of_sales |	Number of rows to create in the table sale        |
| number_of_users	| Number of rows to create in the table users       |
| number_of_products|	Number of rows to create in the table product   |
| number_of_stores |	Number of rows to create in the table store     |
| number_of_coutries |	Number of rows to create in the table country |
| number_of_cities	| Number of rows to create in the table city      |
| number_of_status_names |	Number of rows to create in the table status_name |
| start_date |	Date of the first sale |
| end_date	| Date of the last sale |

## How It Works

1. **Docker Compose**: Using the `docker-compose.yaml` file
2. **Database Initialization**: The `create.sql` script creates tables in the database  and `fill_tables.sql` script loads tables with sample data. 

## Getting Started

1. Ensure you have Docker and Docker Compose installed on your machine.
2. Clone this repository.
3. To create the tables in database add `create_tables.sql` under *volumes:* within `docker-compose.yaml` file, `/docker-entrypoint-initdb.d/`
4. To fill tables add `fill_tables.sql` under *volumes:* within `docker-compose.yaml` file, `/docker-entrypoint-initdb.d/`
5. Navigate to the repository directory and run `docker-compose up`.
6. To connect to Postgres run `$ docker ps -f "name=postgres"` , get the *CONTAINER_ID* of the running container, and execute: `$ docker exec -it <CONTAINER_ID> psql -U postgres` in new terminal window.
7. Connect to postgres database:   `\d`
   
