Primary Key (PK): Garante que cada linha em uma tabela seja identificável de forma única.
Foreign Key (FK): Estabelece relacionamentos entre tabelas, garantindo a integridade referencial.
Unique: Evita duplicações em uma coluna (sem a necessidade de ser PK).
Not Null: Obriga o preenchimento da coluna, evitando valores nulos.

1. Primary Key (PK): Identificador único para cada registro em uma tabela.
````sql
CREATE TABLE funcionarios (
    id INT PRIMARY KEY,       -- id é a chave primária
    nome VARCHAR(100) NOT NULL,
    cargo_id INT
);
-- Cada valor na coluna id será único e não pode ser nulo.
````
2. Foreign Key (FK): Relaciona uma tabela a outra.
````sql
CREATE TABLE cargos (
    id INT PRIMARY KEY,       -- id é a chave primária de cargos
    descricao VARCHAR(100) NOT NULL
);

CREATE TABLE funcionarios (
    id INT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    cargo_id INT,
    FOREIGN KEY (cargo_id) REFERENCES cargos(id)  -- cargo_id é uma chave estrangeira
);
-- A coluna cargo_id na tabela funcionarios faz referência à coluna id da tabela cargos.
````
3. Unique: Garante que valores em uma coluna sejam únicos.
````sql
CREATE TABLE usuarios (
    id INT PRIMARY KEY,
    email VARCHAR(150) UNIQUE,  -- email deve ser único
    nome VARCHAR(100) NOT NULL
);
-- Nenhum valor duplicado será permitido na coluna email.
````
4. Not Null: Impede que uma coluna aceite valores nulos.
````sql
CREATE TABLE produtos (
    id INT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,  -- nome não pode ser nulo
    preco DECIMAL(10, 2) NOT NULL
);
-- As colunas nome e preco devem sempre conter valores.
-- Exemplo Completo: Combinação de PK, FK, Unique e Not Null.

CREATE TABLE departamentos (
    id INT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL UNIQUE  -- Nome deve ser único e não pode ser nulo
);

CREATE TABLE funcionarios (
    id INT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(150) UNIQUE,
    departamento_id INT NOT NULL,
    FOREIGN KEY (departamento_id) REFERENCES departamentos(id)  -- Relaciona com departamentos
);
````
