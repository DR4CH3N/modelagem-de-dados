## Comandos SQL - Referencia
(obs: SQL não e case sensitive porem e recomendado esrever tudo em letra maiuscula)
## nodelagem fisica

### criar banco de dados
```sql
CREATE DATABASE vendas CHARACTER SET utf8mb4;
```
### criar a tabela fabricantes 
```sql
CREATE TABLE fabricantes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT, 
    nome VARCHAR(45) NOT NULL
);
```

### VISUALIZAR DETALHES ESTRUTURAIS DA TABELA
```sql
DESC fabricantes;
```
### criar a tabela produtos

```sql
CREATE TABLE produtos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT, 
    nome VARCHAR(45) NOT NULL, 
    descricao TEXT(1000) NOT NULL, 
    preco DECIMAL(6,2) NOT NULL,
    fabricante_id INT NOT NULL
); 
```
### criação da chave estrangeira (relacionamento entre as tabelas)

```sql
ALTER TABLE produtos
    # CONSTRAINT é uma restrição definida no relacionamento;
    ADD CONSTRAINT fk_produtos_fabricantes

    # a chave estrangeira deve fazer referencia a chave primaria
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id);
```

### deletar uma tabela ou database
```sql
DROP TABLE nome_tabela

DROP DATABASE nome_database
```
### acessar/entrar em uma database
```sql
USE DATABASE nome_database
```