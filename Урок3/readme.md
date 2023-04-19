# ДЗ лекции  Mongo
Порядок команд.

docker pull mongo
docker run -d -p 27017:27017 --name test-mongo mongo:latest
docker exec -it test-mongo bash

## mongosh

use otus

show collections

db.createCollection('otus')
db.createCollection("cars")
db.car.insertOne( { _id: 1, car: "bmw", qty: 2 } )
db.car.insertMany([ { _id: 2, car: "ford", qty: 3 },
{ _id: 3, cat: "Tom", color: "black"} ])
show collections

db.createCollection("movie")
db.movie.insert( { _id: 10, item: "box", qty: 20 } )
- DeprecationWarning: Collection.insert() is deprecated. Use insertOne, insertMany, or bulkWrite.
db.movie.find()

db.movie.insert([
{"_id":11,"title":"Son of the Pink Panther","year":1993,"cast":["Roberto Benigni","Herbert Lom","Claudia Cardinale"],"genres":["Comedy"]},
{"_id":12,"title":"The Dentist 2","year":1998,"cast":["Corbin Bernsen","Jillian McWhirter"],"genres":["Horror"]}])
db.movie.find()


db.movie.insert([
{"_id":11,"title":"Son of the Pink Panther","year":1993,"cast":["Roberto Benigni","Herbert Lom","Claudia Cardinale"],"genres":["Comedy"]},
{"_id":12,"title":"The Dentist 2","year":1998,"cast":["Corbin Bernsen","Jillian McWhirter"],"genres":["Horror"]},
{"_id":13,"title":"Desert Blue","year":1998,"cast":["Brendan Sexton III","Kate Hudson","Casey Affleck","Christina Ricci"],"genres":["Comedy","Drama"]},
{"_id":14,"title":"Ted","year":2012,"cast":["Mark Wahlberg","Mila Kunis","Seth MacFarlane"],"genres":["Comedy"]},
{"_id":15,"title":"The Contractor","year":2013,"cast":["Danny Trejo","Brad Rowe","Christina Cox"],"genres":["Action"]},
{"_id":16,"title":"Need for Speed","year":2014,"cast":["Aaron Paul","Dominic Cooper","Imogen Poots","Kid Cudi"],"genres":["Action"]}])
- MongoBulkWriteError: E11000 duplicate key error collection: otus.movie index: _id_ dup key: { _id: 11 }

db.movie.insert([
{"_id":11,"title":"Son of the Pink Panther","year":1993,"cast":["Roberto Benigni","Herbert Lom","Claudia Cardinale"],"genres":["Comedy"]},
{"_id":12,"title":"The Dentist 2","year":1998,"cast":["Corbin Bernsen","Jillian McWhirter"],"genres":["Horror"]},
{"_id":13,"title":"Desert Blue","year":1998,"cast":["Brendan Sexton III","Kate Hudson","Casey Affleck","Christina Ricci"],"genres":["Comedy","Drama"]},
{"_id":14,"title":"Ted","year":2012,"cast":["Mark Wahlberg","Mila Kunis","Seth MacFarlane"],"genres":["Comedy"]},
{"_id":15,"title":"The Contractor","year":2013,"cast":["Danny Trejo","Brad Rowe","Christina Cox"],"genres":["Action"]},
{"_id":16,"title":"Need for Speed","year":2014,"cast":["Aaron Paul","Dominic Cooper","Imogen Poots","Kid Cudi"],"genres":["Action"]}], 
{ordered:false})
db.movie.find()

db.movie.insert([
{"title":"Second Act","year":2018,"cast":["Jennifer Lopez","Vanessa Hudgens","Leah Remini"],"genres":["Romance","Comedy"]},
{"title":"Mary Poppins Returns","year":2018,"cast":["Emily Blunt","Lin-Manuel Miranda","Ben Whishaw"],"genres":["Musical","Fantasy"]},
{"title":"Aquaman","year":2018,"cast":["Jason Momoa","Amber Heard","Willem Dafoe","Dolph Lundgren"],"genres":["Superhero","Action","Adventure"]}])

-   insertedIds: {
    '0': ObjectId("644038ab3c119555db172bc9"),
    '1': ObjectId("644038ab3c119555db172bca"),
    '2': ObjectId("644038ab3c119555db172bcb")
	
db.movie.find()
db.movie.find().pretty()
db.movie.findOne()

и другие куча find

sort
limit
skip?


index
aggregate

otus> db.movie.count()
DeprecationWarning: Collection.count() is deprecated. Use countDocuments or estimatedDocumentCount.

distinct

update
db.movie.find({_id : 1})
db.car.find({_id : 1})

movie->car))

update
delete

drop

## MongoDB Compass
create collection loaded.
import from file

Далее эксперименты с индекс и не индекс.
Загружал коллекции через  Compass

Без Index
<image src="2023-04-19_22-56-50.png" alt="Текст с описанием картинки">

C Index
<image src="2023-04-19_22-59-38.png" alt="Текст с описанием картинки">

---

Без Index
<image src="2023-04-19_23-04-20.png" alt="Текст с описанием картинки">

C Index
<image src="2023-04-19_23-06-26.png" alt="Текст с описанием картинки">

---


Без Index
<image src="2023-04-19_23-12-43.png" alt="Текст с описанием картинки">

C Index
<image src="2023-04-19_23-15-56.png" alt="Текст с описанием картинки">

<image src="2023-04-19_23-16-20.png" alt="Текст с описанием картинки">