# run db locally
docker run --name flask_postgres -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=password -e POSTGRES_DB=postgres -p 5432:5432 -d postgres

# version 14 of postgres
docker run --name flask_postgres -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=password -e POSTGRES_DB=postgres -p 5432:5432 -d postgres:14

# psql command to connect to postgres db from outside container
psql -h localhost -d postgres -U postgres -W

# migrate the db
flask db init   
flask db migrate -m "Initial migration."
flask db upgrade




# run the app with docker

docker build -t flask-app .
docker run -p 5000:5000 flask-app


# psql 