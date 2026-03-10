# Nginx-Dockerfile

---
## 1. Launch EC2 Instances  -- Ubuntu

Connect Instances
-- Go To Root Directory

```shell
sudo -i
```
 Update Instances

```shell
apt update
```

## 2. Docker Install 

docker install using official documention..

```shell
apt install docker.io -y
```
this command is un-official

## 3. Write index.html
```shell
cat > index.html
```
```shell
hii nginx file
```
ctrl + c

## 4. Write Dockerfile

```shell
nano dockerfile
```

Then Copy & Paste In dockerfile
ubuntu:22.04  -- this is ubuntu version


```shell
FROM ubuntu:22.04

RUN apt-get update && \
    apt-get install -y nginx && \
    rm -rf /var/www/html/

COPY ./index.html /var/www/html/

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```
then ctrl save & exit 

## 5. Build Dockerfile

```shell
docker build . -t new:latest
```

## 6. check docker images

```shell
docker images
```

## 7. Docker Container run 

```shell
docker run -d -P new:latest
```
-d means detached mode 

## 8. check docker container

```shell
docker ps
```
