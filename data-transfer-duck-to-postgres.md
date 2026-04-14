# Transfer tables along data from DuckDB to PostgreSQL

```
INSTALL postgres;
LOAD postgres;


-- Replace with your actual connection details
ATTACH 'dbname=demodb user=demouser host=localhost password=password' AS pg_db (TYPE POSTGRES);


CREATE TABLE pg_db.target_table_name AS SELECT * FROM source_table;
INSERT INTO pg_db.target_table_name SELECT * FROM source_table;

```
