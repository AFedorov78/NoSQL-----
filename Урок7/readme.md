# ДЗ

## Кластер Couchbase
Docker Official Images are a curated set of Docker open source and drop-in solution repositories. https://hub.docker.com/_/couchbase

1. Скачал  Couchbase. 
docker pull couchbase

2. запустил
docker run -d --name db -p 8091-8096:8091-8096 -p 11210-11211:11210-11211 couchbase

3. пошел по адресу
http://localhost:8091

4. Еще машины
docker run -d --name db1 couchbase
docker run -d --name db1 couchbase

5. Получил ip
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' db1
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' db2
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' db

6. в консоле создал кластер CouchBaseClusterTest

7. создал тоже самое и через докер композер.

8. Добавил сервера в кластер

9. сделал ребаланс

10. загрузил Sample Buckets
beer-sample

11. загрузил осавшиеся примеры(нажал назад назад ).
Инче страница с загрузкой примеров не открывалась. Видимо на первый раз сделана.

12. Погонял запросы из примера https://docs.couchbase.com/server/current/getting-started/try-a-query.html
ну и конечно SELECT "Hello world" AS greeting;

13. остановил контейнер db2. В консоле couchdb увидел что сервер умер.
Добавал данные  в таблицу.
Запустил db2.
Нажал на ребаланс.
данные востановились на DB2.


