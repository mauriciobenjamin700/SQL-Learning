## Guia Detalhado sobre Funções Agregadas e Agrupamento de Resultados em SQL

**Introdução**

As funções agregadas em SQL permitem calcular valores estatísticos a partir de um conjunto de dados. Já o agrupamento de resultados (GROUP BY) organiza os dados em grupos e aplica as funções agregadas a cada grupo. Combinadas, essas ferramentas são essenciais para realizar análises complexas e obter insights valiosos dos seus dados.

**Funções Agregadas:**

* **COUNT:** Conta o número de linhas em uma coluna ou conjunto de resultados.
* **SUM:** Soma os valores em uma coluna numérica.
* **AVG:** Calcula a média dos valores em uma coluna numérica.
* **MIN:** Retorna o menor valor em uma coluna.
* **MAX:** Retorna o maior valor em uma coluna.
* **GROUP BY:** Agrupa as linhas por uma ou mais colunas.

**Exemplos:**

**1. Contando o número de clientes por país:**

```sql
SELECT pais, COUNT(*) AS total_clientes
FROM clientes
GROUP BY pais;
```

**Explicação:**

Este comando agrupa os clientes por país e conta o número de clientes em cada grupo. A função COUNT(*) conta todas as linhas em cada grupo, incluindo linhas com valores nulos.

**Saída:**

| pais | total_clientes |
|---|---|
| Brasil | 100 |
| EUA | 50 |
| China | 25 |

**2. Calculando a média de vendas por produto:**

```sql
SELECT produto, AVG(valor_venda) AS media_venda
FROM vendas
GROUP BY produto;
```

**Explicação:**

Este comando agrupa as vendas por produto e calcula a média do valor de venda em cada grupo. A função AVG ignora os valores nulos ao calcular a média.

**Saída:**

| produto | media_venda |
|---|---|
| TV | R$ 1.000 |
| Celular | R$ 500 |
| Notebook | R$ 2.000 |

**3. Encontrando o cliente com a maior compra:**

```sql
SELECT cliente_id, MAX(valor_venda) AS maior_compra
FROM vendas
GROUP BY cliente_id;
```

**Explicação:**

Este comando agrupa as vendas por cliente e encontra o cliente com a maior compra. A função MAX retorna o maior valor em cada grupo.

**Saída:**

| cliente_id | maior_compra |
|---|---|
| 1 | R$ 5.000 |
| 2 | R$ 4.000 |
| 3 | R$ 3.000 |

**4. Combinando funções agregadas:**

```sql
SELECT pais, COUNT(*) AS total_clientes, AVG(valor_venda) AS media_venda
FROM clientes
INNER JOIN vendas
ON clientes.id = vendas.cliente_id
GROUP BY pais;
```

**Explicação:**

Este comando combina as funções COUNT e AVG para calcular o número total de clientes e a média de vendas por país.

**Saída:**

| pais | total_clientes | media_venda |
|---|---|---|
| Brasil | 100 | R$ 1.000 |
| EUA | 50 | R$ 500 |
| China | 25 | R$ 2.000 |

**Dicas:**

* Use o GROUP BY para organizar os dados antes de aplicar as funções agregadas.
* Use funções agregadas diferentes para obter diferentes insights dos seus dados.
* Combine funções agregadas para obter análises mais complexas.
* Use filtros (WHERE) para analisar subconjuntos de dados.

**Recursos Adicionais:**

* W3Schools - Funções Agregadas em SQL: [https://www.w3schools.com/sql/sql_aggregate_functions.asp](https://www.w3schools.com/sql/sql_aggregate_functions.asp)
* GeeksforGeeks - Agrupamento em SQL: [URL inválido removido]
* Tutorials Point - Funções Agregadas e Agrupamento em SQL: [URL inválido removido]

**Conclusão:**

As funções agregadas e o agrupamento de resultados são ferramentas poderosas para analisar dados em SQL. Ao dominar essas técnicas, você poderá obter informações valiosas dos seus dados e tomar decisões mais inteligentes.
