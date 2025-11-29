## 1. Start and enable the PostgreSQL service 

### Start the service:
[bash]
```
sudo systemctl start postgresql
```

### Enable it to start automatically on boot:
[bash]
```
sudo systemctl enable postgresql
```


### Check the status to confirm it's running:
[bash]
```
sudo systemctl status postgresql
```

## 2. Connect to the PostgreSQL server 
### Log in as the postgres user:

[bash]
```
sudo -u postgres psql
```

## 3. Perform basic tasks within psql
### List databases:
[sql]
```
\l
```
### List users:
[sql]
```
\du
```

### Create a new user:
[sql]
```
CREATE USER myuser WITH PASSWORD 'mypassword';
```

### Create a new database:
[sql]
```
CREATE DATABASE mydatabase;
```

### Create a table:
[sql]
```
CREATE TABLE users (name VARCHAR(200));
```

### Insert data:
[sql]
```
INSERT INTO users (name) VALUES ('kali');
```

### Select data:
[sql]
```
SELECT * FROM users;
```
### Exit psql:
[sql]
```
\q
``` 
