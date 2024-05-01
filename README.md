https://www.youtube.com/watch?v=i9RX03zFDHU&ab_channel=BugBytes


```bash

# to start 
alembic init 

# edit sqlalchemy.url = <driver>:<Username>

# create revision file
alembic revision -m "create user table"

alembic upgrade head 
alembic revision --autogenerate -m "message 1" 
alembic history # 
alembic downgrade -1 
alembic current # current branch
alembic upgrade +1 # apply next migration

```

```bash
docker exec -ti alembic-demo psql -U postgres -d alembic_db


\dt # to show tables
\q # to escape out of docker container
```