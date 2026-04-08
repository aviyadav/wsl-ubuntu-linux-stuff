# WSL - Ubuntu

#### using pypi - locally


```
sudo apt update
sudo apt dist-upgrade -y
```

[superset - setup]

```
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.11 python3-pip python3.11-dev python3.11-venv build-essential libssl-dev libffi-dev libsasl2-dev libldap2-dev default-libmysqlclient-dev
```

[installation]

```
mkdir superset && cd superset

uv python pin 3.11

uv init . --bare
uv venv
uv add pip
```

```
source .venv/bin/activate

pip install --upgrade pip setuptools wheel pillow marshmallow==3.20.1

pip install sqlalchemy pydantic psycopg2-binary duckdb-engine duckdb snowflake-sqlalchemy

pip install apache-superset
```

[Generate secret key]

```
openssl rand -base64 42
```

PK5YxJE0hjHu3zgZ5rQJbYOU+C4gdpkKeSm4w7Atp9Cdiitva00ojAFA

[set in the bashrc]

```
export SUPERSET_SECRET_KEY=PK5YxJE0hjHu3zgZ5rQJbYOU+C4gdpkKeSm4w7Atp9Cdiitva00ojAFA
export FLASK_APP=superset
```


[setup --- continued]

```
superset db upgrade

superset fab create-admin 	# admin -- passpwrd

superset load-examples

superset init

superset run

or

superset run -p 8088 --with-threads --reload --debugger

```

[run like production]

```
pip install gunicorn
gunicorn -w 4 -b 0.0.0.0:8088 "superset.app:create_app()"
```

[connect to duckdb - sqlalchemy connection string]
```
sample - duckdb:////path/to/duck.db


duckdb:////apps/superset/clinical_data.duckdb
duckdb:////home/avinash/apps/superset/clinical_data.duckdb
```




