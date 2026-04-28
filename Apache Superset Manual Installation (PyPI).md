# Manual Installation (PyPI)

```text
Use this method if you prefer a native installation. Note that as of late 2024, Superset often requires Python 3.11 or earlier; if Ubuntu 26.04 defaults to a newer version, you may need to use deadsnakes PPA to install an older Python version. 
Install OS Dependencies:
bash
sudo apt update
sudo apt install -y build-essential libssl-dev libffi-dev python3-dev python3-pip python3-venv libsasl2-dev libldap2-dev default-libmysqlclient-dev
Set Up a Virtual Environment:
bash
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip setuptools wheel
Install Superset:
bash
pip install apache-superset
Configure Secret Key: Generate a secure key using openssl rand -base64 42 and set it as an environment variable:
bash
export SUPERSET_SECRET_KEY='your_generated_key'
Initialize the Application:
bash
superset db upgrade
superset fab create-admin
superset load_examples
superset init
Run the Server:
bash
superset run -p 8088 --with-threads --reload --debugger
 ```
