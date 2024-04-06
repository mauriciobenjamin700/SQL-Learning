## Junções em SQL: Um Guia Completo com Códigos, Explicações e Exemplos

**Introdução**

As junções (joins) em SQL são operações que combinam linhas de duas ou mais tabelas com base em colunas comuns. Elas são ferramentas essenciais para recuperar dados de forma eficiente e precisa em bancos de dados relacionais.

**Tipos de Junções**

Existem cinco tipos principais de junções em SQL:

* **INNER JOIN:** Retorna apenas as linhas que possuem uma correspondência em ambas as tabelas.
* **LEFT JOIN:** Retorna todas as linhas da tabela esquerda, mesmo que não haja uma correspondência na tabela direita.
* **RIGHT JOIN:** Retorna todas as linhas da tabela direita, mesmo que não haja uma correspondência na tabela esquerda.
* **FULL JOIN:** Retorna todas as linhas de ambas as tabelas, mesmo que não haja uma correspondência em nenhuma delas.
* **CROSS JOIN:** Retorna todas as linhas de ambas as tabelas, como um produto cartesiano.

**Exemplos**

**1. INNER JOIN:**

```sql
SELECT *
FROM clientes
INNER JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```

**Explicação:**

Este comando irá retornar todas as linhas da tabela `clientes` que possuem uma correspondência na tabela `pedidos`. Isso significa que apenas os clientes que fizeram pelo menos um pedido serão exibidos.

**Entrada:**

* Tabela `clientes`:

| id | nome |
|---|---|
| 1 | João |
| 2 | Maria |
| 3 | Pedro |

* Tabela `pedidos`:

| id | cliente_id | produto |
|---|---|---|
| 1 | 1 | TV |
| 2 | 2 | Celular |
| 3 | 3 | Notebook |

**Saída:**

| id | nome | id | produto |
|---|---|---|---|
| 1 | João | 1 | TV |
| 2 | Maria | 2 | Celular |

**2. LEFT JOIN:**

```sql
SELECT *
FROM clientes
LEFT JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```

**Explicação:**

Este comando irá retornar todas as linhas da tabela `clientes`, mesmo que não haja uma correspondência na tabela `pedidos`. Isso significa que todos os clientes serão exibidos, mesmo que não tenham feito nenhum pedido.

**Saída:**

| id | nome | id | produto |
|---|---|---|---|
| 1 | João | 1 | TV |
| 2 | Maria | 2 | Celular |
| 3 | Pedro | NULL | NULL |

**3. RIGHT JOIN:**

```sql
SELECT *
FROM clientes
RIGHT JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```

**Explicação:**

Este comando irá retornar todas as linhas da tabela `pedidos`, mesmo que não haja uma correspondência na tabela `clientes`. Isso significa que todos os pedidos serão exibidos, mesmo que não tenham sido feitos por um cliente existente.

**Saída:**

| id | cliente_id | produto |
|---|---|---|
| 1 | 1 | TV |
| 2 | 2 | Celular |
| 3 | 3 | Notebook |

**4. FULL JOIN:**

```sql
SELECT *
FROM clientes
FULL JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```

**Explicação:**

Este comando irá retornar todas as linhas de ambas as tabelas, mesmo que não haja uma correspondência em nenhuma delas. Isso significa que todos os clientes e pedidos serão exibidos, mesmo que alguns clientes não tenham feito nenhum pedido ou alguns pedidos não tenham sido feitos por um cliente existente.

**Saída:**

| id | nome | id | cliente_id | produto |
|---|---|---|---|---|
| 1 | João | 1 | 1 | TV |
| 2 | Maria | 2 | 2 | Celular |
| 3 | Pedro | NULL | NULL | NULL |
| NULL | NULL | 3 | 3 | Notebook |

**5. CROSS JOIN:**

```sql
SELECT *
FROM clientes
CROSS JOIN pedidos;
```

**Explicação:**

Este comando irá retornar todas as linhas de ambas as tabelas, como um produto cartesiano. Isso significa que todas as linhas da tabela `clientes` serão combinadas com todas as linhas da tabela `pedidos`, resultando em um grande número de linhas.

**Saída:**

| id | nome | id | cliente_id | produto |
|---|---|---|---|---|
| 1 | João | 1 | 1 | TV |
| 1 | João | 2 | 2 | Celular |
| 