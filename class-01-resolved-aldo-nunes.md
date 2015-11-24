# MongoDB - Aula 01 - Exercício
autor: Aldo Nunes Jr

## Importando os restaurantes
```
C:\mongodb\bin>mongoimport --db be-mean --collection restaurantes --drop --file d:\Curso\restaurantes.json
connected to: localhost
dropping: be-mean.restaurantes
imported 25359 documents
```
## Contando os restaurantes
```
>db.restaurantes.find({}).count()
25359
```

