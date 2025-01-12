# SQL-REVIS-O
## Principais Comandos DDL (Data Definition Language):

CREATE TABLE: Criação de tabelas.
ALTER TABLE: Alteração da estrutura de tabelas. 
DROP TABLE: Exclusão de tabelas.

```sql
CREATE TABLE Funcionarios (
    ID INT PRIMARY KEY,
    Nome VARCHAR(100),
    Cargo VARCHAR(50),
    Salario DECIMAL(10, 2)
);
```


``` sql
-- Adicionar uma nova coluna: 
ALTER TABLE Funcionarios
ADD DataContratacao DATE;

-- Alterar o tipo de dado de uma coluna:
ALTER TABLE Funcionarios
MODIFY Salario DECIMAL(12, 2);

-- Renomear uma coluna:
ALTER TABLE Funcionarios
RENAME COLUMN Cargo TO CargoAtual;
```


Excluir uma tabela:
```sql
DROP TABLE Funcionarios;
```


