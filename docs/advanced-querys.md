## Guia Definitivo de Consultas Avançadas em SQL

**Introdução:**

O SQL (Structured Query Language) é uma linguagem poderosa para gerenciar dados em bancos de dados relacionais. As consultas SQL permitem recuperar, manipular e analisar dados de forma eficiente. Este guia se concentra em consultas avançadas que vão além dos comandos básicos SELECT, INSERT, UPDATE e DELETE.

**Tópicos Abordados:**

* **Junções (Joins):** Combinar dados de várias tabelas com base em colunas comuns.
    * **INNER JOIN:** Retorna linhas que possuem uma correspondência em ambas as tabelas.
    * **LEFT JOIN:** Retorna todas as linhas da tabela esquerda, mesmo que não haja uma correspondência na tabela direita.
    * **RIGHT JOIN:** Retorna todas as linhas da tabela direita, mesmo que não haja uma correspondência na tabela esquerda.
    * **FULL JOIN:** Retorna todas as linhas de ambas as tabelas, mesmo que não haja uma correspondência em nenhuma delas.
    * **CROSS JOIN:** Retorna todas as linhas de ambas as tabelas como um produto cartesiano.
* **Subconsultas:** Consultas dentro de outras consultas.
    * **Subconsultas correlacionadas:** Compartilham colunas com a consulta externa.
    * **Subconsultas não correlacionadas:** Não dependem da consulta externa.
* **Funções Agregadas:** Calcular valores estatísticos a partir de um conjunto de dados.
    * **COUNT:** Conta o número de linhas em uma coluna ou conjunto de resultados.
    * **SUM:** Soma os valores em uma coluna numérica.
    * **AVG:** Calcula a média dos valores em uma coluna numérica.
    * **MIN:** Retorna o menor valor em uma coluna.
    * **MAX:** Retorna o maior valor em uma coluna.
* **Agrupamento de Resultados (GROUP BY):** Organizar os dados em grupos e aplicar as funções agregadas a cada grupo.
* **Cláusulas WHERE e HAVING:** Filtrar os resultados da consulta com base em condições específicas.
    * **WHERE:** Filtra as linhas antes do agrupamento e da aplicação das funções agregadas.
    * **HAVING:** Filtra os grupos após o agrupamento e a aplicação das funções agregadas.
* **Ordenação de Resultados (ORDER BY):** Ordenar os resultados da consulta por uma ou mais colunas.
* **Limitação de Resultados (LIMIT):** Limitar o número de linhas retornadas pela consulta.

**Exemplos:**

**1. Junção de tabelas:**

```sql
SELECT *
FROM clientes
INNER JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```

**2. Subconsulta:**

```sql
SELECT nome
FROM clientes
WHERE id IN (SELECT cliente_id FROM pedidos WHERE valor_total > 1000);
```

**3. Funções agregadas e agrupamento:**

```sql
SELECT pais, COUNT(*) AS total_clientes
FROM clientes
GROUP BY pais;
```

**4. Cláusulas WHERE e HAVING:**

```sql
SELECT pais, AVG(valor_venda) AS media_venda
FROM vendas
WHERE pais = 'Brasil'
HAVING media_venda > 500;
```

**5. Ordenação e limitação:**

```sql
SELECT nome, cidade
FROM clientes
ORDER BY cidade DESC
LIMIT 10;
```

**Recursos Adicionais:**

* **W3Schools - Consultas Avançadas em SQL:** [URL inválido removido]
* **GeeksforGeeks - Consultas Complexas em SQL:** [URL inválido removido]
* **Tutorials Point - Consultas Avançadas em SQL:** [URL inválido removido]

**Observações:**

* Este guia serve como ponto de partida para o aprendizado de consultas avançadas em SQL.
* Aprofunde seus conhecimentos através de cursos online, tutoriais e documentações específicas para o SGBD de sua escolha (MySQL, PostgreSQL, Oracle, etc.).
* Pratique com exercícios e exemplos para dominar as técnicas de consulta avançada.

**Tópicos Adicionais:**

* **Joins com várias tabelas:**
* **Subconsultas com EXISTS e IN:**
* **Funções de janela (Window Functions):**
* **Expressões