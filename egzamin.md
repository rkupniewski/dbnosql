##Egzamin Rafał Kupniewski

**Import**

Ponieważ baza Reddit jest bardzo duża i zapytania tam są wykonywane bardzo wolno więc tak jak część moich koleżanek i kolegów postanowiłem posłużyc się bazą restauracji.


Zaimportowanie do bazy MongoDB za pomocą polecenia:

*mongoimport  --db res --collection res --drop --file restauracje.json*

**Wyszukiwanie - lista miejscowosci w ktorych są restauracje(część)**

![rys](pic/s10.jpg)

**Wyszukiwanie restauracji z polskim jedzeniem**

![rys](pic/s3.jpg)


**Wyszukiwanie z restauracji zaczynajacej sie na literke B**

![rys](pic/s5.jpg)


**Wyszukiwanie restauracji podajacej konkretny typ jedzenia w konkretnym miescie**

![rys](pic/s4.jpg)

**Javascript**


**Wyszukiwanie z warunkiem restauracji z najgorszym ratingiem**

![rys](pic/s6.jpg)

**Wyszukiwanie z warunkiem restauracji gdzie typ jedzenia ma miedzy 5 a 8 liter (w sumie nie wiem po co, ale można...)**

![rys](pic/s9.jpg)

**Agregacja - Resauracje o najwyższej ocenie**

![rys](pic/s7.jpg)

**Agregacja - Miejscowości najrzadziej odwiedzane**

![rys](pic/s8.jpg)
