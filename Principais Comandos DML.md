Principais Comandos DML (Data Manipulation Language):

INSERT: Inserção de dados.
SELECT: Consulta de dados.
UPDATE: Atualização de dados.
DELETE: Exclusão de dados.


INSERT:
```` sql
INSERT INTO funcionarios (nome, cargo, salario) 
VALUES ('João Silva', 'Desenvolvedor', 5000);
````

SELECT:
```` sql
INSERT INTO funcionarios (nome, cargo, salario) 
VALUES ('João Silva', 'Desenvolvedor', 5000);
SELECT: Para consultar dados de uma tabela.
````

UPDATE:
```` sql 
SELECT nome, cargo, salario 
FROM funcionarios 
WHERE cargo = 'Desenvolvedor';
UPDATE: Para atualizar dados em uma tabela.
````

DELETE: 
```` sql 
UPDATE funcionarios 
SET salario = 5500 
WHERE nome = 'João Silva';
DELETE: Para excluir dados de uma tabela.
```` 

DELETE FROM funcionarios 
WHERE nome = 'João Silva';
