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
(escreva aqui a resolução em Cypher)
~~~
