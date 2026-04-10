# install postgresql on openSUSE-Tumbleweed running in WSL2

### Ensure your openSUSE Tumbleweed WSL2 instance is up to date

```
sudo zypper dup
```

#### Install PostgreSQL

```
sudo zypper install postgresql-server postgresql-contrib
```

#### set password for linux user postgres

```
sudo passwd postgres
```

#### Initialize the Database

```
sudo -u postgres initdb --pgdata=/var/lib/pgsql/data
```

```text
initdb: warning: enabling "trust" authentication for local connections
initdb: hint: You can change this by editing pg_hba.conf or using the option -A, or --auth-local and --auth-host, the next time you run initdb.

Success. You can now start the database server using:

    pg_ctl -D /var/lib/pgsql/data -l logfile start
    pg_ctl stop -D /var/lib/pgsql/data -m immediate
```    
    
#### start enable and stop postgresql server

```
sudo systemctl start postgresql
sudo systemctl enable postgresql

sudo systemctl stop postgresql
```

#### loginto pogrgres server instance

```
sudo -i -u postgres psql
	<postgres user passwdd>
```	

#### create user and make admin/superuser

```
-- Inside psql
CREATE USER demouser WITH PASSWORD 'password';
ALTER USER demouser SUPERUSER;
\q
```




#### connection from outside

```
sudo vim /var/lib/pgsql/data/pg_hba.conf
```
```text
Add host all all 0.0.0.0/0 md5 to the end of the file.
```

#### Edit postgresql.conf to listen on all interfaces:

```
sudo vim /var/lib/pgsql/data/postgresql.conf
```

```text
Uncomment listen_addresses and change it to *:
```

```
listen_addresses = '*'
```

#### resrart postgresql

```
sudo systemctl restart postgresql
```



