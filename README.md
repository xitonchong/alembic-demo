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
alembic downgrade base # to remove all of the changes to db
```
### to have autogenerate db changs like django auto migrations 
create a file <models.py> here 
create a declarative_base object in models.py 
then pass it to versions/env.py  --  target_metadata = Base
```bash
alembic revision --autogenerate -m "added company model"
```



### in postgresql container
```bash
docker exec -ti alembic-demo psql -U postgres -d alembic_db


\dt # to show tables
\q # to escape out of docker container
```