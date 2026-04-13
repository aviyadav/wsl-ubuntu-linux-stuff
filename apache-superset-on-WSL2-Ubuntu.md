# Apache Superset on WSL - Ubuntu

#### using pypi

~~~text
sudo apt update
sudo apt dist-upgrade -y


[superset - setup]

sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.11 python3-pip python3.11-dev python3.11-venv build-essential libssl-dev libffi-dev libsasl2-dev libldap2-dev default-libmysqlclient-dev

sudo apt-get install micro build-essential libssl-dev libffi-dev python3-dev python3-pip libsasl2-dev libldap2-dev default-libmysqlclient-dev

mkdir superset && cd superset

uv python pin 3.11

uv init . --bare
uv venv
uv add pip

source .venv/bin/activate

pip install --upgrade pip setuptools wheel pillow marshmallow==3.20.1
pip install sqlalchemy pydantic psycopg2-binary duckdb-engine duckdb snowflake-sqlalchemy

pip install apache-superset


openssl rand -base64 42
generated-key

also set iy up in profile 
export SUPERSET_SECRET_KEY=generated-key
export FLASK_APP=superset

superset db upgrade

superset fab create-admin 	# admin -- passpwrd

superset load-examples

superset init

superset run

or

superset run -p 8088 --with-threads --reload --debugger



pip install gunicorn
gunicorn -w 4 -b 0.0.0.0:8088 "superset.app:create_app()"

# complete

gunicorn \
    -w 10 \
    -k gevent \
    --worker-connections 1000 \
    --timeout 120 \
    -b 0.0.0.0:8088 \
    --limit-request-line 0 \
    --limit-request-field_size 0 \
    "superset.app:create_app()"



duckdb:////path/to/duck.db

duckdb:////apps/superset/dummy_data.duckdb
duckdb:////home/user/apps/superset/sample_data.duckdb

postgresql://{self.DBUSER}:{self.DBPASSWORD}@{self.DBHOST}:{self.DBPORT}/{self.DBNAME}

snowflake://{user}:{password}@{account}.{region}/{database}?role={role}&warehouse={warehouse}
snowflake://{user}:{password}@{account}/{database}/{schema}?role={role}&warehouse={warehouse}&authenticator=username_password_mfa


~~~
