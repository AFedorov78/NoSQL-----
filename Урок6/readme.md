# ДЗ лекции 6

Делал три реплик сета без конфига.
Брал отсюда пример. https://www.youtube.com/watch?v=XLLF3fsEZqs&list=PLW9OjBx2zG1fBpAdjvSci1E3p46QN1jsE&index=2

australia = (new Mongo('localhost:27017')).getDB('test')
australia.mycollection.find()
MongoServerError: not primary and secondaryOk=false - consider using db.getMongo().setReadPref() or readPreference in the connection string
australia.getMongo().setReadPref("secondary")

germany = (new Mongo('localhost:27017')).getDB('test')
germany.getMongo().setReadPref("secondary")

тест - india.mycollection.insert({comment:'how are you?'})

Это без докер композера. Показалось не интересно.

Заморочился как сделать через докер композер.

далее отсюда брал. все по новой.
https://dzone.com/articles/composing-a-sharded-mongodb-on-docker
Создал три ноды кластера шардирования
создал три ноды конфигурации
указал что 