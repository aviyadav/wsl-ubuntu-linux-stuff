# transfer DB (tables with data) from duckdb to postgres

```
INSTALL postgres;
LOAD postgres;

-- Attach the database under the alias 'pg_db'
ATTACH 'host=localhost port=5432 dbname=demodb user=demouser password=password' AS pg_db (TYPE postgres);


-- Create a new table in Postgres from a DuckDB table
CREATE TABLE pg_db.AE AS SELECT * FROM AE;
CREATE TABLE pg_db.CM AS SELECT * FROM CM;
CREATE TABLE pg_db.DM AS SELECT * FROM DM;
CREATE TABLE pg_db.LB AS SELECT * FROM LB;
CREATE TABLE pg_db.TV AS SELECT * FROM TV;
CREATE TABLE pg_db.VS AS SELECT * FROM VS;

-- Insert into an existing Postgres table
INSERT INTO pg_db.AE SELECT * FROM AE;
INSERT INTO pg_db.CM SELECT * FROM CM;
INSERT INTO pg_db.DM SELECT * FROM DM;
INSERT INTO pg_db.LB SELECT * FROM LB;
INSERT INTO pg_db.TV SELECT * FROM TV;
INSERT INTO pg_db.VS SELECT * FROM VS;

```
