### install uv
~~~
curl -LsSf https://astral.sh/uv/install.sh | sh
~~~

#### uv clean init
```
uv init <project-name> --bare

or [inside folder]

uv init . --bare
```

#### Add .python-version
```
uv python pin 3.13
```

#### duckdb
~~~
curl https://install.duckdb.org | sh
~~~
