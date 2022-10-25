# Pimcore New Project Install Guide Ubuntu

## Getting started follow these steps
# Choose which version
## Old Project 

```bash
git clone git@repo
cd ./project
```

### 
 * Open the `docker-compose.yml` file in an editor, uncomment all the `user: '1001:1001'` lines and update the ids if necessary
###

```bash
docker-compose down
docker-compose up -d --remove-orphans
```

### 
 * Make `.docker` folder a put the file in the folder
###
```bash
.docker/nginx.conf
```
###
* This is the `<user>` user you are logged in to ubuntu
###

```bash
chown -R <user>: .
```


###
* Install 3 Party Packages 
###

```bash
composer i --ignore-platform-req=ext-redis

npm i
```
###
* Database
###
```bash
docker-compose ps

docker inspect code | grep IPAdd

mysql -u root -p<password> -h <ip> pimcore < database.sql

docker-compose up -d --remove-orphans
```



You can now visit your pimcore instance:
- The frontend: <http://localhost>
- The admin interface, using the credentials you have chosen above: <http://localhost/admin>
- Done! 😎

**Made By [Jan Van den Bogaert](https://github.com/JanVDB2000) 2022**
