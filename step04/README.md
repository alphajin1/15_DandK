# MySQL Server 기동

```bash
docker network create apl-net

# m1 mac issue
docker pull --platform linux/amd64 mysql:5.7

docker run -d --name mysql --network apl-net -e MYSQL_ROOT_PASSWORD=qwerty --platform linux/amd64 mysql:5.7
```

# PHP 기동 
```bash
docker build -t php-apl:0.1 .

docker run -d --name php --network apl-net -p 8080:80 -e MYSQL_USER=root -e MYSQL_PASSWORD=qwerty php-apl:0.1
```