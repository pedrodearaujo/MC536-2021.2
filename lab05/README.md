# Modelo para Apresentação do Lab05 - Marcadores e Taxonomia em Cypher

Estrutura de pastas:

~~~
├── README.md  <- arquivo apresentando a tarefa
~~~

# Aluno
* `223382`: `Pedro Henrique Rodrigues de Araujo`

## Tarefa de Cypher sobre Marcadores e Taxonomia

## Tarefa 1

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, sem considerar as categorias subordinadas.

### Resolução
~~~cypher
MATCH (m:Marcador)-[:Pertence]->(c:Categoria)
WHERE c.id = 'Serviços'
RETURN m
~~~

## Tarefa 2

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, considerando as categorias subordinadas.

### Resolução
~~~cypher
MATCH (c1:Categoria)-[:Superior]->(c2:Categoria)
WHERE c2.id = 'Serviços'

MATCH (c3:Categoria)-[:Superior]->(c4:Categoria)
WHERE c4.id = c1.id

MATCH (c5:Categoria)-[:Superior]->(c6:Categoria)
WHERE c6.id = 'Serviços'

MATCH (m1:Marcador)-[:Pertence]->(c3:Categoria)

MATCH (m2:Marcador)-[:Pertence]->(c5:Categoria)

MATCH (m3:Marcador)-[:Pertence]->(c6:Categoria)


RETURN m1, m2, m3
~~~
