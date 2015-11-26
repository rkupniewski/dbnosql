Ćwiczenia zostały wykonane na notebooku Fujitsu Celsius 710H z procesorem i5 pierwszej generacji. System operacyjny Windows 10.

#Zadanie MongoDB vs Postgress

#####Pobrany został plik RC_2015-01.bz2
Plik w celach eksperymentalnych został rozkompresowany do pliku JSON.

Nastepnie plik został zaimportowany do bazy MongoDB i Postgress

Import do bazy MongoDB został wykonany za pomocą polecenia:

mongoimport  --db test --collection reddit --drop --file RC_2015-01.json

![Wykres pamięci](pic/1.png)

Czas importu 01:00:43,37

Import do bazy Postgress został wykonany za pomocą zewnetrznego programu Pgfutter ze strony:
(https://github.com/lukasmartinelli/pgfutter)

Składnia polecenia: pgfutter_windows_amd64 --db "reddit" --host "localhost" --port "5432" --user "postgres" --pw "martynka" --table "reddit"  json RC_2015-01.json



![Wykres pamięci](pic/3.png)

Czas importu 01:04:25,83

Wniosek: najwiekszym problemem z szybkością operacji na bazach jest wydajność pamięci masowej. Ani procesor ani pamiec RAM nie jest zbyt mocno obciążana.



Zliczanie rekordów:

- MongoDB - db.reddit.count()

czas operacji: zerowy, wynik : 53851542

- Postgress - select count(*) from import.reddit;  

czas operacji : zdążyłem wyjść z psem i zrobić herbatę, wynik : 53851542

---------------------------------






##Wnioski
| PostgreSQL                  | MongoDB           |
|-----------------------------|-------------------|
| - kłopotliwy import           | + prosty import (nawet ze skompresowanego archiwum)   |
| - JSON-y nie są rozbijane na osobne relacje, wszystko ląduje w polu typu JSON   | - trzeba sie nauczyć nowego języka zapytań  |
| - długi czas najprostrzych agregacji | + szybkie zliczenie |
| + z racji popularności łatwiejszy język zapytań | - nieradzenie sobie z agregacjami na tak dużym zbiorze



(var geojsonFeature = {
    "type": "Feature",
    "properties": {
        "name": "Coors Field",
        "amenity": "Baseball Stadium",
        "popupContent": "This is where the Rockies play!"
    },
    "geometry": {
        "type": "Point",
        "coordinates": [-104.99404, 39.75621]
    }
};)
