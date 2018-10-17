# SQL Mysteries Revealed

Window functions, Explain Plans, and Distributed Data

## Viewing content

This repo collects some Jupyter notebooks used for teaching.
You should be able to view the static notebooks directly in
GitHub without installing anything on your machine.

## Setting up the environment

If you want to execute these notebooks, you'll need to 
have a few things installed.

First, you'll need python 3 installed (which is beyond the scope
of these instructions), then:

```bash
git clone https://github.com/jklukas/sql-mysteries
cd sql-mysteries/
python3 -m venv ./venv
source venv/bin/activate
pip install -r requirements.txt
```

Then fire up the Jupyter notebook server:

```bash
jupyter notebook
```

You'll also need an instance of Postgres to connect to.
A good option is to 
[install Docker](https://www.docker.com/get-started)
and then launch:

```bash
docker run -e POSTGRES_PASSWORD=mysecretpassword -d -p5432:5432 postgres
```

To stop Postgres:
```bash
docker ps  # Look to see what the CONTAINER ID for postgres is
docker stop f0a2e8b1a83e  # replace with the relevant id
docker rm f0a2e8b1a83e
```
