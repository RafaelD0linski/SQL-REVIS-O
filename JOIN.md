1. INNER JOIN
Retorna apenas as linhas que têm correspondência nas duas tabelas.
````sql 
SELECT funcionarios.nome, cargos.descricao 
FROM funcionarios 
INNER JOIN cargos 
ON funcionarios.cargo_id = cargos.id;
````

2. LEFT JOIN (ou LEFT OUTER JOIN)
Retorna todas as linhas da tabela à esquerda, e as correspondentes da tabela à direita. Onde não há correspondência, os valores da tabela da direita serão NULL.
````sql 
SELECT funcionarios.nome, cargos.descricao 
FROM funcionarios 
LEFT JOIN cargos 
ON funcionarios.cargo_id = cargos.id;
````
3. RIGHT JOIN (ou RIGHT OUTER JOIN)
Retorna todas as linhas da tabela à direita, e as correspondentes da tabela à esquerda. Onde não há correspondência, os valores da tabela da esquerda serão NULL.
````sql 
SELECT funcionarios.nome, cargos.descricao 
FROM funcionarios 
RIGHT JOIN cargos 
ON funcionarios.cargo_id = cargos.id;
````
4. FULL JOIN (ou FULL OUTER JOIN)
Retorna todas as linhas quando há correspondência em uma ou ambas as tabelas. Onde não há correspondência, os valores da tabela sem correspondência serão NULL.
````sql 
SELECT funcionarios.nome, cargos.descricao 
FROM funcionarios 
FULL JOIN cargos 
ON funcionarios.cargo_id = cargos.id;
````
5. CROSS JOIN
Retorna o produto cartesiano das duas tabelas, combinando cada linha de uma tabela com todas as linhas da outra.
````sql 
SELECT funcionarios.nome, cargos.descricao 
FROM funcionarios 
CROSS JOIN cargos;
````
6. SELF JOIN
É um join de uma tabela consigo mesma. Útil para comparar linhas dentro da mesma tabela.
````sql 
SELECT a.nome AS funcionario, b.nome AS supervisor 
FROM funcionarios a 
INNER JOIN funcionarios b 
ON a.supervisor_id = b.id;
````
