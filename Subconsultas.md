1. Subconsulta no SELECT
Utilizada para calcular ou buscar valores adicionais em outra consulta.
````sql
-- Retorna o nome dos funcionários e o salário médio de seus respectivos cargos
SELECT nome, 
       (SELECT AVG(salario) 
        FROM funcionarios f2 
        WHERE f2.cargo_id = funcionarios.cargo_id) AS salario_medio_cargo 
FROM funcionarios;
````
2. Subconsulta no WHERE
Utilizada para filtrar dados com base nos resultados de outra consulta.
````sql
-- Retorna os funcionários que têm salário acima da média
SELECT nome, salario 
FROM funcionarios 
WHERE salario > (SELECT AVG(salario) FROM funcionarios);
````
3. Subconsulta no FROM (View Inline)
Trata a subconsulta como uma tabela temporária.
````sql
-- Calcula o salário médio por cargo e retorna apenas os cargos com média acima de 5000
SELECT cargo_id, salario_medio 
FROM (SELECT cargo_id, AVG(salario) AS salario_medio 
      FROM funcionarios 
      GROUP BY cargo_id) AS subquery 
WHERE salario_medio > 5000;
````
4. Subconsulta no HAVING
Utilizada para filtrar grupos após uma operação agregada.
````sql
-- Retorna os cargos que possuem média salarial acima da média geral
SELECT cargo_id, AVG(salario) AS salario_medio 
FROM funcionarios 
GROUP BY cargo_id 
HAVING AVG(salario) > (SELECT AVG(salario) FROM funcionarios);
````
5. Subconsulta com IN
Utilizada para verificar se valores estão presentes em um conjunto retornado por outra consulta.
````sql
-- Retorna os nomes dos funcionários que pertencem aos departamentos com mais de 5 pessoas
SELECT nome 
FROM funcionarios 
WHERE departamento_id IN (SELECT departamento_id 
                          FROM funcionarios 
                          GROUP BY departamento_id 
                          HAVING COUNT(*) > 5);
````
6. Subconsulta com EXISTS
Verifica se uma subconsulta retorna algum resultado.
````sql
-- Retorna os nomes dos funcionários que têm supervisores
SELECT nome 
FROM funcionarios f1 
WHERE EXISTS (SELECT 1 
              FROM funcionarios f2 
              WHERE f1.supervisor_id = f2.id);
````
7. Subconsulta Correlacionada
A subconsulta depende de valores da consulta externa.
````sql
-- Retorna os funcionários que têm salário acima da média do seu próprio cargo
SELECT nome, salario 
FROM funcionarios f1 
WHERE salario > (SELECT AVG(salario) 
                 FROM funcionarios f2 
                 WHERE f1.cargo_id = f2.cargo_id);
````
