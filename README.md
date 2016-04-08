*Based on thingspeak fork by https://github.com/yuzhangiot/thingspeak*

## Docker Thingspeak
To run this container you need to have mysql running on port 3306 with root password of "speak" (database.yml.example).

### Example mysql run command:
``` docker run --name mysql55 -e MYSQL_ROOT_PASSWORD=speak -d mysql:5.5

### Example thingspeak container run command:
``` docker run --name thingspeak -p 80:80 --link mysql55:mysql -d synomi/thingspeak

### After running containers you need to create dbs
``` docker exec -it thingspeak rake db:create

``` docker exec -it thingspeak rake db:schema:load

Now you should see thingspeak running on your http://dockerhost!




