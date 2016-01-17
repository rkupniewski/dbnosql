##Egzamin
###Rafał Kupniewski

**Import**

Ponieważ baza Reddit jest bardzo duża i zapytania tam są wykonywane bardzo wolno więc tak jak część moich koleżanek i kolegów postanowiłem posłużyc się bazą restauracji.


Zaimportowanie do bazy MongoDB za pomocą polecenia:

*mongoimport  --db res --collection res --drop --file restauracje.json*

**Wyszukiwanie - lista miejscowosci w ktorych są restauracje(część)**

![rys](pic/s10.jpg)

**Wyszukiwanie restauracji z polskim jedzeniem** :heart:

![rys](pic/s3.jpg)


**Wyszukiwanie z restauracji zaczynajacej sie na literke B**

![rys](pic/s5.jpg)


**Wyszukiwanie restauracji podajacej konkretny typ jedzenia w konkretnym miescie** :angry:

![rys](pic/s4.jpg)

**Javascript**


**Wyszukiwanie z warunkiem restauracji z najgorszym ratingiem** :rage:

![rys](pic/s6.jpg)

**Wyszukiwanie z warunkiem restauracji gdzie typ jedzenia ma miedzy 5 a 8 liter (w sumie nie wiem po co, ale można...)** :confused:

![rys](pic/s9.jpg)

**Agregacja - Restauracje o najwyższej ocenie** :+1:

![rys](pic/s7.jpg)

**Agregacja - Miejscowości najrzadziej odwiedzane** :disappointed_relieved:

![rys](pic/s8.jpg)



__Eksploracja danych__

**Grupujemy restauracje wg rankingu poleceniem:**


''' db.res.aggregate( [   {"$group" :      {"_id" : "$rating", "count" : {"$sum" : 1}}},     {"$sort" : {"count" : -1}},     {"$limit" : 14}     ])
{ "_id" : 5, "count" : 1107 }
{ "_id" : 5.5, "count" : 600 }
{ "_id" : 4.5, "count" : 472 }
{ "_id" : 4, "count" : 167 }
{ "_id" : "Not yet rated", "count" : 63 }
{ "_id" : 3.5, "count" : 51 }
{ "_id" : 6, "count" : 49 }
{ "_id" : 3, "count" : 16 }
{ "_id" : 2.5, "count" : 13 }
{ "_id" : 1, "count" : 5 }
{ "_id" : 2, "count" : 3 }
{ "_id" : 1.5, "count" : 2 },,,

**Mamy posortowane dane: ilość restauracji pogrupowanych wg rankingu**

Konwertuje do CVS

| _id            | count     |
|----------------|-----------|
| 5,0            |	1107    |
| 5,5            |	600      |
| 4,5            |	472      |
| 4,0            |	167      |
| Not yet rated  |	63       |
| 3,5            |	51       |
| 6,0            |	49       |
| 3,0            |	16       |
| 2,5            |	13       |
| 1,0            |	5        |
| 2,0            |	3        |
| 1,5            |	2        |

I robimy wykresik

![rys](pic/s11.png)
