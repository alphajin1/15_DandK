# my_daemon

```bash
docker build --tag my_daemon:0.1 .

docker run --name myd my_daemon:0.1

# another terminal 
docker stop myd 

# restart origin terminal
docker start -i myd 
```

# my_daemon2

```bash
docker build --tag my_daemon:0.2 -f Dockerfile2 .

docker run --name myd my_daemon:0.2
 
docker stop myd 

docker start -i myd
```


# my_daemon3

```bash
docker build --tag my_daemon:0.3 -f Dockerfile3 .

# 호스트에 퍼시스턴트 볼륨 추가
docker run --name myd -v `pwd`/data:/pv my_daemon:0.3

docker stop myd

docker rm myd

docker run --name myd -v `pwd`/data:/pv my_daemon:0.3
```

# 백그라운드에서 동작하는 컨테이너를 포그라운드로 전환
```bash
docker attach --sig-proxy=false myd
```