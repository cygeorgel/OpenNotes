	```
docker exec -it mysql bash
```

```
mysql -uroot -proot
```

```
mysql> CREATE DATABASE my_db;
mysql> GRANT ALL PRIVILEGES ON my_db.* TO 'default'@'%';
mysql> FLUSH PRIVILEGES;
```

```
docker cp my_dump.sql.gz mysql:/tmp
```

Or from the host with MySQL installed:

```
gunzip < my_dump.sql.gz | mysql -udefault -psecret -h127.0.0.1 my_db
```


