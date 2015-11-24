##MongoDB - Aula 02 - Exercício
autor: Aldo Nunes Jr

##Listagem das databases (passo 2)
```
> use be-mean-pokemons
switched to db be-mean-pokemons
> show dbs
be-mean            0.078GB
be-mean-instagram  0.078GB
local              0.078GB
```
##Listagem das coleções (passo 3)
```
> show collections
>
```
##Cadastro dos pokemons (passo 4)
```
> var pokemons = [{ 'name' : 'Arbok', 'description' : 'Cobra Mui Loka', 'type' : 'Veneno', 'attack' : 49,'defense' : 45, 'height' : 3.5 },{ 'name' : 'Charmander', 'description' : 'Esse é o cão chupando manga de fofinho', 'type' : 'fogo', 'attack' : 52,'defense': 34, 'height' : 0.6},{ 'name' : 'Jynx', 'description' : 'Aquela Boca nao me engana', 'type' : 'gelo', 'attack' : 30,'defense': 25, 'height' : 1.4},{ 'name' : 'Ledian', 'description' : 'Joaninha do Boxe', 'type' : 'inseto', 'attack' : 30, 'defense' : 25, 'height' : 1.4},{ 'name' : 'Magikarp', 'description' : 'Peixe Inutil', 'type' : 'água', 'attack' : 10, 'defense' :15, 'height' : 0.9} ]
> pokemons
[
        {
                "name" : "Arbok",
                "description" : "Cobra Mui Loka",
                "type" : "Veneno",
                "attack" : 49,
                "defense" : 45,
                "height" : 3.5
        },
        {
                "name" : "Charmander",
                "description" : "Esse é o cão chupando manga de fofinho",
                "type" : "fogo",
                "attack" : 52,
                "defense" : 34,
                "height" : 0.6
        },
        {
                "name" : "Jynx",
                "description" : "Aquela Boca nao me engana",
                "type" : "gelo",
                "attack" : 30,
                "defense" : 25,
                "height" : 1.4
        },
        {
                "name" : "Ledian",
                "description" : "Joaninha do Boxe",
                "type" : "inseto",
                "attack" : 30,
                "defense" : 25,
                "height" : 1.4
        },
        {
                "name" : "Magikarp",
                "description" : "Peixe Inutil",
                "type" : "água",
                "attack" : 10,
                "defense" : 15,
                "height" : 0.9
        }
]
>
]
> db.pokemons.insert(pokemons)
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 5,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
>
```
##Lista dos pokemons (passo 5)

```
> db.pokemons.find()
{ "_id" : ObjectId("565490da88ce9d2ce2a84252"), "name" : "Arbok", "description" : "Cobra Mui Loka", "type" : "Veneno", "attack" : 49, "defense" : 45, "height" : 3.5 }
{ "_id" : ObjectId("565490da88ce9d2ce2a84253"), "name" : "Charmander", "description" : "Esse é o cão chupando manga de fofinho", "type" : "fogo", "attack" : 52, "defense" : 34, "height" : 0.6 }
{ "_id" : ObjectId("565490da88ce9d2ce2a84254"), "name" : "Jynx", "description" : "Aquela Boca nao me engana", "type" : "gelo", "attack" : 30, "defense" : 25, "height" : 1.4 }
{ "_id" : ObjectId("565490da88ce9d2ce2a84255"), "name" : "Ledian", "description" : "Joaninha do Boxe", "type" : "inseto", "attack" : 30, "defense" : 25, "height" : 1.4 }
{ "_id" : ObjectId("565490da88ce9d2ce2a84256"), "name" : "Magikarp", "description" : "Peixe Inutil", "type" : "água", "attack" : 10, "defense" : 15, "height" : 0.9 }
>
##Pokemon (passo 6)

> var query = {name: 'Arbok'}
> var poke = db.pokemons.findOne(query)
> poke
{
        "_id" : ObjectId("565490da88ce9d2ce2a84252"),
        "name" : "Arbok",
        "description" : "Cobra Mui Loka",
        "type" : "Veneno",
        "attack" : 49,
        "defense" : 45,
        "height" : 3.5
}
>
```
##Atualização do Pokemon (passo 7)
```
> var query = {name: 'Arbok'}
> var poke = db.pokemons.findOne(query)
> poke
{
        "_id" : ObjectId("565490da88ce9d2ce2a84252"),
        "name" : "Arbok",
        "description" : "Cobra Mui Loka",
        "type" : "Veneno",
        "attack" : 49,
        "defense" : 45,
        "height" : 3.5
}
> poke.description
Cobra Mui Loka
> poke.description = "Cobra mui Loka de arretada"
Cobra mui Loka de arretada
> db.pokemons.save(poke)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.pokemons.findOne(query)
{
        "_id" : ObjectId("565490da88ce9d2ce2a84252"),
        "name" : "Arbok",
        "description" : "Cobra mui Loka de arretada",
        "type" : "Veneno",
        "attack" : 49,
        "defense" : 45,
        "height" : 3.5
}
>
```
