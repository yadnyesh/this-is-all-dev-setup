docker-compose.yml

version: "3.8"
 
services:
  mysqldb:
    image: mysql:8.0.32
    container_name: mysql_db
    restart: unless-stopped
    # env_file: ./.env
    environment:
      - MYSQL_USER= yadnyesh
      - MYSQL_PASSWORD=yadnyesh
      - MYSQL_ROOT_PASSWORD=yadnyesh
      - MYSQL_DATABASE=yadnyesh
    ports:
      - '3306:3306'
    volumes:
      - mysqldb:/var/lib/mysql
volumes:
  mysqldb:      %
 
After creating the above file run
Docker-compose up
 
For connecting to the pod:
docker exec -it mysql_db mysql --user=yadnyesh --password=yadnyesh
