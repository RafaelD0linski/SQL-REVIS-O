Funções Agregadas

COUNT(), SUM(), AVG(), MIN(), MAX(). Exemplo:

1. COUNT(): Conta o número de registros em uma tabela ou coluna.
````sql
-- Conta o número total de funcionários na tabela
SELECT COUNT(*) AS total_funcionarios 
FROM funcionarios;

-- Conta quantos funcionários têm o cargo de 'Desenvolvedor'
SELECT COUNT(nome) AS desenvolvedores 
FROM funcionarios 
WHERE cargo = 'Desenvolvedor';
````
2. SUM(): Calcula a soma de valores em uma coluna.
````sql
-- Soma dos salários de todos os funcionários
SELECT SUM(salario) AS total_salarios 
FROM funcionarios;

-- Soma dos salários de funcionários do cargo 'Gerente'
SELECT SUM(salario) AS total_salarios_gerentes 
FROM funcionarios 
WHERE cargo = 'Gerente';
````
3. AVG(): Calcula a média dos valores em uma coluna.
````sql
-- Média dos salários de todos os funcionários
SELECT AVG(salario) AS salario_medio 
FROM funcionarios;

-- Média dos salários de funcionários no cargo 'Analista'
SELECT AVG(salario) AS salario_medio_analistas 
FROM funcionarios 
WHERE cargo = 'Analista';
````
4. MIN(): Retorna o menor valor em uma coluna.
````sql
-- Menor salário entre os funcionários
SELECT MIN(salario) AS menor_salario 
FROM funcionarios;

-- Menor salário entre os desenvolvedores
SELECT MIN(salario) AS menor_salario_desenvolvedor 
FROM funcionarios 
WHERE cargo = 'Desenvolvedor';
````
5. MAX(): Retorna o maior valor em uma coluna.
````sql
-- Maior salário entre os funcionários
SELECT MAX(salario) AS maior_salario 
FROM funcionarios;

-- Maior salário entre os gerentes
SELECT MAX(salario) AS maior_salario_gerente 
FROM funcionarios 
WHERE cargo = 'Gerente';
````
