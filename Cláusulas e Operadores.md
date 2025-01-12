WHERE: Filtra os resultados.
ORDER BY: Ordena os resultados.
GROUP BY: Agrupa dados para operações agregadas.
HAVING: Filtra grupos criados por GROUP BY.
Operadores Lógicos: AND, OR, NOT.
Operadores de Comparação: =, <>, >, <.


1. WHERE: Filtra os resultados com base em uma condição.

````sql 
SELECT nome, cargo, salario 
FROM funcionarios 
WHERE salario > 4000;
````

2. ORDER BY: Ordena os resultados em ordem crescente (ASC) ou decrescente (DESC).

````sql 
SELECT nome, cargo, salario 
FROM funcionarios 
ORDER BY salario DESC;
````
3. GROUP BY: Agrupa dados para realizar operações agregadas.

````sql 
SELECT cargo, AVG(salario) AS salario_medio 
FROM funcionarios 
GROUP BY cargo;
````
4. HAVING: Filtra grupos criados com GROUP BY.

````sql 
SELECT cargo, AVG(salario) AS salario_medio 
FROM funcionarios 
GROUP BY cargo 
HAVING AVG(salario) > 4500;
````

5. Operadores Lógicos: Combina condições com AND, OR e NOT.
````sql 
-- Exemplo com AND
SELECT nome, cargo, salario 
FROM funcionarios 
WHERE cargo = 'Desenvolvedor' AND salario > 5000;

-- Exemplo com OR
SELECT nome, cargo, salario 
FROM funcionarios 
WHERE cargo = 'Desenvolvedor' OR cargo = 'Analista';

-- Exemplo com NOT
SELECT nome, cargo, salario 
FROM funcionarios 
WHERE NOT cargo = 'Estagiário';
````

6. Operadores de Comparação: Exemplos com =, <>, >, <.
````sql 
-- Exemplo com '='
SELECT nome, cargo 
FROM funcionarios 
WHERE cargo = 'Gerente';

-- Exemplo com '<>'
SELECT nome, cargo 
FROM funcionarios 
WHERE cargo <> 'Estagiário';

-- Exemplo com '>'
SELECT nome, cargo 
FROM funcionarios 
WHERE salario > 4000;

-- Exemplo com '<'
SELECT nome, cargo 
FROM funcionarios 
WHERE salario < 3000;
````
