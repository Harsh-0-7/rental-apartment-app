## Steps to Install DATABASE in Local:
1. Create postgres docker container: 
sudo podman run -d --name rentiFullDB -e POSTGRES_PASSWORD='Harsh@18' -e POSTGRES_USER=postgres -p 5433:5432 docker.io/postgis/postgis:latest

2. Create pgadmin docker container
sudo podman run --name pgadmin-container -p 5050:80 -e 'PGADMIN_DEFAULT_EMAIL=<email>' -e 'PGADMIN_DEFAULT_PASSWORD=<password>' -d docker.io/dpage/pgadmin4

3. Get internal IP Address of postgres container
sudo podman inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' rentiFullDB

4. Open pgAdmin on localhost:5050 with email and password

5. Create server with hostname as internal ip address of postgres container and port 5432 and password.

6. Create Database inside new server created.

7. Run query tool on new database created.

8. Run 'CREATE EXTENSION IF NOT EXISTS "postgis"'

